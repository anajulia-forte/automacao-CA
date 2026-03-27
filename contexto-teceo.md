# Contexto Teceo

## O que é a Teceo

SaaS B2B vertical para o mercado de moda e lifestyle no atacado (wholesale). Atende marcas, multimarcas, franquias e representantes comerciais.

A Teceo **não é** um ERP, não é um marketplace, não é um e-commerce B2C. É a plataforma que digitaliza a relação comercial entre quem fabrica/distribui e quem compra pra revender.

**Tese central:** vertical SaaS + network effects. Não é só software transacional — é inteligência que conecta demanda, decisão e execução na cadeia de moda.

---

## Produto

### V1 — Core atual (Commercial Commerce)

- Showroom digital (catálogo B2B, grades, preços por canal)
- Pedidos B2B (sell-in, carrinho, condições comerciais, aprovação)
- Gestão de vendedores e representantes
- Portal do lojista (pedidos, notas fiscais, contas a receber, devoluções)
- Analytics e relatórios de vendas
- Metas comerciais

### V2 — Em construção (Inteligência)

- **Sell-out:** visibilidade de dados do ponto de venda dentro da experiência de sell-in
- **Decisão:** sortimento, OTB (open-to-buy), planejamento de compra inteligente
- **Execução:** reposição automática, sugestão de pedido baseada em dados

### 3 Pilares de Raciocínio

| # | Pilar | O que representa |
|---|---|---|
| 1 | **Demanda** | Sell-out, sinal de mercado, o que o consumidor final está comprando |
| 2 | **Decisão** | Sortimento, OTB, planejamento de quanto e o quê comprar |
| 3 | **Execução** | Pedido, reposição, logística de sell-in |

---

## Clientes e Mercado

- **Clientes:** marcas de moda/lifestyle que vendem no atacado (B2B) — desde marcas médias regionais até grandes operações com centenas de multimarcas
- **Usuários:** times comerciais das marcas (vendedores, gerentes, diretores) e lojistas/compradores (multimarcas e franqueados)
- **Mercado:** moda wholesale no Brasil — grande, digitalização lenta, muita operação manual (WhatsApp, planilha, pedido em papel)
- **Concorrência:** ERPs genéricos tentando resolver sell-in, ferramentas horizontais de e-commerce B2B, planilhas. Poucos verticais especializados em moda

---

## Estrutura do Time

- ~50 pessoas, 100% remoto, sem escritório
- **Squads:** produto, engenharia, dados, comercial, CS, marketing
- **Cultura:** liberdade com responsabilidade, transparência radical, régua alta de contratação
- **Founders:**
  - Guilherme Scalon — CEO (produto/estratégia)
  - Alan Melo Clappis — CTO (engenharia/arquitetura)

---

## Terminologia Interna

| Termo | Significado |
|---|---|
| **Sell-in** | Venda da marca pro lojista (B2B). O core da Teceo |
| **Sell-out** | Venda do lojista pro consumidor final (B2C). Dados que alimentam a inteligência da V2 |
| **OTB** (open-to-buy) | Orçamento de compra do lojista. Quanto ele pode/deve gastar por categoria |
| **Grade** | Tabela de tamanhos × cores de um produto (ex: P/M/G/GG × preto/branco/azul) |
| **Multimarca** | Loja que vende várias marcas (vs. monomarca/franquia) |
| **Showroom** | Ambiente onde a marca apresenta a coleção pro lojista. Na Teceo, é digital |
| **Representante** | Vendedor externo que atende lojistas em nome da marca. Geralmente autônomo |
| **Coleção** | Conjunto de produtos lançados por temporada (ex: inverno 26, verão 27) |
| **Pronta-entrega** | Produtos disponíveis pra envio imediato, sem esperar produção |
| **Carteira** | Conjunto de pedidos de um vendedor/representante |
| **Pré-venda** | Período de vendas antes da produção. Lojista faz pedido, marca produz depois |
| **Sell-through** | Taxa de venda do estoque (sell-out ÷ estoque). Indicador-chave de performance |
| **Markup** | Multiplicador de preço do atacado pro varejo |

---

## Stack Tecnológica

| Camada | Tecnologia |
|---|---|
| Backend | Node.js / TypeScript |
| Frontend | React |
| Banco de dados | PostgreSQL |
| Infraestrutura | AWS |
| BI | Lightdash |
| AI | Claude (Anthropic) |

---

## O que a Teceo NÃO é

- ❌ **Não é ERP** — não faz fiscal, contábil, RH
- ❌ **Não é e-commerce B2C** — não vende pro consumidor final
- ❌ **Não é marketplace** — não intermedia transação entre marca e lojista
- ❌ **Não é só catálogo digital** — tem pedido, analytics, metas, portal do lojista, sell-out
