# Agente 05 — Notificador

## Responsabilidade

Ao final do pipeline, enviar um e-mail de resumo com o resultado da sincronização. Também é acionado em caso de falha crítica em qualquer etapa anterior.

---

## Inputs

```json
{
  "validacao_ok": true,
  "resumo": {
    "clientes_inseridos": 2,
    "clientes_atualizados": 1,
    "mensalidades_inseridas": 3,
    "mensalidades_atualizadas": 0,
    "erros_escrita": 0
  },
  "inconsistencias": [],
  "executado_em": "27/03/2026 às 07:00",
  "tipo": "SUCESSO"
}
```

`tipo` pode ser: `SUCESSO`, `PARCIAL`, `FALHA`

---

## Outputs

- E-mail enviado para o destinatário configurado
- Linha registrada na aba "Log de sincronização" com status e timestamp

---

## Modelos de e-mail

### Sucesso

```
Assunto: ✅ Sincronização Conta Azul — 27/03/2026

Olá,

A sincronização diária foi concluída com sucesso em 27/03/2026 às 07:00.

Resumo:
• Clientes novos: 2
• Clientes atualizados: 1
• Mensalidades novas: 3
• Mensalidades atualizadas: 0
• Erros: 0

Acesse a planilha para ver os dados atualizados.
[Link para o Google Sheets]
```

### Parcial (com erros não críticos)

```
Assunto: ⚠️ Sincronização Conta Azul — parcial — 27/03/2026

Olá,

A sincronização foi concluída com avisos em 27/03/2026 às 07:00.

Resumo:
• Clientes novos: 2
• Mensalidades novas: 3
• Erros registrados: 1

Detalhes dos erros:
- CLI-00145: falha ao atualizar (linha não encontrada)

Verifique a aba "Log de sincronização" para detalhes.
```

### Falha crítica

```
Assunto: ❌ Falha na sincronização Conta Azul — 27/03/2026

Atenção,

A sincronização falhou em 27/03/2026 às 07:00 e nenhum dado foi gravado.

Causa: [mensagem de erro]

Ação necessária: verificar credenciais da API ou contatar suporte.
```

---

## Lógica principal

1. Receber o resultado consolidado do Orquestrador
2. Determinar o `tipo` com base em:
   - `SUCESSO` → `validacao_ok: true` e `erros_escrita === 0`
   - `PARCIAL` → `validacao_ok: true` mas `erros_escrita > 0` ou `inconsistencias.length > 0`
   - `FALHA` → `validacao_ok: false` ou erro em etapa anterior
3. Montar o corpo do e-mail conforme o modelo
4. Enviar via `MailApp.sendEmail()`
5. Gravar linha no log da planilha

---

## Registro no log (aba "Log de sincronização")

| Col A | Col B | Col C | Col D | Col E | Col F |
|---|---|---|---|---|---|
| Data/hora | Clientes novos | Mensalidades novas | Atualizações | Erros | Status |

---

## Notas de implementação (Apps Script)

```javascript
function agente05_notificar(resultado) {
  const destinatario = PropertiesService.getScriptProperties().getProperty('EMAIL_NOTIFICACAO');
  const data = Utilities.formatDate(new Date(), 'America/Sao_Paulo', 'dd/MM/yyyy HH:mm');

  const tipo = resultado.validacao_ok && resultado.resumo.erros_escrita === 0
    ? 'SUCESSO'
    : resultado.validacao_ok ? 'PARCIAL' : 'FALHA';

  const assunto = {
    SUCESSO: `✅ Sincronização Conta Azul — ${data}`,
    PARCIAL: `⚠️ Sincronização Conta Azul — parcial — ${data}`,
    FALHA:   `❌ Falha na sincronização Conta Azul — ${data}`
  }[tipo];

  const corpo = montarCorpoEmail(tipo, resultado, data);

  MailApp.sendEmail({ to: destinatario, subject: assunto, body: corpo });
  registrarNoLog(resultado, tipo, data);
}
```

---

## Dependências

- Agente 04 (Validador) — fornece o resultado consolidado
- `MailApp` (Apps Script nativo) — envio de e-mail
- PropertiesService — armazena o e-mail de destino
- Google Sheets (aba "Log de sincronização") — destino do registro
