# Agente 02 — Processador

## Responsabilidade

Receber os dados brutos do Agente 01, normalizar campos, eliminar duplicatas e mapear os dados para o formato exato das colunas do Google Sheets. Nenhum dado chega à planilha sem passar por este agente.

---

## Inputs

```json
{
  "clientes": [...],
  "mensalidades": [...],
  "coletado_em": "2026-03-27T07:00:00Z"
}
```

---

## Outputs

```json
{
  "clientes_processados": [
    {
      "id_conta_azul": "CLI-00142",
      "nome": "Marca Exemplo Ltda",
      "cnpj_cpf": "12.345.678/0001-99",
      "email": "financeiro@marca.com",
      "telefone": "(11) 98765-4321",
      "status": "Ativo",
      "data_cadastro": "10/03/2026",
      "ultima_atualizacao": "27/03/2026"
    }
  ],
  "mensalidades_processadas": [
    {
      "id_mensalidade": "MEN-0891",
      "id_cliente": "CLI-00142",
      "nome_cliente": "Marca Exemplo Ltda",
      "plano": "Pro",
      "valor": "R$ 1.200,00",
      "competencia": "Mar/2026",
      "vencimento": "05/03/2026",
      "status_pagamento": "Pago",
      "data_pagamento": "04/03/2026"
    }
  ],
  "ids_existentes_clientes": ["CLI-00142", "CLI-00143"],
  "ids_existentes_mensalidades": ["MEN-0891"]
}
```

---

## Lógica principal

### Clientes

1. Para cada cliente recebido do Agente 01:
   - Formatar CNPJ/CPF com máscara (`XX.XXX.XXX/XXXX-XX`)
   - Normalizar telefone com DDD e parênteses
   - Converter status (`active` → `Ativo`, `inactive` → `Inativo`)
   - Formatar datas para `DD/MM/AAAA`
2. Ler coluna A da aba "Clientes" e montar lista de IDs já existentes
3. Separar clientes em **novos** (ID não existe na planilha) vs **atualizados** (ID já existe)

### Mensalidades

1. Para cada mensalidade recebida:
   - Formatar valor monetário (`R$ 1.200,00`)
   - Derivar competência a partir da data de vencimento (`Mar/2026`)
   - Converter status (`paid` → `Pago`, `pending` → `Pendente`, `overdue` → `Vencido`)
   - Buscar nome do cliente a partir do `id_cliente` nos clientes já processados
2. Ler coluna A da aba "Mensalidades" e montar lista de IDs já existentes
3. Separar em **novas** vs **atualizadas**

---

## Regras de deduplicação

| Situação | Ação |
|---|---|
| ID não existe na planilha | Marca como `INSERIR` |
| ID existe e dados são idênticos | Descarta (sem alteração) |
| ID existe e há campos diferentes | Marca como `ATUALIZAR` |

---

## Tratamento de campos ausentes

| Campo | Fallback |
|---|---|
| `email` | `—` |
| `telefone` | `—` |
| `data_pagamento` (se não pago) | `—` |
| `plano` | `Não informado` |

---

## Notas de implementação (Apps Script)

```javascript
function agente02_processar(dadosBrutos) {
  const idsClientesExistentes = lerColuna('Clientes', 'A');
  const idsMensalidadesExistentes = lerColuna('Mensalidades', 'A');

  const clientesProcessados = dadosBrutos.clientes.map(c => ({
    id_conta_azul: c.id,
    nome: c.name,
    cnpj_cpf: formatarDocumento(c.document),
    email: c.email || '—',
    telefone: formatarTelefone(c.phone) || '—',
    status: c.active ? 'Ativo' : 'Inativo',
    data_cadastro: formatarData(c.createdAt),
    ultima_atualizacao: formatarData(new Date()),
    _acao: idsClientesExistentes.includes(c.id) ? 'ATUALIZAR' : 'INSERIR'
  }));

  // lógica similar para mensalidades...

  return { clientes_processados: clientesProcessados, mensalidades_processadas: [] };
}
```

---

## Dependências

- Agente 01 (Coletor) — fornece os dados brutos
- Agente 03 (Escritor) — recebe o output processado
