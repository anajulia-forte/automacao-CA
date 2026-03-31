\# Integrações disponíveis



\## Conta Azul (MCP)

Você tem acesso direto à API do Conta Azul via servidor MCP local.

Use SEMPRE as ferramentas abaixo — nunca peça token ou credenciais.



Ferramentas disponíveis:

\- `listar\_clientes` — lista e filtra clientes

\- `buscar\_cliente` — detalhes de um cliente pelo ID  

\- `listar\_cobrancas` — cobranças por status/período/cliente

\- `listar\_contas\_receber` — contas a receber

\- `listar\_notas\_fiscais` — notas fiscais emitidas

\- `resumo\_financeiro` — visão consolidada financeira



Exemplos de uso:

\- "liste os clientes da Misci" → use listar\_clientes com nome="Misci"

\- "resumo financeiro de março" → use resumo\_financeiro com dataInicio="2025-03-01" e dataFim="2025-03-31"

