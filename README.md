# Automacao-CA

Automação de sincronização de clientes e mensalidades entre a API da Conta Azul e o Google Sheets, desenvolvida para a plataforma Teceo.

## Visão Geral

Pipeline diário que coleta dados da Conta Azul, processa, escreve no Google Sheets e envia notificação por e-mail com o resultado da sincronização.

```
[Agendador Diário]
       ↓
[Agente 01 - Coletor]      → Busca clientes e cobranças novos/modificados na API
       ↓
[Agente 02 - Processador]  → Normaliza dados e define operações INSERT/UPDATE
       ↓
[Agente 03 - Escritor]     → Grava dados nas abas do Google Sheets
       ↓
[Agente 04 - Validador]    → Verifica integridade dos dados gravados
       ↓
[Agente 05 - Notificador]  → Envia resumo por e-mail e registra log
```

## Estrutura do Repositório

```
automacao-CA/
├── docs/                            # Documentação e contexto
│   ├── contexto-teceo.md            # Contexto da plataforma Teceo
│   └── manual_teceo_v2_16-03.md     # Manual estratégico
├── specs/                           # Especificações de arquitetura
│   ├── orquestrador.md              # Orquestrador do pipeline
│   └── agentes/                     # Specs individuais dos agentes
│       ├── agente-01-coletor.md
│       ├── agente-02-processador.md
│       ├── agente-03-escritor.md
│       ├── agente-04-validador.md
│       └── agente-05-notificador.md
└── src/                             # Código-fonte (Google Apps Script)
```

## Tecnologias

- **Plataforma:** Google Apps Script
- **Fonte de dados:** Conta Azul API
- **Destino:** Google Sheets (abas: Clientes, Mensalidades, Log de sincronização)
- **Notificações:** Gmail (via MailApp)
- **Credenciais:** PropertiesService (Apps Script)

## Configuração

As seguintes propriedades devem ser configuradas no PropertiesService antes de executar:

| Propriedade         | Descrição                          |
|---------------------|------------------------------------|
| `CLIENT_ID`         | Client ID da API Conta Azul        |
| `CLIENT_SECRET`     | Client Secret da API Conta Azul    |
| `REFRESH_TOKEN`     | Refresh token OAuth                |
| `SPREADSHEET_ID`    | ID da planilha Google Sheets       |
| `EMAIL_NOTIFICACAO` | E-mail para receber notificações   |

## Documentação

- Arquitetura do pipeline: [`specs/orquestrador.md`](specs/orquestrador.md)
- Specs dos agentes: [`specs/agentes/`](specs/agentes/)
- Contexto do projeto: [`docs/contexto-teceo.md`](docs/contexto-teceo.md)
