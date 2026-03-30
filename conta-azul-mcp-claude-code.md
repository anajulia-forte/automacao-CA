# Integrando Claude Code com a API do Conta Azul via MCP

> Resumo da conversa sobre como fazer o Claude Code consultar dados do Conta Azul em tempo real, sem precisar de relatórios exportados.

---

## Objetivo

Conectar o Claude Code diretamente à API do Conta Azul usando um **MCP server** (Model Context Protocol), permitindo que o Claude busque dados como clientes, cobranças e faturas em tempo real — sem necessidade de baixar relatórios manualmente.

---

## Como funciona

O Claude Code suporta MCP, que permite conectar ferramentas externas. Você cria um servidor MCP que faz as chamadas à API do Conta Azul, e o Claude passa a ter "ferramentas" disponíveis como `buscar_clientes`, `listar_cobranças`, etc.

---

## Passo a passo geral

### 1. Pegar as credenciais do Conta Azul

1. Acessar o portal de desenvolvedores: **developers-portal.contaazul.com**
2. Fazer login (pode usar a conta Conta Azul Pro existente) ou criar uma conta nova
3. Clicar em **"Criar uma aplicação"** e selecionar o tipo (Desenvolvimento ou Produção)
4. Para testes, usar `https://www.contaazul.com` como URL de redirecionamento
5. Anotar o **Client ID** e o **Client Secret** gerados

> ⚠️ Ao criar um app de desenvolvimento, uma conta de teste é criada automaticamente com acesso por 3 dias. Para mais tempo, enviar e-mail para api@contaazul.com.

### 2. Criar o arquivo do servidor MCP

Criar uma pasta (ex: `~/mcp-conta-azul`) com dois arquivos:
- O servidor MCP em Node.js
- O `package.json` com as dependências

**Exemplo básico do servidor (`conta-azul-mcp.js`):**

```js
import { McpServer } from "@modelcontextprotocol/sdk/server/mcp.js";
import { StdioServerTransport } from "@modelcontextprotocol/sdk/server/stdio.js";
import { z } from "zod";

const BASE_URL = "https://api.contaazul.com/v1";
const TOKEN = process.env.CONTA_AZUL_TOKEN;

const server = new McpServer({ name: "conta-azul", version: "1.0.0" });

// Ferramenta: listar clientes
server.tool("listar_clientes", { search: z.string().optional() }, async ({ search }) => {
  const url = new URL(`${BASE_URL}/customers`);
  if (search) url.searchParams.set("search", search);

  const res = await fetch(url, {
    headers: { Authorization: `Bearer ${TOKEN}` }
  });
  const data = await res.json();
  return { content: [{ type: "text", text: JSON.stringify(data, null, 2) }] };
});

// Ferramenta: listar cobranças/faturas
server.tool("listar_cobrancas", {
  status: z.enum(["PENDING", "PAID", "OVERDUE"]).optional(),
  data_inicio: z.string().optional(),
  data_fim: z.string().optional()
}, async (params) => {
  const url = new URL(`${BASE_URL}/bills-to-receive`);
  Object.entries(params).forEach(([k, v]) => v && url.searchParams.set(k, v));

  const res = await fetch(url, {
    headers: { Authorization: `Bearer ${TOKEN}` }
  });
  const data = await res.json();
  return { content: [{ type: "text", text: JSON.stringify(data, null, 2) }] };
});

const transport = new StdioServerTransport();
await server.connect(transport);
```

### 3. Instalar as dependências

```bash
npm install @modelcontextprotocol/sdk zod
```

### 4. Configurar no Claude Code

Editar o arquivo `~/.claude/claude.json` (ou `.claude/claude.json` dentro do projeto):

```json
{
  "mcpServers": {
    "conta-azul": {
      "command": "node",
      "args": ["/caminho/para/conta-azul-mcp.js"],
      "env": {
        "CONTA_AZUL_TOKEN": "seu_token_aqui"
      }
    }
  }
}
```

### 5. Testar

Abrir o Claude Code e pedir:

> *"Liste os clientes com cobranças em atraso esse mês"*

O Claude vai consultar direto, sem relatório.

---

## Pontos de atenção

| Item | Detalhe |
|------|---------|
| **Autenticação** | A API usa OAuth 2.0 — é necessário implementar renovação automática de token |
| **Validade do token** | O `access_token` expira em 1 hora; o `refresh_token` serve para renovar |
| **Conta de dev** | A conta de desenvolvedor é independente da conta de usuário do ERP |
| **Webhooks** | O Conta Azul não possui webhooks nativos — dados em tempo real exigem polling periódico |
| **Credenciais** | Nunca expor `client_id` e `client_secret` em repositórios públicos |

---

## Próximos passos

- [ ] Criar conta no portal de desenvolvedores do Conta Azul
- [ ] Criar o app e anotar Client ID e Client Secret
- [ ] Gerar o código completo do MCP server (incluindo OAuth com refresh automático)
- [ ] Instalar dependências e configurar no Claude Code
- [ ] Testar com queries reais

---

## Referências

- Portal de desenvolvedores: https://developers-portal.contaazul.com
- Documentação da API: https://developers.contaazul.com
- Dúvidas frequentes (API): https://ajuda.contaazul.com/hc/pt-br/articles/360044777972
