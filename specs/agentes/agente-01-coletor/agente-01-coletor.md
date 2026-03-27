# Agente 01 — Coletor

## Responsabilidade

Conectar-se à API do Conta Azul e buscar todos os clientes e mensalidades adicionados ou modificados desde a última execução. É o ponto de entrada de dados do pipeline.

---

## Inputs

| Campo | Origem | Descrição |
|---|---|---|
| `client_id` | PropertiesService (Apps Script) | Client ID OAuth do Conta Azul |
| `client_secret` | PropertiesService (Apps Script) | Client Secret OAuth do Conta Azul |
| `ultima_sincronizacao` | Aba "Log de sincronização" | Timestamp da última execução bem-sucedida |

---

## Outputs

```json
{
  "clientes": [...],
  "mensalidades": [...],
  "coletado_em": "2026-03-27T07:00:00Z",
  "erro": null
}
```

---

## Lógica principal

1. Ler `ultima_sincronizacao` na aba de log (última linha com status "Sucesso")
2. Autenticar via OAuth 2.0 no Conta Azul (Client Credentials Flow)
3. Chamar `GET /customers?updatedAfter={ultima_sincronizacao}`
4. Chamar `GET /charges?updatedAfter={ultima_sincronizacao}` (mensalidades/cobranças)
5. Paginar os resultados enquanto `hasMore === true`
6. Retornar os arrays consolidados para o Orquestrador

---

## Tratamento de erros

- **401 Unauthorized** → renovar token e tentar novamente (máx. 1 retry)
- **429 Too Many Requests** → aguardar `Retry-After` e tentar novamente
- **500+ Server Error** → abortar e registrar falha no log
- **Sem dados novos** → retornar arrays vazios (não é erro)

---

## Endpoints utilizados

```
GET https://api.contaazul.com/v1/customers
GET https://api.contaazul.com/v1/charges
POST https://api.contaazul.com/oauth2/token
```

---

## Notas de implementação (Apps Script)

```javascript
function agente01_coletar() {
  const props = PropertiesService.getScriptProperties();
  const token = obterToken(props.getProperty('CLIENT_ID'), props.getProperty('CLIENT_SECRET'));
  const ultimaSync = lerUltimaSincronizacao();

  const clientes = buscarPaginado('/v1/customers', token, ultimaSync);
  const mensalidades = buscarPaginado('/v1/charges', token, ultimaSync);

  return { clientes, mensalidades, coletado_em: new Date().toISOString(), erro: null };
}
```

---

## Dependências

- Agente 02 (Processador) — recebe o output deste agente
- Google Apps Script `UrlFetchApp` — para chamadas HTTP
- PropertiesService — para armazenar credenciais com segurança
