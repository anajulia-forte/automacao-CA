# Orquestrador — Pipeline Conta Azul → Google Sheets

## Responsabilidade

Coordenar a execução sequencial dos 5 agentes, gerenciar o estado entre eles, tratar falhas em cada etapa e garantir que o pipeline sempre termine com um registro no log e uma notificação por e-mail — mesmo em caso de erro.

---

## Visão geral do pipeline

```
[Agendador Diário]
        |
        v
[Ag. 01 — Coletor]      → dados brutos da API Conta Azul
        |
        v
[Ag. 02 — Processador]  → dados normalizados + flags INSERIR/ATUALIZAR
        |
        v
[Ag. 03 — Escritor]     → gravação no Google Sheets
        |
        v
[Ag. 04 — Validador]    → confirmação de integridade
        |
        v
[Ag. 05 — Notificador]  → e-mail de resumo + linha no log
```

---

## Configuração necessária (PropertiesService)

Antes da primeira execução, configurar as seguintes propriedades no Apps Script:

| Chave | Descrição |
|---|---|
| `CLIENT_ID` | Client ID da API Conta Azul |
| `CLIENT_SECRET` | Client Secret da API Conta Azul |
| `EMAIL_NOTIFICACAO` | E-mail que receberá o resumo diário |
| `SPREADSHEET_ID` | ID do Google Sheets de destino |

Para configurar via script:

```javascript
function configurarPropriedades() {
  const props = PropertiesService.getScriptProperties();
  props.setProperties({
    'CLIENT_ID':          'SEU_CLIENT_ID',
    'CLIENT_SECRET':      'SEU_CLIENT_SECRET',
    'EMAIL_NOTIFICACAO':  'seu@email.com',
    'SPREADSHEET_ID':     'ID_DA_SUA_PLANILHA'
  });
}
```

---

## Implementação principal

```javascript
function executarPipeline() {
  const contexto = {
    iniciado_em: new Date().toISOString(),
    etapa_atual: null,
    erro_critico: null
  };

  try {

    // Etapa 1 — Coleta
    contexto.etapa_atual = 'COLETA';
    const dadosBrutos = agente01_coletar();
    if (dadosBrutos.erro) throw new Error(`Coleta falhou: ${dadosBrutos.erro}`);

    // Atalho: sem dados novos, registrar log e encerrar sem e-mail
    const semDados = dadosBrutos.clientes.length === 0 && dadosBrutos.mensalidades.length === 0;
    if (semDados) {
      registrarLog({ clientes: 0, mensalidades: 0, atualizacoes: 0, erros: 0, status: 'Sucesso' });
      return;
    }

    // Etapa 2 — Processamento
    contexto.etapa_atual = 'PROCESSAMENTO';
    const dadosProcessados = agente02_processar(dadosBrutos);

    // Etapa 3 — Escrita
    contexto.etapa_atual = 'ESCRITA';
    const resultadoEscrita = agente03_escrever(dadosProcessados);

    // Etapa 4 — Validação
    contexto.etapa_atual = 'VALIDACAO';
    const resultadoValidacao = agente04_validar(resultadoEscrita);

    // Etapa 5 — Notificação
    contexto.etapa_atual = 'NOTIFICACAO';
    agente05_notificar(resultadoValidacao);

  } catch (erro) {
    contexto.erro_critico = erro.message;
    Logger.log(`[ORQUESTRADOR] Falha na etapa ${contexto.etapa_atual}: ${erro.message}`);

    // Sempre notificar mesmo em falha crítica
    agente05_notificar({
      validacao_ok: false,
      resumo: { clientes_inseridos: 0, clientes_atualizados: 0,
                mensalidades_inseridas: 0, mensalidades_atualizadas: 0, erros_escrita: 1 },
      inconsistencias: [{ problema: erro.message, etapa: contexto.etapa_atual }],
      tipo: 'FALHA'
    });
  }
}
```

---

## Agendamento

No Apps Script, criar um trigger de tempo para executar `executarPipeline` diariamente:

1. Abrir o projeto no Apps Script
2. Ir em **Triggers** (ícone de relógio)
3. Adicionar novo trigger:
   - Função: `executarPipeline`
   - Tipo: **Time-driven**
   - Intervalo: **Day timer**
   - Horário: **6am – 7am** (executa entre 6h e 7h no fuso configurado)

Ou via código:

```javascript
function criarTrigger() {
  ScriptApp.newTrigger('executarPipeline')
    .timeBased()
    .everyDays(1)
    .atHour(7)
    .inTimezone('America/Sao_Paulo')
    .create();
}
```

---

## Fluxo de decisão em caso de erro

| Etapa com falha | Impacto | Ação do Orquestrador |
|---|---|---|
| Ag. 01 — Coletor | Nenhum dado coletado | Abortar pipeline, enviar e-mail de falha |
| Ag. 02 — Processador | Nenhum dado gravado | Abortar pipeline, enviar e-mail de falha |
| Ag. 03 — Escritor | Dados parcialmente gravados | Continuar para validação, enviar e-mail parcial |
| Ag. 04 — Validador | Inconsistência detectada | Continuar para notificação, enviar e-mail parcial |
| Ag. 05 — Notificador | E-mail não enviado | Registrar no log, falhar silenciosamente |

---

## Estrutura de arquivos recomendada no Apps Script

```
Projeto: ContaAzul_Sync
│
├── orquestrador.gs          ← executarPipeline(), configurarPropriedades(), criarTrigger()
├── agente01_coletor.gs      ← agente01_coletar()
├── agente02_processador.gs  ← agente02_processar()
├── agente03_escritor.gs     ← agente03_escrever()
├── agente04_validador.gs    ← agente04_validar()
├── agente05_notificador.gs  ← agente05_notificar()
└── utils.gs                 ← lerColuna(), formatarData(), formatarDocumento(), registrarLog()
```

---

## Checklist de primeira execução

- [ ] Criar planilha com as abas: `Clientes`, `Mensalidades`, `Log de sincronização`
- [ ] Adicionar cabeçalhos em cada aba conforme schema definido
- [ ] Configurar credenciais via `configurarPropriedades()`
- [ ] Criar o trigger via `criarTrigger()` ou pela interface
- [ ] Executar `executarPipeline()` manualmente uma vez para validar
- [ ] Verificar e-mail de resumo recebido
- [ ] Verificar linhas gravadas na planilha e no log

---

## Dependências externas

| Serviço | Uso |
|---|---|
| API Conta Azul (OAuth 2.0) | Fonte dos dados |
| Google Sheets API | Destino dos dados |
| MailApp (nativo Apps Script) | Envio de e-mail |
| PropertiesService (nativo Apps Script) | Armazenamento de credenciais |
