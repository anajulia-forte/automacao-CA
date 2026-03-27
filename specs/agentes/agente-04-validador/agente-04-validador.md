# Agente 04 — Validador

## Responsabilidade

Após a escrita do Agente 03, verificar se os dados foram gravados corretamente na planilha. Garantir integridade antes de encerrar o pipeline.

---

## Inputs

```json
{
  "clientes_inseridos": 2,
  "clientes_atualizados": 1,
  "mensalidades_inseridas": 3,
  "mensalidades_atualizadas": 0,
  "erros": [],
  "dados_esperados": {
    "ids_clientes": ["CLI-00145", "CLI-00146"],
    "ids_mensalidades": ["MEN-0894", "MEN-0895", "MEN-0896"]
  }
}
```

---

## Outputs

```json
{
  "validacao_ok": true,
  "clientes_verificados": 2,
  "mensalidades_verificadas": 3,
  "inconsistencias": [],
  "resumo": {
    "clientes_inseridos": 2,
    "clientes_atualizados": 1,
    "mensalidades_inseridas": 3,
    "mensalidades_atualizadas": 0,
    "erros_escrita": 0
  }
}
```

---

## Lógica principal

### Verificação de presença

1. Para cada ID em `ids_clientes` esperados, confirmar que existe na coluna A da aba "Clientes"
2. Para cada ID em `ids_mensalidades` esperados, confirmar que existe na coluna A da aba "Mensalidades"
3. Registrar qualquer ID ausente como inconsistência

### Verificação de integridade mínima

Para cada linha gravada, checar que:

- Coluna A (ID) não está vazia
- Coluna B (Nome) não está vazia
- Coluna F (Status) contém valor válido (`Ativo`, `Inativo`, `Pago`, `Pendente`, `Vencido`)
- Datas estão no formato `DD/MM/AAAA`

### Decisão final

| Situação | Resultado |
|---|---|
| Todos os IDs encontrados, sem inconsistências | `validacao_ok: true` |
| IDs ausentes mas erros já registrados pelo Ag. 03 | `validacao_ok: true` com aviso |
| IDs ausentes sem registro de erro | `validacao_ok: false` — notificar Orquestrador |

---

## Tratamento de erros

- **Inconsistência detectada** → adicionar ao array `inconsistencias` e retornar `validacao_ok: false`
- **Aba não encontrada** → erro crítico, abortar e notificar
- **Validação parcial** (só alguns IDs ausentes) → retornar `validacao_ok: false` com detalhe por ID

---

## Notas de implementação (Apps Script)

```javascript
function agente04_validar(resultadoEscrita) {
  const ss = SpreadsheetApp.getActiveSpreadsheet();
  const idsClientesNaPlanilha = lerColuna('Clientes', 'A');
  const idsMensalidadesNaPlanilha = lerColuna('Mensalidades', 'A');
  const inconsistencias = [];

  resultadoEscrita.dados_esperados.ids_clientes.forEach(id => {
    if (!idsClientesNaPlanilha.includes(id)) {
      inconsistencias.push({ tipo: 'cliente', id, problema: 'ID não encontrado após escrita' });
    }
  });

  resultadoEscrita.dados_esperados.ids_mensalidades.forEach(id => {
    if (!idsMensalidadesNaPlanilha.includes(id)) {
      inconsistencias.push({ tipo: 'mensalidade', id, problema: 'ID não encontrado após escrita' });
    }
  });

  return {
    validacao_ok: inconsistencias.length === 0,
    inconsistencias,
    resumo: {
      clientes_inseridos: resultadoEscrita.clientes_inseridos,
      clientes_atualizados: resultadoEscrita.clientes_atualizados,
      mensalidades_inseridas: resultadoEscrita.mensalidades_inseridas,
      mensalidades_atualizadas: resultadoEscrita.mensalidades_atualizadas,
      erros_escrita: resultadoEscrita.erros.length
    }
  };
}
```

---

## Dependências

- Agente 03 (Escritor) — fornece o resultado da escrita e os IDs esperados
- Agente 05 (Notificador) — recebe o resumo validado para enviar por e-mail
- Google Sheets (aba "Clientes" e aba "Mensalidades") — fonte de verificação
