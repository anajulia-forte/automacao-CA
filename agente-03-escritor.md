# Agente 03 — Escritor

## Responsabilidade

Receber os dados processados e normalizados do Agente 02 e gravá-los no Google Sheets — inserindo linhas novas ou atualizando registros existentes conforme a flag `_acao` de cada registro.

---

## Inputs

```json
{
  "clientes_processados": [
    { "_acao": "INSERIR", "id_conta_azul": "CLI-00145", ... },
    { "_acao": "ATUALIZAR", "id_conta_azul": "CLI-00142", ... }
  ],
  "mensalidades_processadas": [
    { "_acao": "INSERIR", "id_mensalidade": "MEN-0894", ... }
  ]
}
```

---

## Outputs

```json
{
  "clientes_inseridos": 2,
  "clientes_atualizados": 1,
  "mensalidades_inseridas": 3,
  "mensalidades_atualizadas": 0,
  "erros": [],
  "sucesso": true
}
```

---

## Lógica principal

### Para registros com `_acao: "INSERIR"`

1. Adicionar nova linha ao final da aba correspondente
2. Preencher todas as colunas na ordem definida no schema da planilha

### Para registros com `_acao: "ATUALIZAR"`

1. Localizar a linha pelo ID na coluna A (`findIndex`)
2. Sobrescrever apenas as células que mudaram (não limpar a linha inteira)
3. Sempre atualizar a coluna "Última atualização"

### Ordem das colunas — aba Clientes

| Col | Campo |
|---|---|
| A | id_conta_azul |
| B | nome |
| C | cnpj_cpf |
| D | email |
| E | telefone |
| F | status |
| G | data_cadastro |
| H | ultima_atualizacao |

### Ordem das colunas — aba Mensalidades

| Col | Campo |
|---|---|
| A | id_mensalidade |
| B | id_cliente |
| C | nome_cliente |
| D | plano |
| E | valor |
| F | competencia |
| G | vencimento |
| H | status_pagamento |
| I | data_pagamento |

---

## Tratamento de erros

- **Linha não encontrada para ATUALIZAR** → registrar aviso e inserir como novo
- **Falha ao escrever no Sheets** → registrar no array `erros` e continuar (não abortar tudo)
- **Quota excedida (Sheets API)** → aguardar 1s e tentar novamente (máx. 3 retries)

---

## Notas de implementação (Apps Script)

```javascript
function agente03_escrever(dadosProcessados) {
  const ss = SpreadsheetApp.getActiveSpreadsheet();
  const abaClientes = ss.getSheetByName('Clientes');
  const abaMensalidades = ss.getSheetByName('Mensalidades');
  const resultado = { clientes_inseridos: 0, clientes_atualizados: 0,
                      mensalidades_inseridas: 0, mensalidades_atualizadas: 0,
                      erros: [], sucesso: true };

  dadosProcessados.clientes_processados.forEach(cliente => {
    try {
      const linha = [cliente.id_conta_azul, cliente.nome, cliente.cnpj_cpf,
                     cliente.email, cliente.telefone, cliente.status,
                     cliente.data_cadastro, cliente.ultima_atualizacao];

      if (cliente._acao === 'INSERIR') {
        abaClientes.appendRow(linha);
        resultado.clientes_inseridos++;
      } else {
        const rowIndex = encontrarLinhaPorId(abaClientes, cliente.id_conta_azul);
        if (rowIndex > 0) {
          abaClientes.getRange(rowIndex, 1, 1, linha.length).setValues([linha]);
          resultado.clientes_atualizados++;
        }
      }
    } catch (e) {
      resultado.erros.push({ id: cliente.id_conta_azul, erro: e.message });
    }
  });

  // lógica similar para mensalidades...
  return resultado;
}
```

---

## Dependências

- Agente 02 (Processador) — fornece os dados prontos para escrita
- Agente 04 (Validador) — valida o que este agente escreveu
- Google Sheets (aba "Clientes" e aba "Mensalidades")
