# teceo v2 — manual estratégico consolidado

*documento de contexto interno — mar/2026 · v5*

---

## 1. o que é a teceo v2

a teceo evolui de plataforma de commerce B2B (v1) para infraestrutura de distribuição de moda. não é SaaS com features de IA — é o protocolo onde toda decisão de distribuição de uma marca acontece, em qualquer canal, executada por humanos ou agentes autônomos.

a mudança central de posicionamento: a teceo v1 servia o canal wholesale. a teceo v2 serve **todos os canais de distribuição de uma marca** — multimarcas, franquias e lojas próprias. a dor é a mesma nos três: produto certo, loja certa, hora certa. a diferença entre canais é de nuance (pedido vs. transferência/alocação), não de natureza. e o GTM é idêntico: marca manda usar, usam.

a visão de longo prazo: cada peça de moda vendida no brasil, em qualquer canal, passou pela teceo. infraestrutura invisível de distribuição.

analogia: a B3 da distribuição de moda. não vende produtos — garante que decisões de distribuição acontecem de forma ordenada, com regras, dados e inteligência.

referência internacional: NuOrder (Lightspeed). plataforma de wholesale buying que virou infraestrutura de Nordstrom, Bloomingdale's, Saks, Macy's. 4.000+ marcas, 100.000+ varejistas. a diferença: NuOrder cresceu como ferramenta da marca, depois inverteu e fez varejistas enterprise puxarem marcas. a teceo faz o mesmo, com duas vantagens que a NuOrder não tem — sell-out integrado e cobertura de todos os canais.

---

## 2. mercado

### a abstração: 3 canais, mesma dor, usuário capturado

olhando de forma abstrata, todos os canais de venda de uma marca compartilham a mesma estrutura:

| canal | dor | usuário principal | relação com a marca |
|-------|-----|-------------------|---------------------|
| multimarcas | produto certo, loja certa, hora certa | representante comercial | contrato de representação — usa o que a marca mandar |
| franquias | produto certo, loja certa, hora certa | franqueado | monomarca, investiu no modelo — segue diretrizes da marca |
| lojas próprias | produto certo, loja certa, hora certa | gerente de loja / planejamento | funcionário da marca — usa o que ela mandar |

no multimarcas e franquia, existe transação comercial (pedido). na loja própria, existe decisão de distribuição (transferência/alocação). mas a proposta de valor — inteligência pra decidir o que mandar pra cada loja — é a mesma. e o GTM é idêntico: marca manda usar, usam.

### segmentação de porte

| porte | sell-in B2B anual | perfil |
|-------|-------------------|--------|
| PP | R$ 0-5M | micro-marcas formais. operação mínima, 1-2 reps, poucas multimarcas. |
| P | R$ 5-20M | marca pequena estruturada. 3-10 reps, 50-200 multimarcas. |
| M | R$ 20-100M | marca média consolidada. 10-30 reps, 200-1000 multimarcas, pode ter franquias. |
| G | R$ 100-500M | marca grande. 30-80 reps, rede nacional, multimarcas + franquias + lojas próprias. |
| GG | R$ 500M+ | grupo/holding com múltiplas marcas. cobertura total, todos os canais. |

### formal vs. informal

o corte não é por preço — é por modelo de negócio. formal = venda com NF, catálogo estruturado, canal de distribuição definido. informal = brás, 25 de março, feiras regionais, sacoleiras, porta de fábrica, cross-border não tributado — sem NF, sem catálogo, sem rep formal.

a teceo só endereça o mercado formal. a informalidade varia por subsegmento: vestuário ~30%, calçados ~20%, acessórios ~25%.

### o canal multimarcas

90% das vendas por intermédio de reps ou vendedores próprios. marcas não enxergam sell-out — apenas sell-in. mercado extremamente fragmentado em ERPs de PDV, o que dificulta integrações. sem padronização entre produtos: a marca vende de um jeito, o lojista cadastra tudo diferente.

processo de compras caótico: OTB no excel, pedidos de cada marca em lugar diferente, nenhuma categorização padrão, sem sistema integrado, sem visão do que já comprou vs. OTB, sem controle do que recebeu vs. pendente, cadastro 100% manual quando mercadoria chega.

### o canal de franquias

mais evoluído, crescendo forte no brasil. marca enxerga estoque do franqueado, sugere OTBs e pedidos. sem figura do rep — lojas monomarca. discussão é quanto comprar, não se comprar.

### o canal de lojas próprias

lojas operadas pela própria marca. gerente de loja / time de planejamento decide o que mandar pra cada loja, em qual quantidade, com base em quê. ERPs enterprise (Linx/TOTVS) prometem módulos de distribuição inteligente e não entregam — entregam planilha glorificada. a teceo entra pelo gap entre a promessa do ERP e a execução real.

o que a teceo oferece que o ERP não pode: (1) inteligência de rede — o ERP sabe tudo sobre as lojas daquela marca e só. a teceo sabe sobre as lojas dela E sobre milhares de outras lojas que vendem categorias parecidas. (2) execução real de OTB e distribuição inteligente.

**pra entrar de verdade nesse canal (e no de franquias com franqueado pagando, via teceo para lojistas), a teceo precisa construir um produto de inteligência de distribuição de primeira classe.** não basta adaptar a UX de sell-in — é um produto adjacente com profundidade própria: alocação inicial, reposição dinâmica, transferência entre lojas, liquidação inteligente, tudo orientado a dados de sell-through em tempo real.

as referências no brasil são **OneBeat** e **Analyticalways**. OneBeat é uma plataforma israelense de otimização de estoque com IA (levantou $15M em 2025), focada em decisões granulares e diárias de alocação e reposição. trabalha com Calvin Klein, Panasonic, Aramis, com presença forte na América Latina. Analyticalways é espanhola, 150+ marcas em 15 países, com parceria com a Linx no brasil — cobre planejamento de coleção, OTB, alocação inicial, reposição e liquidação. ambas resolvem a dor de distribuição inteligente para varejistas com rede de lojas. **a teceo precisa entregar essa profundidade de produto pra competir nesse espaço, com a vantagem de inteligência de rede cross-brand que nenhuma das duas tem.**

case concreto: Loftystyle — 64 lojas próprias, R$ 250M GMV varejo, contrato de R$ 120K. dor: decidir o que mandar pra cada loja. ERP (Linx/TOTVS) entrega operação, não inteligência.

### dois modelos de venda

entrega futura (pré-venda) e pronta-entrega. marcas fortes focam em pedidos antecipados, empurrando risco de estoque pro lojista. marcas menores operam com ambos ou focam em pronta-entrega.

### funil do mercado — moda brasil 2024

```
sell-out total moda BR              R$ 422B  (USD 74B)
  └ informal (~23%)                 R$ 116B
  └ formal (~77%)                   R$ 306B
      └ sell-in formal              R$ 133B  ← TAM
          └ SAM                     R$  90B
              └ SOM                 R$  30B
                  └ teceo (jun/25)  R$ 2.3B
```

**sell-out total moda BR = R$ 422B.** vestuário: R$ 295B (IEMI 2024). calçados: R$ 77B (IEMI/Abicalçados 2024). acessórios (joias, óculos, bolsas): R$ 50B (Mordor/ABF/Abióptica).

**informal (~23%) = R$ 116B.** venda sem NF, sem catálogo, sem rep formal. vestuário ~30% informal, calçados ~20%, acessórios ~25%.

**sell-in formal = R$ 133B (TAM).** sell-out formal (R$ 306B) ÷ markup médio (~2.3x). inclui TODO sell-in onde existe decisão de distribuição: multimarcas, franquias, lojas próprias, e-commerce de marca, dept stores.

**SAM = R$ 90B.** TAM menos dept stores verticalizadas (~R$ 30B produção interna) e micro-confecções formais sem catálogo/rep (~R$ 13B). inclui marcas P como segmento endereçável mas não validado.

**SOM = R$ 30B.** ~250 grupos M/G/GG. sell-in via multimarcas + franquias. exclui loja própria (upside). exclui marcas P/PP.

| porte | # grupos | sell-in est. | % do SOM |
|-------|----------|-------------|----------|
| GG (>R$ 500M) | ~15-20 | ~R$ 12B | ~40% |
| G (R$ 100-500M) | ~60-80 | ~R$ 11B | ~35% |
| M (R$ 20-100M) | ~150-170 | ~R$ 7B | ~25% |
| **total SOM** | **~250** | **~R$ 30B** | **100%** |

### composição do SOM por subsegmento

| subsegmento | R$ bi | # grupos |
|-------------|-------|----------|
| vestuário feminino | 7.0 | ~50 |
| vestuário masculino | 4.0 | ~35 |
| vestuário infantil | 2.5 | ~25 |
| vestuário básico/casual | 5.0 | ~30 |
| calçados | 6.0 | ~45 |
| acessórios | 2.0 | ~25 |
| esportivo/fitness | 3.5 | ~40 |
| **total** | **30.0** | **~250** |

### upsides fora do SOM moda

| upside | R$ bi | status |
|--------|-------|--------|
| marcas P/PP (~1K+ marcas) | 10 | endereçável, não validado. pós série A. |
| loja própria (upsell 250 grupos) | 8 | produto v2. Loftystyle = primeiro case. |
| dept stores — fatia terceiros | 5 | retailer-pull longo prazo. |
| e-commerce de marca | 4 | loja própria digital. adjacente. |
| **total upsides moda** | **27** | — |

### tabela de endereçabilidade

| tipo de operação | TAM? | SAM? | SOM? |
|---|---|---|---|
| marca M/G/GG → multimarcas via rep | ✓ | ✓ | ✓ |
| marca P → multimarcas via rep | ✓ | ✓ | ✗ |
| marca PP → multimarcas | ✓ | ✗ | ✗ |
| marca → franquias | ✓ | ✓ | ✓ |
| marca → lojas próprias | ✓ | ✓ | ✗ |
| marca → e-commerce próprio | ✓ | ✓ | ✗ |
| dept store — produção própria | ✓ | ✗ | ✗ |
| dept store — marcas terceiras | ✓ | ✓* | ✗ |
| venda direta / MLM | ✗ | ✗ | ✗ |
| informal | ✗ | ✗ | ✗ |

### mercado adjacente: lifestyle brasil 2024

lifestyle = casa e decoração + beleza e cuidados + saúde e bem-estar. a dor é a mesma: produto certo, loja certa, hora certa. a teceo v2 endereça distribuição em qualquer vertical, não só moda.

```
sell-out total lifestyle BR         R$ 456B  (USD 80B)
  └ informal (~19%)                 R$ 88B
  └ formal (~81%)                   R$ 368B
      └ sell-in formal              R$ 202B  ← TAM lifestyle
          └ SAM lifestyle           R$ 120B
              └ SOM lifestyle       a definir (não é foco Y1-Y3)
```

| segmento | sell-out BR (R$ bi) | % informal | sell-out formal | markup | sell-in formal |
|----------|-------------------|-----------|----------------|--------|---------------|
| casa e decoração | 182 | 20% | 146 | 2.0x | 73 |
| beleza e cuidados | 171 | 15% | 145 | 1.8x | 81 |
| saúde e bem-estar | 103 | 25% | 77 | 1.6x | 48 |
| **total lifestyle** | **456** | **~19%** | **368** | — | **202** |

notas: casa inclui móveis (~R$ 110B), têxtil lar (~R$ 30B), decoração (~R$ 42B). beleza é 4º maior mercado do mundo — venda direta MLM não endereçável. saúde inclui fitness + suplementos + wellness, exclui pharma/hospitalar.

**SAM lifestyle = R$ 120B.** exclui venda direta/MLM beleza (~R$ 50B), hipermercados/farmácias com compra centralizada (~R$ 20B), artesãos informais casa (~R$ 12B).

**o que entra no SAM lifestyle:** casa e decoração (~R$ 55B sell-in) — cama/mesa/banho (Buddemeyer, Karsten, Döhler), utilidades (Tramontina, Nadir Figueiredo), móveis e decoração de marca via rep/showroom. beleza (~R$ 40B sell-in excl. MLM) — franquias (O Boticário, QDB, MAC, Granado), multimarcas (perfumarias, drogarias regionais), profissional (Wella, Kerastase pra salões via rep). saúde (~R$ 25B sell-in) — suplementos (Integralmédica, Max Titanium, Growth) pra lojas via rep, fitness/wellness pra lojas especializadas.

### consolidado moda + lifestyle

| métrica | moda | lifestyle | total |
|---------|------|-----------|-------|
| sell-out total BR | R$ 422B | R$ 456B | R$ 878B |
| sell-out formal | R$ 306B | R$ 368B | R$ 674B |
| sell-in formal (TAM) | R$ 133B | R$ 202B | R$ 335B |
| SAM | R$ 90B | R$ 120B | R$ 210B |
| SOM (foco Y1-Y3) | R$ 30B | a definir | R$ 30B+ |

### LATAM

| segmento | brasil (USD bi) | latam ex-BR | latam total | % BR |
|----------|----------------|-------------|-------------|------|
| moda | 74 | 60 | 134 | 55% |
| lifestyle | 80 | 63 | 143 | 56% |
| **total** | **154** | **123** | **277** | **56%** |

### teceo hoje

| métrica | valor |
|---------|-------|
| teceo (jun/25) | R$ 2,3B GMV, R$ 4,2M ARR, 51 clientes |
| penetração no SOM | ~7,7% do GMV |
| base | 140k+ lojas cadastradas, 10k ativas (multimarcas), 1k+ franquias |
| unit economics (jun/25) | LTV/CAC 8,7x, logo churn 4%, NRR 99,6%, gross margin 71% |
| seed | R$ 5M (ABSeed) após 4 anos de bootstrap |

fontes: IEMI, Abicalçados, ABIT/Texbrasil, ABF, Mordor Intelligence, Statista, Grand View Research, GWI, Emergen Research, ABIHPEC.

---

# PRODUTO

---

## 3. as 3 camadas do produto

### camada 1 — software (commerce + teceo para lojistas + rep + distribuição)

o que existe e o que está sendo construído. quatro superfícies de produto sobre a mesma base:

**commerce (marca):** plataforma de sell-in — showroom digital, catálogo e preços (pré-venda, pronta-entrega, packs, composição de preços, tabelas, políticas comerciais), pedidos (offline, colaborativo, sugerido, assinatura, editor de grades), gestão do cliente 360, relatórios de vendas e faturamento. base de receita e canal de distribuição que viabiliza tudo. v1 cresce e gera caixa enquanto v2 é construída por cima.

**teceo para lojistas:** experiência de compra do varejista com sell-out integrado, hub de compras unificado independente do cenário de integração de cada marca.

**rep (representante):** ambiente próprio do representante comercial. o rep deixa de ser um cadastro dentro da brand e vira entidade de primeira classe na rede. a marca vincula o rep à sua brand; o rep gerencia seus próprios usuários e prepostos. funcionalidades: analytics cross-brand (visão consolidada de todas as marcas que atende), controle de comissões, gestão do negócio (agenda, pipeline, financeiro, carteira por preposto), controle de mostruário, gestão da região (mapa de oportunidades e cobertura), CRM do escritório (relacionamento com lojistas).

**distribuição (loja própria):** inteligência de OTB e alocação para lojas próprias da marca. produto adjacente ao commerce que compartilha o data layer — a UX e integrações são diferentes de sell-in, mas a proposta de valor é a mesma.

**add-ons:** CRM de vendas, CRM de atendimento, sell-out (beta), rachel (IA), integrações ERP, plano de sucesso.

**boundary claro:** a teceo não compete com CRM (Salesforce, HubSpot). o core é venda e distribuição B2B: OTB, inteligência de distribuição, catálogo, pedido, integração. CRM básico (oportunidades, casos, pipeline) entra incluso com limite no core, mas não é o produto. funcionalidades avançadas de CRM ficam via integração.

### camada 2 — dados (sell-in + sell-out + índice)

o ativo mais defensável. dois fluxos contínuos: sell-in via commerce e integrações com marcas; sell-out via integrações com ERPs/PDVs dos varejistas e lojas próprias. cruzados e padronizados, formam o **teceo data layer** — o grafo de dados da rede.

sobre o data layer, um **índice de moda proprietário** transforma dados brutos em inteligência: benchmarks de giro por categoria, tendências de sell-through por região, gaps entre oferta e demanda.

efeito de consolidação de canais: quando uma marca traz todos os canais pra teceo (multimarcas + franquias + lojas próprias), sell-out de lojas próprias informa decisões de multimarcas e vice-versa. o data layer fica mais rico, o índice mais preciso, os agentes mais inteligentes.

### camada 3 — AI agents (ação autônoma)

agentes que operam sobre dados pra executar decisões de distribuição. ciclo completo: collection intelligence → planejamento → sortimento/compras → reposição → performance. começam como sugestões, evoluem pra ações autônomas, e no endgame operam em agent-to-agent commerce.

---

## 4. o data layer

### ingestão de sell-in — dois vetores

**brand-push (via commerce):** marca vende pela teceo. dado mais rico: catálogo completo, preços, condições, pedidos, faturamento, devoluções. cenário ideal e objetivo de longo prazo.

**retailer-pull (via integração):** marca não vende pela teceo, mas varejista centraliza compras na plataforma. teceo integra com sistema da marca ou captura via ERP do varejista. dado menos rico, mas suficiente pra visão consolidada e alimentação do data layer. desbloqueia marcas enterprise (Nike, Adidas, Grendene, Vulcabras) que não adotariam o commerce.

### cenários de integração de sell-in

| cenário | descrição | qualidade do dado |
|---------|-----------|-------------------|
| A — commerce direto | marca vende pelo commerce. controle total | máxima |
| B — integração via varejista | marca tem API/portal. teceo integra e puxa catálogo + pedidos | média (suficiente pra data layer) |
| C — ingestão mínima | sem API. upload manual/planilha | mínima (melhor que zero) |

pro varejista é transparente — usa a teceo como hub de compras independente do cenário de cada marca.

### ingestão de sell-out

via integração com ERPs/PDVs dos varejistas: vendas ao consumidor, estoque, giro por SKU, ticket médio, sazonalidade, markdown. modelo ativo (Linx, grandes ERPs) + modelo passivo (API exposta pra ERPs menores). funciona independente do vetor de sell-in. estratégia detalhada de integração e parceria com ERPs na seção 5.

**sell-out de loja própria:** dado limpo e de alta qualidade (ERP padronizado, marca controla 100%). sell-out de lojas próprias alimenta padrões de demanda — categorias, localizações, faixas de preço, sazonalidade — que servem qualquer marca na rede. e o dado tende a ser mais limpo: a distribuição é mais deliberada, sem distorção de rep ou condição comercial, refletindo demanda real com menos ruído. o efeito multiplicador direto (1 loja própria = 1 marca) é menor que o de multimarcas (1 loja informa 10-15 marcas), mas a qualidade do sinal compensa — em escala, contribui volume relevante ao índice por categoria/região.

### a chave mestra: normalização de catálogo

o catálogo normalizado de uma marca é a chave que decodifica todo o sell-out dessa marca na rede. sem ele, dados de sell-out são ruído (cada loja cadastra diferente). com ele, todo sell-out opaco se ilumina instantaneamente.

implicação: normalizar catálogo de uma marca via projeto com grande varejista desbloqueia sell-out em **toda a rede existente**. custo finito (um projeto por marca), benefício multiplicado por todas as lojas da base que vendem aquela marca.

### sell-out: mecânica de aquisição (tradeoff ida/volta)

cadastro de produto no ERP do lojista é uma das maiores dores operacionais do varejo multimarca. quando a teceo manda sell-in estruturado (catálogo normalizado) direto pro ERP, resolve duas coisas: mata trabalho manual e padroniza dado na origem — que é o que permite ler sell-out com clareza.

**a ida (sell-in → ERP) é o que torna a volta (sell-out → teceo) tecnicamente possível e justificável.** não é troca transacional — é consequência técnica. o fluxo usa a mesma integração.

**framing pro lojista:** "a teceo conecta o catálogo da marca direto no teu sistema — tu nunca mais cadastra produto manualmente. pra isso funcionar, o fluxo precisa ser de ida e volta." analogia do waze: dado flui porque o sistema funciona assim.

**salvaguardas:** marca A só vê sell-out de marca A. dados agregados/cruzados pertencem à teceo e alimentam o índice. transparência total via dashboard do lojista. valor progressivo — quanto mais marcas integradas, mais benchmarks o lojista recebe.

**desafio técnico atual:** de/para pós-cadastro causa duplicação nos ERPs. resolver é pré-condição pra escalar.

### sequencing do índice (recalibração)

feedback consistente do mercado: a maior dor hoje não é falta de sell-out — é falta de sell-in organizado. recalibra o sequencing:

1. **sell-in organizado** (hoje, provado) — marca sai do modelo transacional pro estrutural. arroz e feijão.
2. **sell-out de franquias** (em rollout) — canal mais limpo, ERPs padronizados, dados com NF. 100+ integradas.
3. **sell-out de lojas próprias** (em validação) — ERPs padronizados, dado limpo, integração mais simples. primeiro case: Loftystyle.
4. **sell-out de multimarcas via catálogos normalizados** (fronteira) — depende de catálogos normalizados. primeiro via design partners, depois expandindo.
5. **índice cruzado em escala** (visão) — sell-in de todas as marcas + sell-out de todos os canais = inteligência que ninguém mais tem. só chega aqui com etapas 1-4 feitas.

---

## 5. integração com ERPs de PDV: a estratégia de parceiros

### por que isso é um capítulo

a integração com ERPs de PDV é a infraestrutura que viabiliza os dois fluxos mais importantes da v2: sell-in enriquecido chegando no sistema do lojista (ida) e sell-out voltando pro data layer (volta). sem isso, o data layer não se alimenta, o índice não existe, e os agentes são cegos. não é "feature de integração" — é pré-condição de tudo.

o mercado de ERPs de PDV no varejo multimarca brasileiro é extremamente fragmentado. dezenas de sistemas regionais, nenhum padrão, qualidade técnica variável. a teceo precisa de uma estratégia de parceria que funcione em escala sem virar empresa de integração.

### dois modelos de integração

**modelo ativo — teceo faz a integração.**

ERPs grandes e estratégicos: Linx Microvix, TOTVS, e similares. mercado relevante, concentração alta de lojistas no canal multimarcas e em redes de franquias/lojas próprias. a teceo investe no desenvolvimento e mantém controle de ponta a ponta: venda pro lojista, implantação, suporte.

por que fazer: esses ERPs cobrem fatia significativa do mercado que importa. controlar a experiência garante qualidade do dado e do onboarding. o custo de desenvolvimento é finito e o benefício é multiplicado por toda a base de lojistas naquele ERP.

status atual: 1 integração ativa (Linx Microvix).

**modelo passivo — teceo expõe API, parceiro integra.**

ERPs pequenos e regionais: Objetiva, Informezz, e dezenas de outros. mercado extremamente fragmentado — impossível a teceo integrar cada um. a teceo expõe uma API padronizada com dois fluxos: sell-in teceo → PDV (catálogo normalizado, pedidos confirmados, status de entrega) e sell-out PDV → teceo (vendas ao consumidor, estoque, giro por SKU).

o parceiro (ERP) desenvolve a integração do lado dele. a teceo fornece documentação, sandbox, suporte técnico e homologação.

por que fazer: escala. o canal multimarcas tem centenas de ERPs regionais. se cada um integrar via API padronizada, a teceo ganha cobertura sem custo de desenvolvimento proporcional. em teoria, esse modelo escala melhor que o ativo — mas depende do parceiro querer integrar.

status atual: 2 integrações passivas rodando (Objetiva, Informezz).

### critério: quando ativo, quando passivo

a decisão é por **porte + relevância estratégica** do ERP.

| critério | ativo (teceo faz) | passivo (parceiro faz) |
|---|---|---|
| porte do ERP | grande, concentração alta de mercado | pequeno/regional, fragmentado |
| relevância estratégica | alto — destranca canal inteiro ou segmento | médio/baixo — soma volume incremental |
| investimento teceo | alto (dev + manutenção + suporte) | baixo (API + docs + homologação) |
| controle da experiência | total | parcial (depende da qualidade do parceiro) |
| escalabilidade | limitada (1 por vez) | alta (N parceiros em paralelo) |

zona cinzenta: ERPs de porte médio com relevância regional forte. caso a caso — pode começar passivo e migrar pra ativo se volume justificar.

### proposta de valor pro ERP parceiro

o ERP precisa querer integrar. a teceo é, pra ele, a porta de entrada de tudo que os clientes dele compram. o pitch tem 3 pilares:

**1. sell-in enriquecido pros clientes dele.** o lojista que usa aquele ERP passa a receber catálogo normalizado das marcas direto no sistema — sem cadastro manual. isso mata uma das maiores dores operacionais do varejo multimarca. o ERP que oferece isso se diferencia de qualquer concorrente que não tem. é feature competitiva que o ERP não precisou desenvolver.

**2. revenue share sobre receita de lojista.** o lojista que entra no teceo para lojistas (ferramenta de compras e, no futuro, b2b2c) gera receita recorrente. a teceo compartilha essa receita com o ERP homologado que investiu na integração — independente de quem trouxe o lojista (o ERP, a marca, ou a teceo direto). o ERP que integrou e viabilizou o fluxo técnico ganha participação na receita.

**3. possibilidade de indicações de lojistas.** a teceo pode indicar lojistas pro ERP parceiro. quando a teceo traz uma marca que precisa ativar sell-out e os lojistas dela não têm ERP ou usam algo precário, a teceo pode direcionar esses lojistas pro ERP homologado que já tem a integração pronta. pra ERPs pequenos e regionais, que atendem lojistas SMB e não têm como ir atrás de marcas grandes, isso é lead qualificado caindo no colo. ciclo virtuoso: quanto mais ERPs homologados, mais fácil ativar sell-out de novas marcas; quanto mais marcas na teceo, mais lojistas precisam de ERP integrado.

### modelo financeiro

ninguém paga ninguém pela integração. é parceria ganha-ganha: a teceo ganha dados de sell-out e cobertura de mercado. o ERP ganha feature competitiva (sell-in enriquecido), revenue share e indicações. o custo de cada lado é o investimento de desenvolvimento, que se paga com o benefício recorrente.

### programa de homologação: "teceo certified PDV"

**precisa ser criado.** a visão:

processo de homologação em 3 etapas:

1. **técnica** — integração funcional nos dois fluxos (sell-in → PDV e sell-out → PDV → teceo). testes automatizados contra sandbox. validação de qualidade do dado: catálogo chegando limpo, sell-out voltando completo e padronizado. SLA mínimo de uptime e latência.

2. **operacional** — capacidade de suporte ao lojista no onboarding da integração. documentação interna do parceiro. ponto de contato técnico dedicado.

3. **selo** — ERP aprovado recebe selo "teceo certified PDV" com tier (starter, certified, strategic). selo visível pro lojista no teceo para lojistas. tier define nível de revenue share e prioridade de suporte.

| tier | critério | benefícios |
|---|---|---|
| starter | integração funcional, testes passando | selo básico, revenue share base, documentação |
| certified | + SLA comprovado, + suporte ao lojista, + volume mínimo de lojas | revenue share maior, co-marketing, prioridade no suporte |
| strategic | parceiro ativo de alto volume ou relevância de mercado (Linx, TOTVS) | revenue share premium, planejamento conjunto, acesso antecipado a APIs novas |

**status:** programa não formalizado ainda. precisa definir: critérios exatos por tier, % de revenue share por tier, SLAs mínimos, processo de recertificação, e governança (quem decide promoção/rebaixamento de tier).

### o ERP como parte da comunidade

esses ERPs não são fornecedores — são parceiros do ecossistema. a teceo é, pra eles, o hub que torna o produto deles mais valioso pro lojista. a estratégia de comunidade (seção 15) se aplica aqui: parceiros de integração participam do collection, têm acesso ao índice, e ganham visibilidade dentro da rede.

o flywheel: ERP integra → lojistas ganham sell-in enriquecido → sell-out flui pro data layer → índice melhora → mais marcas querem sell-out → mais lojistas precisam integrar → ERP homologado se diferencia → mais ERPs querem integrar.

### desafios e riscos

| risco | mitigação |
|---|---|
| ERP pequeno não tem capacidade técnica pra integrar | documentação clara, sandbox, suporte técnico na homologação. starter tier com requisitos mínimos |
| ERP não vê valor o suficiente pra investir | revenue share + sell-in enriquecido como argumento. começar com design partners que já sentem a dor |
| qualidade do dado varia muito entre ERPs | homologação valida qualidade. tier starter aceita mínimo viável, tiers superiores exigem mais |
| virar empresa de integração | modelo passivo é o default. ativo só pra ERPs estratégicos. framing interno: integração é meio, dados são fim |
| duplicação no ERP (de/para pós-cadastro) | desafio técnico atual. resolver é pré-condição pra escalar — tanto no ativo quanto no passivo |
| revenue share cria dependência do ERP | o valor do teceo pro lojista não depende do ERP. se ERP sai, lojista continua. revenue share é incentivo, não dependência |

### sequencing

1. **agora** — consolidar as 3 integrações existentes (Linx Microvix ativa, Objetiva e Informezz passivas). coletar aprendizados de qualidade de dado, onboarding e manutenção.
2. **próximo** — formalizar programa de homologação (critérios, tiers, revenue share). documentação e sandbox públicos. abordar 3-5 ERPs regionais relevantes no canal multimarcas.
3. **depois** — escalar modelo passivo com programa estruturado. expandir integrações ativas pra TOTVS e outros ERPs enterprise relevantes pra franquias e lojas próprias.

---

## 6. API-first, UI-second

mudança mental central da v2: produto principal não é "a plataforma que o comprador usa" — é "a infraestrutura que o agente do comprador consulta".

**catálogo v2:** 4 camadas de acesso (disponibilidade → brand → acesso → navegação) + camada de agent metadata: atributos estruturados, métricas de performance, compatibilidade entre produtos.

**OTB engine:** wizard progressivo pra humanos + API pro agente. "dado meu OTB de R$ 180K, distribui nas categorias X, Y, Z respeitando min/max por marca e giro histórico" = uma chamada de API. funciona tanto pra multimarcas (OTB de compras) quanto pra lojas próprias (OTB de distribuição/alocação).

**MCP server:** tools cobrindo ciclo completo — consultar catálogo, sell-out, sell-through, montar pedido, enviar pedido, comparar performance, sugestão de reposição. conexão via OAuth, agente externo vira copiloto comercial.

**webhooks:** eventos em tempo real — pedido confirmado, estoque atualizado, nova coleção, threshold de reposição.

---

## 7. agentes: cenários concretos

### representante — "preciso bater minha meta"

rep faltando R$ 200k pra meta. agente puxa performance, mapeia clientes com gap, analisa categorias subdimensionadas, busca best sellers não comprados, cruza com índice teceo + sell-out, monta pedido sugerido com racional completo pra abordagem.

resultado: rep mediano vira tão bom quanto o melhor rep. rep bom vira sobre-humano. agente potencializa com dados que nenhum humano processa sozinho.

### representante — "não preciso mais de 4 prepostos"

rep que hoje gerencia 4 prepostos pra cobrir uma região. agente cuida de reposição automática, pedidos sugeridos, follow-up pós-venda, alertas de estoque. rep reduz de 4 prepostos pra 1 (ou zero), com cobertura igual ou melhor. economia de R$ 20-30K/mês. o que sobra vira investimento em abertura de mercado e venda consultiva — ou margem.

### admin da marca — "como tá meu canal?"

diretora comercial recebe resumo semanal: sell-in, sell-out, giro por categoria, oportunidades (lojistas que não compraram cápsula), riscos (estoque zerado, pedidos pendentes), recomendações de ação.

cenários complementares: collection intelligence (brief quantitativo pra coleção futura), gestão de reps (performance comparativa), monitoramento de canal em tempo real.

### lojista multimarcas — "preciso comprar a coleção"

OTB inteligente baseado em histórico e benchmark → seleção de marcas/sortimento (experiência unificada independente do cenário de integração) → comparação por categoria, não por marca → execução (pedido na teceo, via sistema da marca, ou planejamento manual). cadastro automático no recebimento. reposição preditiva. análise de performance com benchmarks.

### gerente de loja própria — "o que mandar pra cada loja?"

agente analisa sell-through por loja, estoque atual, perfil de cliente da região, sazonalidade, e sugere alocação por loja. cruza com inteligência de rede (lojas parecidas no data layer). "manda mais vestido longo P&B P1/P2 pra loja do Morumbi porque o sell-through de lojas com perfil parecido na rede tá disparando nos últimos 60 dias." nenhum ERP entrega isso.

### captura de valor: teceo vs. provider de modelo

anthropic (compute): ~2-3% do valor (~R$ 5-20 por interação). teceo (dados + transação): ~97-98%. modelo é commodity, dados proprietários são o moat.

### catálogo de agentes: duas categorias

os agentes se dividem em duas categorias com lógicas de valor (e pricing) diferentes:

**agentes que agem** — geram receita ou evitam perda diretamente:

| agente | o que faz | persona principal |
|---|---|---|
| reposição | sugere pedidos de reposição automática baseado em sell-out e giro | rep, lojista |
| quebra | scoring de risco por produto na hora do pedido, sugere substituições pra reduzir encalhe | rep |
| devolução | gestão inteligente de devoluções — triagem, roteamento, decisão | marca, lojista |
| sortimento | monta grade ideal por loja baseado em perfil, sazonalidade e benchmark da rede | rep, lojista, gerente de loja |

**inteligência que informa** — melhora decisão sem executar diretamente:

| produto | o que faz | persona principal |
|---|---|---|
| índice teceo | benchmark de mercado: sell-through por categoria, preço médio, performance comparada, sazonalidade | marca, rep, lojista |
| analytics premium | drill-down avançado, relatórios customizados, collection intelligence | marca, rep |
| MCP server | acesso à teceo via claude/agentes externos — rep usa inteligência sem abrir a plataforma | rep |

**cada persona consome o mesmo dado por um motivo diferente:** marca compara performance vs mercado pra ajustar estratégia. lojista decide OTB da próxima coleção baseado em quais marcas performam acima do índice. rep usa ranking da carteira vs média do mercado pra argumentar com diretor comercial.

---

## 8. níveis de autonomia

| nível | rep/gerente faz | teceo faz | tempo operacional |
|-------|---------|-----------|-------------------|
| 1 — ferramentas (hoje) | tudo, com ferramenta melhor | digitaliza processo | ~80% |
| 2 — sugestões | curadoria + fechamento | monta sugestão com dados | ~50% |
| 3 — execução automática | venda consultiva + abertura | executa reposição e básico | ~20% |
| 4 — rede autônoma | estratégia + relacionamento | distribuição programática | ~5% |

**princípio:** cada nível não reduz o número de reps — muda o que fazem. o bom rep vale mais a cada nível. na loja própria, o princípio é o mesmo: cada nível libera o time de planejamento pra pensar em mix e posicionamento, não em alocação operacional.

---

## 9. o representante: de usuário a cliente

### premissa

agente + rep, nunca agente vs. rep. a plateia da teceo é de marcas. se a narrativa parecer que agente elimina rep, a sala se fecha.

### o que mudou

o manual v1 tratava o rep como extensão da marca — um usuário do showroom. a realidade é mais complexa: o rep é um empresário independente que atende múltiplas marcas, gerencia prepostos, controla comissões, administra mostruários e cobre regiões. ele tem dores próprias que a marca não resolve e o software da marca não endereça.

a constatação central: **o rep é um cliente da teceo, não apenas um usuário.** a marca paga pela tranquilidade operacional do canal B2B. o rep paga pelo que amplifica o negócio dele — analytics, agentes, gestão, inteligência de rede.

### as 5 dores do rep

1. **controle de comissões** — quanto ganha por marca, por período, reconciliação com faturamento
2. **gestão do negócio** — agenda, pipeline, financeiro, carteira por preposto (pros maiores, funciona como mini-empresa)
3. **controle de mostruário** — rastreamento de amostras por marca, logística de envio/devolução
4. **gestão da região** — mapa de oportunidades e cobertura territorial, whitespace analysis
5. **CRM do escritório** — relacionamento com lojistas, follow-up, pós-venda básico

### rep como entidade na rede

o rep deixa de ser cadastro dentro da brand e vira entidade de primeira classe na rede teceo. marca vincula o rep; rep gerencia seus próprios usuários e prepostos. o ambiente do rep é cross-brand — ele vê todas as marcas que atende num lugar só.

implicação técnica: gestão de usuários do showroom migra pro rep. a marca não cadastra o preposto do JOMA. o JOMA cadastra os prepostos dele. a marca só vincula o rep à brand.

### a economia do preposto

o mercado de prepostos está em crise. reps e marcas reclamam da mesma coisa: mão de obra escassa, prepostos envelhecendo, novos não querem ir pra estrada. um preposto bom custa R$ 10K+/mês entre fixo e variável. rep médio tem 3-4 prepostos.

proposta de valor: a teceo + agentes podem reduzir de 3-4 prepostos pra 0-1, com cobertura igual ou melhor. economia de R$ 20-30K/mês por rep. se desses R$ 20-30K o rep paga R$ 1-5K pra teceo, a conta fecha com sobra.

### o rep como acelerador de aquisição

quando o rep paga e depende da teceo, ele vira aliado na venda pra marca. rep que já usa a teceo pra outra marca pressiona as marcas que ainda não estão na plataforma. 40 reps de uma marca grande enchendo o saco do diretor comercial é muito mais poderoso que o time de aquisição da teceo ligando.

isso não é um terceiro flywheel separado (rep não existe sem marca), mas é um acelerador potente do brand-push: reps satisfeitos → pressão bottom-up nas marcas → marca adota → mais reps satisfeitos.

### sell-out sustentável

às vezes o dado mostra que a loja não precisa comprar mais agora. não empurra. lojista não afoga, não devolve, não para de comprar. vende de forma sustentável = carteira mais saudável.

### visão de longo prazo: distribuição como serviço

marcas que querem entrar no B2B mas não têm canal (D2C que nunca vendeu wholesale, marcas envelhecendo com reps aposentando). a teceo pode evoluir pra resolver a distribuição da marca por completo — conecta marca com rep qualificado da região, entrega toda infraestrutura (ferramenta, agentes, inteligência de rede), cobra fee maior sobre a operação (ex: 8-10% do sell-in, com repasse ao rep).

o modelo funciona pros dois lados: a marca não quer administrar rep, quer que alguém resolva o canal pra ela. o rep quer acesso a marcas novas e complementares pro portfólio. a teceo homologa os dois — qualifica o rep, qualifica a marca, faz o match, e opera a infraestrutura embaixo. funciona especialmente bem com marcas menores e/ou com pouca/zero experiência no canal multimarcas.

**regra inviolável:** a teceo nunca assume meta de venda. nunca vira responsável pelo resultado comercial de uma região. é infraestrutura que qualifica e conecta — tipo Amazon/Mercado Livre pro vendedor. se a teceo tiver meta de uma marca específica, perde neutralidade da rede e cria conflito com todas as outras marcas. isso é inegociável.

---

## 10. o conflito de servir marcas concorrentes

a teceo não vende "marcas" ao lojista — vende "categorias." o agente diz "sua loja precisa de R$ 8K em bermudas masculinas" e mostra opções ranqueadas por performance. decisão final é do lojista. teceo é a prateleira, não vendedor de marca específica.

**governança:** sell-in da marca A nunca informa venda de marca B. recomendação vem de sell-out do lojista + dados de mercado agregados. monetiza via visibilidade premium (marca paga destaque dentro da categoria, tipo Amazon Sponsored Products).

**a mesma governança se aplica à distribuição como serviço:** se o rep atende marcas concorrentes, a teceo não pode favorecer nenhuma. o rep decide como distribui seu esforço — a teceo fornece dados e ferramentas neutras.

---

## 11. os 3 canais: multimarcas, franquias e lojas próprias

### multimarcas

lojista compra de 10-30 marcas sem dados unificados. teceo pode virar o canal — agente de compras do lojista, agente de vendas da marca. take rate de 5-10% faz sentido nas pontas do mercado.

**trade-off pro data layer:** sell-out de multimarcas é o mais valioso — uma loja informa 10-15 marcas ao mesmo tempo. efeito multiplicador máximo. mas é o mais difícil de capturar (ERPs fragmentados, cadastro caótico).

### franquias

franqueadora já é o canal. teceo entrega eficiência operacional (reposição, grade, sell-out). SaaS + dados. contas previsíveis, fonte de sell-out limpo.

**trade-off pro data layer:** sell-out limpo e padronizado, mas monomarca — informa só aquela marca. efeito multiplicador menor que multimarcas, mas dado de alta qualidade.

### lojas próprias

marca opera as lojas diretamente. teceo entrega inteligência de OTB e distribuição — o que o ERP promete e não cumpre. produto adjacente ao commerce que compartilha o data layer.

**trade-off pro data layer:** dado mais limpo de todos (ERP padronizado, marca controla 100%). sell-out de lojas próprias alimenta padrões de demanda — categorias, localizações, faixas de preço, sazonalidade — que servem qualquer marca na rede. e o dado tende a ser mais limpo: a distribuição é mais deliberada, sem distorção de rep ou condição comercial, refletindo demanda real com menos ruído. o efeito multiplicador direto é menor que o de multimarcas, mas a qualidade do sinal e o volume em escala contribuem significativamente ao índice.

**o incentivo de consolidação:** marca que traz todos os canais pra teceo consolida volume na tabela progressiva, melhora fee unitário, e a inteligência de rede fica mais rica pra ela. sell-out de loja própria + sell-out de franquias + sell-in de multimarcas = visão completa do canal. ninguém mais oferece isso.

### sequencing entre canais

multimarcas como motor de receita da v1 + território de expansão pro data layer. franquias como base de receita + sell-out limpo. lojas próprias como upsell natural pra marcas que já são clientes nos outros canais. grandes multimarcas como aceleradores do data layer via retailer-pull.

---

## 12. estratégia de AI: sequenciamento

**fase 1 — MCP leve (agora).** 5-10 tools essenciais expostos via remote MCP server. power users testam via Claude/agentes externos. validação barata, aprendizado alto.

**fase 2 — agentes embedados (Q2-Q3 2026).** 2-3 agentes nativos: sortimento, replenishment, performance. alimentados pelo índice + dados individuais. controlam experiência, monetizam como add-on de consumo, capturam dados de interação. agentes do rep (gestão de carteira, sugestão de abordagem) entram nessa fase.

**fase 3 — agent-to-agent commerce (Q4 2026+).** agente do comprador + agente da marca transacionando programaticamente. teceo como clearing house.

**embedado = produto principal** (controle, monetização, dados ficam dentro). **MCP = stickiness** (power users puxam dados pra workflows deles, teceo vira source of truth).

---

## 13. o moat na era dos agentes

agente pessoal do comprador precisa de dados pra recomendar sortimento. sem sell-out, é cego. teceo é a única com dados cruzados sell-in + sell-out em escala no mercado de moda brasileiro. cada transação alimenta o agente de todos. competidor que queira replicar precisa de anos de dados transacionais reais — não dá pra comprar ou sintetizar.

a cobertura de todos os canais amplifica o moat: quem tem sell-in de multimarcas + sell-out de franquias + dados de distribuição de lojas próprias tem uma visão do mercado que ninguém consegue montar de fora.

SaaSpocalypse é aliado: se IA commoditiza software, quem tem dados proprietários + rede vira mais valioso. foundation model é commodity, agente vertical com dados exclusivos é moat.

**risco existencial:** se a teceo demorar e alguém construir camada de agente que conecta direto com APIs dos ERPs, perde posição. a defesa: ninguém tem dados cruzados da rede. a janela está aberta agora.

---

# GTM

---

## 14. os flywheels de crescimento

### flywheel 1 — brand-push (original)

marca adota commerce → sell-in entra → marca empurra "teceo para lojistas" → varejista integra ERP → sell-out entra → dados cruzados → índice melhora → agentes mais inteligentes → mais marcas.

**limitação:** depende da marca adotar o commerce. funciona pra marcas M/G. não funciona pra enterprise GG (Nike, Adidas) que já têm plataformas.

**acelerador: rep como pressão bottom-up.** quando reps já usam a teceo por outras marcas e pagam por add-ons, eles pressionam as marcas que ainda não estão na plataforma. 40 reps de uma marca grande exigindo migração pro diretor comercial é mais eficaz que qualquer pitch de vendas. o rep vira aliado de aquisição.

### flywheel 2 — retailer-pull (novo)

grande varejista adota teceo como hub de compras → teceo integra com sistemas das marcas → catálogo normalizado criado → desbloqueia sell-out em toda a rede → teceo vai na marca com sell-out de centenas de PDVs → marca paga por inteligência → marca considera commerce → mais varejistas entram.

**efeito multiplicador:** quando Afeet (220 lojas, maior buyer Nike BR) gera catálogo normalizado de Nike, benefício não é 220 lojas — são 220 + todas multimarcas da base que vendem Nike. pode ser 500, 800 lojas. dado já existia, faltava a chave de decodificação.

### upsell de loja própria

marca que já é cliente de multimarcas/franquias → oferecer loja própria como expansão natural. mesma tabela progressiva (volume consolida), mesma inteligência de rede, novo canal gerando dados. pipeline de upsell previsível: mapear clientes e prospects com operação significativa de lojas próprias.

juntos cobrem o mercado inteiro. brand-push é motor de receita da v1. retailer-pull é acelerador do data layer da v2. loja própria é upsell natural que enriquece ambos.

---

## 15. comunidade — estratégia de growth

### por que comunidade

o mercado de moda B2B já é uma comunidade — diretor comercial da marca A almoça com o da B, lojista de curitiba indica ferramenta pro de BH. melhor canal de aquisição não é ads nem outbound — é a rede de relações que já existe. a teceo só precisa ser o centro gravitacional.

**três razões:** (1) v1 → v2 exige mudança de percepção, não deck de vendas. (2) data layer depende de mais marcas + lojistas + sell-out — comunidade cria pull. (3) CAC cai, LTV sobe via referral orgânico e lock-in de pertencimento.

**o norte:** a teceo não é empresa de software com comunidade. é comunidade do mercado de moda que tem uma plataforma.

### os 5 pilares

**1. collection (eventos presenciais de alto impacto)**

carro-chefe. evento semestral alinhado ao ciclo de coleção. 50-80 convidados (c-level de marcas, compradores, lideranças). 1 dia inteiro. manhã: painel de dados/tendências alimentado pelo data layer. tarde: mesas redondas por tema. noite: networking. cada edição com tema-âncora conectado à narrativa v2.

posiciona teceo como hub intelectual, cria FOMO legítimo, dados apresentados SÃO o produto, gera conteúdo pra 6 meses. cadência: 2x/ano.

arco narrativo padrão em 4 atos: o mundo mudou (contexto macro) → diagnóstico honesto (cliente faz a ponte) → o framework (3 camadas: dados → inteligência → ação) → o convite (problema de rede, solução coletiva).

**2. academy (educação como canal de aquisição)**

mercado não entende OTB, sell-through, sortimento orientado a dados. se não entende, não compra. academy educa, gera autoridade, cria pipeline.

3 camadas: conteúdo aberto (vídeos curtos, topo de funil, 2x/semana), programas estruturados (workshops 2-4h, meio de funil, 20-30 leads por turma), certificação (programa 4-6 semanas, fundo de funil, stickiness).

**3. rede digital (tecido conectivo diário)**

espaço curado com regras e valor recorrente. whatsapp communities com canais por perfil e tema. conteúdo recorrente: flash report semanal (micro-dose do teceo index), caso da semana, AMA mensal com líder de mercado.

**4. parcerias e ecossistema**

parceiros de integração (ERPs — cada um integrado = mais sell-out; programa detalhado na seção 5), parceiros de conteúdo/educação (consultorias, professores), parceiros de serviço (agências de buying, consultorias de VM), parceiros financeiros (fintechs de crédito B2B — pré-techfin), parceiros de mídia.

modelo: "teceo certified partner" com tiers (starter, certified, strategic).

**5. teceo index (dados como produto comunitário)**

o pilar que conecta tudo. relatório trimestral/semestral com inteligência agregada da rede: sell-through por categoria/região/faixa de preço, tendências sell-in vs. sell-out, gaps oferta/demanda, benchmarks por perfil de loja.

3 níveis de acesso: aberto (headlines), comunidade (report completo), premium (dados customizados, dashboard interativo — produto de dados da v2).

o teceo index é o que faz a comunidade girar. sem ele, é grupo de networking. com ele, é rede de inteligência.

### flywheel da comunidade

mais membros → mais dados na rede → index mais rico → mais gente quer o index → mais gente entra → mais sell-out integrado → v2 mais valiosa → comunidade mais relevante → mais membros.

### como comunidade conecta com v2

collection é onde index é apresentado → valida demanda por dados. academy educa em OTB/sell-through → prepara terreno pra agentes. rede digital mantém engajamento → reforça teceo = inteligência. parcerias ampliam integração → mais sell-out. **index É a v2 em formato de report** — quando vira dashboard interativo, transição já aconteceu.

---

## 16. hierarquia de canais

### pra marca (sell-side): zero mídia paga

SOM são ~250 grupos M/G/GG. as que importam a teceo já sabe quem são. narrativa da v2 não cabe em anúncio. 100% comunidade + ativação direta + referral. account-based tudo.

### pra lojista (buy-side): marca como canal primário

motor de aquisição: marca/rep empurrando "teceo para lojistas". mídia paga só como amplificador de conteúdo educacional (academy), nunca anúncio de conversão.

### pra rep: produto como canal

rep entra porque a marca que ele atende adota a teceo. descoberta do ambiente próprio + add-ons é orgânica. à medida que mais marcas do portfólio dele entram, o valor do ambiente cross-brand aumenta e ele se torna pagante. o rep satisfeito vira canal de aquisição reverso — pressiona marcas que ainda não estão.

### marca como distribuição

cada marca cliente tem 50-500 lojistas. se ativa "teceo para lojistas" pra rede: (1) melhora experiência do cliente (cadastro automático no ERP), (2) ganha visibilidade de sell-out. investimento certo é em ferramentas/incentivos pra marca fazer essa ativação.

| canal | pra marca | pra lojista | pra rep |
|-------|-----------|-------------|---------|
| comunidade | canal primário (100%) | awareness + educação | awareness |
| ativação direta | complemento ABM (250 contas) | não escalável | — |
| marca como distribuição | — | **canal primário de aquisição** | **canal primário** (entra via marca) |
| mídia paga | zero | amplificador de conteúdo | zero |
| referral orgânico | forte na comunidade | forte na rede | forte (rep indica pra marca) |

sequência: comunidade posiciona → marca distribui (pro lojista e pro rep) → academy educa → mídia amplifica o que funciona.

---

# PRICING

---

## 17. modelo de cobrança

### estrutura geral

**assinatura (aquisição) + add-ons de consumo (expansão).** uma única lógica para as 3 personas — marca, rep, lojista. ACVs diferentes, estrutura igual.

assinatura = fee mensal. ancora o compromisso, garante receita previsível (GRR). consumo = motor real de receita. cresce proporcional ao uso e ao sucesso do cliente (NRR).

**proporção shopify:** assinatura é piso baixo, receita real vem do consumo. referência: shopify cobra $39/mês mas faz dinheiro em payments, capital, apps (subscription solutions ~25%, merchant solutions ~75%).

### princípio: quem compra o quê

a marca compra **tranquilidade operacional** — a segurança de que o canal B2B e a distribuição rodam sem dor de cabeça. o decisor da marca (diretor comercial, CEO) muitas vezes nunca abriu a teceo — especialmente nas marcas grandes onde decisor e admin são pessoas diferentes. o admin (time comercial, gerentes) usa e muito o dia a dia. quem usa o sistema diariamente é o rep, o franqueado, o gerente de loja. o decisor quer paz.

implicação: cobrar caro da marca por coisas que o rep e o lojista usam é a razão dos descontos absurdos de 70-90% em marcas grandes. o modelo correto: cobrar da marca um preço justo pela infraestrutura core, e monetizar o valor incremental via quem realmente se beneficia (rep, lojista, agentes).

### as 3 personas pagam

| persona | assinatura (fee mensal) | consumo (motor de crescimento) |
|---|---|---|
| marca | maior — core da plataforma (showroom, pedidos, gestão comercial, portal do lojista) | volume de pedidos/GMV, agentes, índice, analytics premium, sell-out |
| rep | pequeno — suficiente pra gerar comprometimento, baixo o bastante pra não ser barreira | proporcional à carteira e ao uso de agentes/inteligência |
| lojista | pequeno — mesma lógica do rep | proporcional ao uso de inteligência (OTB, reposição, analytics, índice) |

**por que cobrar fee dos 3:** quem paga trata diferente de quem usa de graça. filtra quem é sério. e o custo é baixo o suficiente pra não ser barreira de entrada no network.

**lógica de alinhamento:** rep vendendo mais = pagando mais = feliz porque tá ganhando mais. lojista comprando melhor = pagando mais = feliz porque tá lucrando mais. a expansão da conta da marca cresce conforme ela ativa mais lojistas e reps na plataforma.

### assinatura core da marca: tabela progressiva sobre volume

a teceo vende uma assinatura dimensionada pelo volume de pedidos/ordens finalizados na plataforma. tabela progressiva tipo imposto de renda — cada faixa de volume tem seu fee, o acumulado é proporcional:

| faixa de vendas | fee |
|-----------------|-----|
| até R$ 5M | 0,30% |
| de R$ 5M a R$ 20M | 0,25% |
| de R$ 20M a R$ 100M | 0,20% |
| de R$ 100M a R$ 500M | 0,15% |
| acima de R$ 500M | 0,10% |

exemplo: marca de R$ 2B de sell-in → anual acumulado de R$ 2,3M → com negociação pode chegar a ~R$ 1,6M/ano → R$ 135K/mês → fee médio efetivo de 0,08%.

**modelo unificado:** mesma tabela pra todos os canais (multimarcas, franquias, lojas próprias). sem separação por canal. marca que traz mais canais consolida volume, sobe de faixa, melhora fee unitário. incentivo de consolidação natural.

**base de cálculo pra loja própria:** não existe "preço de sell-in" na distribuição interna. duas opções em avaliação: (A) preço de custo da mercadoria distribuída (dado limpo, volume em custo é ~40-50% do varejo — cai numa faixa adequada); (B) percentual do preço de varejo como proxy. decisão pendente.

**mecânica:** voucher antecipado. marca paga parcelado mensal com base no volume projetado (últimos 12 meses). reconciliação anual. comunicação lidera com valor mensal, não fee %. *mecânica de reconciliação a ser aprofundada em momento dedicado de pricing.*

### add-ons de consumo: duas categorias

além do core, a teceo oferece produtos complementares metrificados por uso — lógica de consumo. incluso na assinatura até um limite; acima, paga por uso. referência mental: modelo de tokens do Claude (assinatura dá direito a um limite, excedente é consumo).

**agentes que agem** — geram receita ou evitam perda diretamente:

| agente | o que faz | persona principal |
|---|---|---|
| reposição | sugere pedidos de reposição automática baseado em sell-out | rep, lojista |
| quebra | scoring de risco por produto na hora do pedido, sugere substituições | rep |
| devolução | gestão inteligente de devoluções | marca, lojista |
| sortimento | monta grade ideal por loja baseado em perfil, benchmark da rede | rep, lojista, gerente de loja |

**inteligência que informa** — melhora decisão sem executar diretamente:

| produto | o que faz | persona principal |
|---|---|---|
| índice teceo | benchmark de mercado: sell-through por categoria, preço médio, performance comparada | marca, rep, lojista |
| analytics premium | drill-down avançado, relatórios customizados, collection intelligence | marca, rep |
| MCP server | acesso à teceo via claude/agentes externos | rep |

**cada persona consome o mesmo dado por um motivo diferente:** marca compara performance vs mercado pra ajustar estratégia. lojista decide OTB da próxima coleção baseado em quais marcas performam acima do índice. rep usa ranking da carteira vs média do mercado pra argumentar com diretor comercial.

### mecânica do "gostinho"

cada fee mensal inclui um uso X de agentes e inteligência embutido no contrato. suficiente pra criar hábito e o momento de "caralho, isso funciona". apertado o bastante pra sentir falta quando acaba.

passou de X → cobra consumo extra.

a expansão é pull, não push. ninguém precisa vender upsell — o próprio uso vende.

**calibragem do threshold é o ponto mais sensível do modelo.** baixo demais = nickel-and-diming antes do cara virar fã. alto demais = inteligência de graça pra quem nunca converte.

### modelos de pricing dos add-ons

**quando o agente gera receita** (reposição, cross-sell, sugestão de compra): cobrar **% do GMV gerado**. é comissão sobre venda que não existiria sem o agente. reposição: 2-3% do GMV da venda criada. escala infinitamente com o sucesso. alinhamento total: todo mundo ganha (marca vende mais, lojista repõe sem atrito, rep ganha comissão sem esforço, teceo leva %).

**quando o agente evita perda ou melhora decisão** (quebra, sortimento, OTB, índice): cobrar **por uso** — por pedido analisado, por consulta, por relatório. o valor tá no acesso à inteligência, não no resultado pontual. não se esgota (sempre vai ter próxima coleção, próximo pedido). evita o paradoxo do success fee: agente eficaz demais mata a própria receita.

**exemplo do agente de quebra:** o valor real não é "redução de quebra" — é inteligência de sortimento em tempo real. enquadrar como scoring de risco por produto, não como success fee sobre quebra evitada.

**alternativa: consumo unificado (créditos).** cada ação de agente consome X créditos. fee mensal vem com N créditos inclusos. vantagens: evita 6 modelos de pricing pra 6 agentes, lançar agente novo = definir créditos sem mexer no contrato, simplicidade operacional e de comunicação. riscos: pode ficar abstrato demais, usuário pode não entender o que tá pagando, precisa de "rótulo" visível por tipo de uso. **status: ambos os modelos (por agente vs unificado) podem funcionar. precisa testar.**

### a conta do rep

exemplo concreto: Tommy (marca de R$ 500M, ~40 reps).

- modelo antigo: proposta de R$ 40K/mês rejeitada (marca paga R$ 4K no concorrente)
- modelo novo: Tommy paga ~R$ 25-30K/mês pela assinatura core (0,1% do sell-in, aceitável)
- 40 reps pagando R$ 1-5K/mês cada em add-ons de consumo = R$ 40-200K/mês
- receita total da conta: R$ 65-230K/mês vs. R$ 40K/mês que a marca rejeitou

a tabela progressiva resolve a objeção de preço da marca. os add-ons de consumo do rep são receita incremental que não existia no modelo anterior.

### divisão comercial

assinatura core = responsabilidade da área de aquisição. add-ons de consumo = responsabilidade da área de expansão. divisão clara de responsabilidade e técnica de venda.

**GTM motion proporcional ao ACV:** ACV da marca justifica medium/high touch. ACV do rep/lojista pede low touch/PLG. o produto tem que vender sozinho pro rep e pro lojista — se precisar de vendedor, não escala.

### renovação

automática com reajuste por índice (IGPM/IPCA). revisão só com trigger material: volume cresceu 20-30%, novo canal, add-on novo, produto v2 relevante. semântica: não é "renovação" — é "expansão."

### risco: imprevisibilidade de custos

modelo de consumo pode gerar imprevisibilidade pro cliente — alguém aperta um botão errado no ERP e sincroniza 1M de produtos, estoura o custo. mitigações: caps mensais configuráveis, alertas de consumo, tiers com ceiling, dashboard de uso em tempo real. o produto tem que ser bom o suficiente pra justificar o uso — se o cliente não usa, não paga, e a receita não vem. isso força qualidade.

### decisões em aberto

- threshold do uso incluso no fee (o "X" do gostinho) — por persona
- pricing específico de cada agente vs modelo unificado de créditos
- como comunicar consumo pro usuário sem parecer "taxa sobre operação"
- precificação do índice teceo (por consulta? por tier de profundidade? incluído em plano premium?)
- MCP: cobrar acesso ou cobrar uso? (acesso = assinatura; uso = consumo)
- reconciliação: mensal, trimestral, ou por coleção?

---

## 18. caminho de monetização v1 → v2

| horizonte | fonte de receita | fee efetivo |
|-----------|-----------------|-------------|
| agora (Y1-Y3) | assinatura core (marca) + primeiros add-ons de consumo | 0,10–0,20% |
| médio prazo (Y4-Y6) | + add-ons de rep + sell-out e índice como produtos de dados + loja própria como upsell | receita incremental significativa |
| longo prazo (Y7+) | + agentes autônomos + distribuição como serviço + distribuição programática | 0,5–1%+ |

curva total de ARR pode ser igual ou maior que BP projeta, mas composição muda: menos assinatura core pura, mais add-ons de consumo + dados + inteligência.

### camadas de receita

**assinatura core (marca):** tabela progressiva sobre volume. todos os canais. cresce e financia tudo.

**assinatura core (rep):** fee mensal pequeno. ancora comprometimento, viabiliza acesso ao ambiente cross-brand e agentes básicos.

**assinatura core (lojista):** fee mensal pequeno. ancora comprometimento, viabiliza hub de compras e inteligência básica.

**add-ons de consumo (marca):** analytics premium, collection intelligence, integração ERP avançada. metrificados por uso.

**add-ons de consumo (rep):** analytics cross-brand, gestão de prepostos, agentes de venda, inteligência de rede. metrificados por uso. potencial de ser maior que a assinatura da marca em contas com muitos reps.

**add-ons de consumo (lojista):** inteligência de compra, benchmarks, agentes de reposição e OTB. fee + consumo.

**dados/índice:** add-on pra marcas (+0,1-0,2% GMV), assinatura pra não-clientes (R$ 5-20K/mês), licenciamento.

**visibilidade premium (ads B2B):** posicionamento de prateleira baseado em dados dentro da experiência de compra.

**teceo para lojistas:** fee mensal baixo no core. monetização real via add-ons de consumo e sell-out gerado.

**distribuição como serviço (visão):** fee sobre operação de marcas que contratam canal completo via teceo (8-10% do sell-in via rep homologado, com repasse ao rep). mercado potencial: marcas D2C entrando no wholesale + marcas tradicionais com rede de reps envelhecendo + marcas menores sem experiência no canal.

**longo prazo:** revenue share sobre vendas incrementais. take rate acompanha autonomia: 0,1-0,3% → 1-2% → 5-10% (distribuição autônoma nas pontas do mercado).

### flywheel de dados do consumo

o consumo dos agentes pelo rep gera dado de sell-in que alimenta a inteligência da marca. a marca paga pelo analytics premium e pelo sell-out. os dados que o rep gera usando os agentes tornam o produto da marca melhor.

cada consulta ao índice retroalimenta o índice — o dado fica melhor com o uso.

**cada persona consumindo melhora o produto da outra.** é o closed-loop aplicado ao produto, não só ao GTM. índice teceo é o exemplo perfeito: depende de dados agregados de toda a rede. quanto mais gente na plataforma, mais valioso fica. network effect monetizado diretamente.

### alinhamento com revenue architecture

| conceito (jacco/WbD) | aplicação teceo |
|---|---|
| arco ownership → subscription → consumption | modelo híbrido subscription + consumption |
| recurring revenue = recurring impact | agentes entregam impact a cada uso; sem impact, sem consumo, sem receita |
| acquisition → retention → expansion (3 steps) | assinatura = acquisition; fee recorrente = retention; consumo crescente = expansion |
| NRR como motor de growth pós $10M ARR | consumo de agentes + índice é o vetor de NRR |
| closed-loop system | consumo retroalimenta dados que melhoram o produto que gera mais consumo |
| nonlinearity / marginal gains | cada agente novo é vetor de expansion sem mexer no contrato base |
| GTM motion proporcional ao ACV | ACV da marca justifica medium/high touch; ACV do rep/lojista pede low touch/PLG |

---

# FINANCIALS

---

## 19. números atuais (jun/25)

| métrica | valor |
|---------|-------|
| clientes ativos | 51 marcas |
| GMV anualizado | R$ 2,3B |
| ARR total | R$ 4,2M (commerce R$ 3,7M + add-ons R$ 0,5M) |
| MRR total | R$ 351K |
| fee médio | 0,18% GMV |
| ARPA mensal | R$ 6.891 |
| CAC total | R$ 41.667 |
| payback | 6 meses |
| LTV | R$ 360K |
| LTV/CAC | 8,7x |
| gross margin | 71% |
| logo churn mensal | 4,0% |
| NRR mensal | 99,6% |
| time | 42 pessoas |

### evolução

| | dez/21 | dez/22 | dez/23 | dez/24 | jun/25 |
|---|--------|--------|--------|--------|--------|
| clientes | 2 | 8 | 24 | 43 | 51 |
| GMV anualizado (R$ mi) | 47 | 67 | 564 | 1.138 | 2.344 |
| ARR (R$ mi) | 0,13 | 0,23 | 0,91 | 2,54 | 4,22 |

---

## 20. metas e projeções

### metas 2027 (BP 2 anos)

**objetivo 1 — crescer com eficiência:** ARR v1 de R$ 4,7M → R$ 16,2M (3,4x). burn máximo 0,8 em 2026, 0,2 em 2027.

**objetivo 2 — validar v2:** R$ 2,1M ARR marca (dados/IA) + R$ 1,8M ARR lojista + receita de rep (add-ons) = R$ 3,9M+ receita nova. total ~R$ 20M ARR = gatilho série A com v2 funcionando.

### projeções long-term

| ano | Y1 | Y5 | Y10 | Y15 |
|-----|------|------|-------|-------|
| clientes | 2 | 49 | 402 | 1.250+ |
| GMV (R$ bi) | 0,05 | 3,55 | 23,0 | 30,0 |
| ARR total (R$ mi) | 0,08 | 4,83 | 150,9 | 467,5 |
| fee total | 0,15% | 0,14% | 0,66% | 1,56% |

Y15 de 1.250+ clientes inclui expansão pra marcas P/PP e potencialmente lifestyle — coerente com SAM de R$ 90B+ em moda e R$ 120B em lifestyle.

v2 (lojista + marca + rep) começa no Y7 e representa a maior parte do ARR no longo prazo.

### estratégia de fundraising

seed R$ 5M (ABSeed) captado. série A quando provar v2 com receita real (~R$ 20M ARR). valuation esperada R$ 200-300M a 10-15x ARR. tese: vender execução, não promessa.

---

# EXECUÇÃO

---

## 21. estrutura de times

### produto

commerce, CRM, retail ("teceo para lojistas" + ambiente do rep), core arq, core xp, analytics, dados, IA, integrações.

nota: ambiente do rep começa dentro do squad de retail, sem squad separado. se demanda crescer, quebra em squad próprio.

### GTM

marketing, aquisição (assinatura core), expansão (add-ons de consumo), CS, suporte, sustentação.

*nota: estrutura de GTM com mais detalhes pendentes de atualização. áreas de marketing, vendas (aquisição/expansão) e CS (suporte/sustentação/CS) em reorganização.*

### apoio

admin, RH, CEO.

---

## 22. OKRs 1S26

### produto

| squad | objetivo |
|-------|----------|
| commerce | melhorar experiência de apresentação de coleção + automatizar workflow de pedido |
| CRM | otimizar pré-venda |
| retail | teceo vendável para o lojista + primeira versão do ambiente do rep |
| core arq | destravar complexidade enterprise |
| core xp | facilitar acesso à teceo |
| analytics | recriar experiência de analytics |
| dados | construir fundação de dados |
| IA | (re)criar a Rachel |
| integrações | validar tese de integração de sell-out |

### GTM

| squad | objetivo |
|-------|----------|
| marketing | tangibilizar construção da comunidade |
| aquisição | vender pra (muito) mais marcas |
| expansão | engatilhar upsell (add-ons + loja própria) |
| CS | reter marcas satisfeitas |
| suporte | automatizar suporte N1 |

### apoio

RH: montar time pra v2. CEO: redefinir produtividade com IA.

---

## 23. entregáveis até o collection inverno 27

tudo abaixo é meta pra entregar até o próximo collection (inverno 27):

- **UI v2** — nova interface da plataforma
- **analytics v2** — experiência de analytics recriada
- **teceo para lojistas** — produto vendável pro varejista
- **teceo para reps** — ambiente próprio do representante
- **agente / MCP** — primeiros agentes e MCP server funcional
- **índice teceo (v0)** — primeira versão do índice de moda
- **academy** — primeiros conteúdos e programas educacionais
- **docs** — documentação pública da plataforma

---

## 24. sequenciamento da comunidade

### Q1-Q2 2026 (fundação)

1. collection verão 27 como evento fundador (mar/26)
2. primeiro teceo index (v1, dados disponíveis hoje)
3. primeiros 10 vídeos da academy
4. lançar rede digital com 50-100 membros seed
5. definir 3-5 parceiros piloto

### Q3-Q4 2026 (escala)

collection inverno 27. index v2. primeiro workshop da academy. rede com 300-500 membros. partner program com 10+ parceiros.

### 2027 (maturidade)

collection como evento de referência (100+). index como produto de receita (premium pago). academy com certificação. comunidade como principal canal (>30% novos clientes). agent commerce showcase no collection.

### investimento estimado

R$ 155-285K/semestre. referência: CAC atual ~R$ 42K/cliente. se comunidade gera 10 clientes por semestre via referral, já paga investimento. efeito composto de marca e retenção é onde mora o real ROI.

### métricas-alvo

| métrica | baseline | meta Q4 2026 | meta 2027 |
|---------|----------|--------------|-----------|
| membros total | 0 | 300-500 | 1.000+ |
| leads academy | 0 | 200 | 500+ |
| % novos clientes via comunidade | 0% | 10-15% | 30%+ |
| deals influenciados | 0 | 15-20 | 40+ |

---

## 25. roadmap geral

### fase 1 — fundação (agora → 18 meses)

commerce v1 crescendo 2-3x. "teceo para lojistas" em rollout. ambiente do rep v1 (entidade própria, analytics cross-brand, gestão de prepostos). sell-out estabilizando. primeiro case de loja própria (Loftystyle). design partners validando retailer-pull. primeiros catálogos normalizados enterprise. MCP leve (5-10 tools). agentes v1 (sugestões). consolidação data layer. comunidade lançada. tabela progressiva de pricing implementada. primeiros add-ons de consumo.

### fase 2 — aceleração (18 → 36 meses)

índice como produto vendável. agentes semi-autônomos (incluindo agentes do rep). loja própria como produto consolidado e canal de upsell. retailer-pull escalando. sell-out desbloqueado via catálogos normalizados. first revenue de dados pra enterprise. receita de add-ons de rep representativa. collection intelligence v1. série A.

### fase 3 — dominância (36 → 60 meses)

rede autônoma: agent-to-agent commerce. teceo como clearing house. distribuição como serviço. intelligence marketplace. distribuição direta em todos os canais. techfin.

---

## 26. riscos e mitigações

### riscos do vetor retailer-pull

| risco | mitigação |
|-------|-----------|
| integração sem cooperação da marca | começar onde varejista tem leverage real (Afeet = maior buyer Nike BR) |
| qualidade dos dados menor | funciona pra visão consolidada e OTB. agent metadata completo como upgrade futuro |
| custo operacional alto por integração | custo cai após primeiras marcas. benefício multiplica pela rede |
| virar empresa de integração | framing interno: integração é meio, dados são fim |
| escopo excessivo com design partners | escopo fechado no piloto: 3-5 marcas, 20-30 lojas |

### riscos do rep como cliente

| risco | mitigação |
|-------|-----------|
| rep não acostumado a pagar por software | começar gratuito/freemium, monetizar quando valor é percebido. economia de prepostos é o argumento |
| rep atende marcas fora da teceo e experiência é fragmentada | valor cresce com mais marcas na plataforma. rep vira aliado de aquisição |
| marca sente que teceo está "do lado do rep" | comunicação clara: marca é a cliente core, rep é extensão do produto |
| distribuição como serviço cria conflito de neutralidade | teceo nunca assume meta de venda de marca específica. é infraestrutura, não vendedor |

### riscos de loja própria

| risco | mitigação |
|-------|-----------|
| produto adjacente, não idêntico — UX e integrações diferentes | roadmap dedicado dentro do squad de retail. compartilha data layer, não necessariamente UI. produto de inteligência de distribuição de primeira classe é pré-requisito |
| competição com ferramentas especializadas (OneBeat, Analyticalways) | vantagem de inteligência de rede cross-brand que ninguém mais tem. complementar onde necessário |
| base de cálculo de volume indefinida (custo vs. % varejo) | definir com primeiro case (Loftystyle) e validar com 2-3 marcas adicionais |

### riscos do modelo de consumo

| risco | mitigação |
|-------|-----------|
| imprevisibilidade de custos pro cliente | caps mensais, alertas de consumo, tiers com ceiling |
| produto não bom o suficiente pra justificar uso recorrente | consumo força qualidade — se cliente não usa, receita não vem. é feature, não bug |
| metrificação difícil (como medir "uso" de cada add-on?) | começar com métricas simples e óbvias. refinar com dados reais de uso |
| calibragem do threshold do "gostinho" | baixo demais = nickel-and-diming antes do cara virar fã. alto demais = inteligência de graça pra quem nunca converte. testar por persona |
| paradoxo do success fee (agente eficaz mata a receita) | enquadrar como inteligência contínua (scoring, sortimento), não como success fee sobre resultado pontual |

### riscos da comunidade

| risco | mitigação |
|-------|-----------|
| grupo morto | community lead dedicado + calendário editorial rígido primeiros 6 meses |
| marcas concorrentes não dividem espaço | governança clara (nada individual), temas de mercado |
| lojista sente "evento de marca" | 40-50% convidados sendo lojistas/compradores |
| conteúdo genérico | teceo index é o diferencial — dados exclusivos |
| custo sem ROI | medir pipeline influenciado desde dia 1, tag "comunidade" no CRM |

### risco existencial

se alguém construir camada de agente conectando direto com APIs de ERPs sem a teceo no meio, perde posição. defesa: ninguém tem dados cruzados da rede. mas se dados ficarem trancados numa UI que só humanos acessam enquanto mundo migra pra agentes, a janela fecha.

---

## 27. referências de mercado

**NuOrder / Lightspeed:** wholesale buying. inverteu com retailer-pull (Nordstrom, Saks). 4.000+ marcas, 100.000+ varejistas. "Order Trends" = inteligência agregada.

**Palantir:** enterprises pagam por "outcome machines" autônomas em dados exclusivos. pricing por valor, não seat.

**Faire:** marketplace B2B. sugere com base em sell-out, net-60. ~$1B+ GMV/mês.

**Shopify:** referência de modelo de receita. começou cobrando assinatura (subscription solutions ~25% da receita), mas a maior parte do faturamento vem de merchant solutions (~75%) — pagamentos, capital, apps, serviços que monetizam o GMV. em 2025, ~R$ 60B de receita sobre ~R$ 2T de GMV. a lógica é: assinatura barata traz o merchant, consumo sobre a atividade econômica é o motor de crescimento. paralelo com a teceo: assinatura core justa pra marca (como o plano Shopify), add-ons de consumo sobre a atividade (como merchant solutions) são o upside real. shopify cresce receita 30%+ ao ano nessa composição, com merchant solutions crescendo mais rápido (37%) que subscriptions (17%).

**Toast (benchmarking):** referência pro teceo index. Toast é infraestrutura de restaurantes (POS + pagamentos + gestão) com 156k+ locais. construiu produto de benchmarking que usa dados agregados e anonimizados da rede pra oferecer inteligência comparativa: o restaurante compara vendas, volume, pricing e tendências de menu contra peers filtrados por localização, tipo e tamanho. lançou também o Menu Price Monitor — dados públicos de precificação por item alimentados pela rede. usa IA pra classificar itens de menu em categorias padronizadas e agregar comparações. paralelo direto: teceo faz o mesmo com moda — classifica produtos em categorias padronizadas (via catálogo normalizado), agrega dados transacionais da rede, e entrega benchmarks pra cada participante. Toast prova que "dados da rede como produto" funciona em vertical SaaS com base transacional grande.

**B3:** clearing house de transações com regras, liquidação e dados. modelo mental correto pra teceo v2.

**Amazon/Mercado Livre:** marketplace que qualifica vendedores, entrega infraestrutura, mas não vende diretamente. modelo mental correto pra distribuição como serviço.

**OneBeat:** plataforma israelense de otimização de estoque com IA. decisões granulares e diárias de alocação e reposição. $15M levantados (2025). clientes: Calvin Klein, Panasonic, Aramis. presença em LATAM/EMEA/APAC. referência pra profundidade de produto de distribuição inteligente.

**Analyticalways:** espanhola, 150+ marcas em 15 países. parceria com Linx no brasil. cobre planejamento de coleção, OTB, alocação inicial, reposição e liquidação. produto ROIvolution. referência pra inteligência de distribuição end-to-end em moda.

---

## 28. a decisão estratégica central

a teceo v2 não é evolução incremental. é mudança de natureza: de plataforma de vendas para **infraestrutura de dados e distribuição de moda, em todos os canais.**

data layer é o ativo. commerce (v1), teceo para lojistas e distribuição de loja própria são canais de ingestão. agentes são interface de entrega. comunidade é o veículo de posicionamento e rede. o rep é cliente e aliado de aquisição. três vetores complementares alimentam o data layer: brand-push (motor de receita), retailer-pull (acelerador), e consolidação de canais (lojas próprias como enriquecedor).

o modelo de receita reflete essa mudança: assinatura + consumo pras 3 personas (marca, rep, lojista). assinatura core justa pra marca (tabela progressiva), fee mensal baixo pro rep e lojista (comprometimento sem barreira), e add-ons de consumo pra quem usa (agentes que agem cobram % do GMV gerado, inteligência que informa cobra por uso). a composição de ARR muda ao longo do tempo — menos fee de commerce puro, mais consumo + dados + inteligência. cada persona consumindo melhora o produto da outra — closed-loop onde o uso retroalimenta os dados que melhoram os agentes que geram mais uso.

o mercado é maior do que parecia: R$ 133B de sell-in formal só em moda (TAM), R$ 90B endereçável (SAM), R$ 30B no SOM imediato com ~250 grupos M/G/GG. lifestyle adiciona R$ 202B de TAM como mercado adjacente. a teceo tem 2,3B de GMV — ~7,7% do SOM. espaço enorme pra crescer antes de precisar expandir.

ignorar retailer-pull = marcas GG inacessíveis. ignorar loja própria = R$ 8B de upside no chão. ignorar o rep como cliente = receita na mesa que fica no chão. ignorar comunidade = reposicionamento impossível. a janela está aberta agora. quem construir a infraestrutura de distribuição inteligente primeiro vira o protocolo padrão.
