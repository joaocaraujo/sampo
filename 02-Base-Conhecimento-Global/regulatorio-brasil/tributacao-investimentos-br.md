# Tributação de Investimentos no Brasil — Renda Fixa, Fundos, Isentos, FGC e Renda Variável

> **Documento canônico — Sampo**
> Escopo: tabela regressiva, come-cotas, atentes isentos (LCI/LCA/CRI/CRA/debêntures), FGC e renda variável PF.
> **Vigência dos dados: 2026** (última revisão: 23/10/2026).
> Fontes primárias: Lei 11.033/2004, Decreto 6.558/2008 (IOF), Lei 12.431/2011, Resolução CMN 5.118/2024, Lei 14.754/2023, Lei 13.259/2016, Lei 7.958/1989 (FGC).

---

## 1. Tributação Regressiva de Renda Fixa e Fundos

### 1.1 Tabela regressiva de IR — renda fixa e fundos (Lei 11.033/2004)

| Prazo da aplicação | Alíquota de IR |
|---|---|
| Até **180 dias** | **22,5%** |
| De **181 a 360 dias** | **20,0%** |
| De **361 a 720 dias** | **17,5%** |
| Acima de **720 dias** | **15,0%** |

### 1.2 Base de incidência

- Incide **exclusivamente sobre o rendimento nominal auferido** — **nunca sobre o principal**.
- Recolhimento: na fonte, no resgate/vencimento (e no come-cotas para fundos — §2).
- Fundos de renda fixa, multimercados e ações (exceto day trade, §5) seguem a regressiva; a "tabela progressiva anual" antiga só vale para aplicações anteriores a 2004 (contratos legados).

### 1.3 IOF — tabela decrescente (Decreto 6.558/2008 e alterações)

| Dia da aplicação | Alíquota de IOF sobre o rendimento |
|---|---|
| **D1** | **96%** (máximo prático — desestimula resgate imediato) |
| D2 a D29 | Decrescente diariamente (alíquota por dia, tabela do decreto) |
| **D30 em diante** | **0% — isenção total** |

> 📌 **Regra prática:** qualquer resgate em renda fixa antes do 30º dia perde quase todo o rendimento em IOF. Liquidez de verdade começa no D30.

---

## 2. Mecanismo do Come-Cotas em Fundos de Investimento

### 2.1 Alíquotas antecipadas

| Perfil do fundo | Prazo médio de vencimento da carteira | Alíquota do come-cotas |
|---|---|---|
| **Curto prazo** | ≤ **365 dias** | **20%** |
| **Longo prazo** | > **365 dias** | **15%** |

### 2.2 Periodicidade de recolhimento

- **Semestral**: último dia útil de **maio** e de **novembro** de cada ano.
- Recolhe IR sobre os rendimentos acumulados desde o último come-cotas (ou desde a compra, se mais recente).

### 2.3 Ajuste no resgate

```
IR final no resgate = Rendimento × Alíquota da tabela regressiva (conforme prazo)
Ajuste a pagar      = Max(0, IR final − IR já recolhido pelo come-cotas)
```

- Se o prazo total passar de 720 dias → alíquota final 15% < 20% (come-cotas curto) → **há devolução/redução no cálculo final** (o ajuste zera; perda é o imposto antecipado remunerado pelo Tesouro até o resgate).
- Se prazo < 180 dias → 22,5% > 20% → complementa 2,5 p.p. no resgate.

### 2.4 Impacto na composição de juros

| Instrumento | Tratamento do IR | Efeito de juros compostos |
|---|---|---|
| **Título de resgate único** (CDB, LCI pós-carência, Tesouro) | Imposto só no vencimento/resgate | **Juros compostos plenos** sobre o principal + rendimento |
| **Fundo com come-cotas** | IR antecipado semestralmente retira caixa do fundo | **Erosão do efeito compost** — capital tributado "cede" antes de render de novo; perda acumulada cresce com o tempo e o prazo médio da carteira |

> 🔴 **Alerta:** para horizonte longo, a diferença entre títulos de resgate único e fundos com come-cotas pode superar **1 p.p. a.a. de retorno líquido equivalente**. Simular sempre.

---

## 3. Ativos Isentos de Imposto de Renda para Pessoa Física

### 3.1 Universo de isentos (comprar somente na emissão primária)

| Ativo | Emissor | Lei | Natureza |
|---|---|---|---|
| **LCI** — Letra de Crédito Imobiliário | Bancos | Lei 9.514/1997 | Crédito imobiliário |
| **LCA** — Letra de Crédito do Agronegócio | Bancos | Lei 11.076/2004 | Agronegócio |
| **CRI** — Certificado de Recebíveis Imobiliários | Securitizadoras | Lei 9.514/1997 | Crédito imobiliário (não bancário) |
| **CRA** — Certificado de Recebíveis do Agronegócio | Securitizadoras | Lei 11.076/2004 | Agronegócio (não bancário) |
| **Debêntures Incentivadas** | Empresas (infra) | **Lei 12.431/2011** | Infraestrutura (concessões) |

> ⚠️ Isenção vale para **PF residente no Brasil**, na **emissão primária**. Revenda no mercado secundário: ganho de capital tributado (15%, §5).

### 3.2 Regras de emissão e prazos mínimos de carência (Resolução CMN 5.118/2024)

| Ativo | Carência mínima | Efeito da carência |
|---|---|---|
| **LCI** | **12 meses** | Sem liquidez sem perda de isenção / descumprimento da regra de carência do emissor |
| **LCA** | **9 meses** | Idem |
| CRI / CRA | Carência típica conforme edital (via estruturação; sem carência legal fixa universal — verificar cada emissão) | — |
| Debêntures incentivadas | Prazo conforme edital (geralmente longo, 3–5+ anos) | — |

> 📌 A Resolução CMN 5.118/2024 encerrou a "liquidez diária" artificial de LCI/LCA: para o emissor honrar os prazos regulatórios, o investidor precisa manter o papel no mínimo o período de carência.

### 3.3 Fórmula de equivalência — isento vs. tributado

Para comparar uma LCI/LCA isenta com um CDB/Tesouro tributado na tabela regressiva:

```
Taxa Equivalente (tributada) = Taxa Isenta ÷ (1 − Alíquota IR projetada)
```

**Exemplos (taxa isenta = 13,0% a.a.):**

| Alíquota IR projetada (pelo prazo) | Taxa tributada equivalente |
|---|---|
| 22,5% (≤ 180 dias) | 13,0% ÷ 0,775 = **16,77% a.a.** |
| 20,0% (181–360 dias) | 13,0% ÷ 0,800 = **16,25% a.a.** |
| 17,5% (361–720 dias) | 13,0% ÷ 0,825 = **15,76% a.a.** |
| 15,0% (> 720 dias) | 13,0% ÷ 0,850 = **15,29% a.a.** |

**Regra inversa** (achar a taxa isenta mínima que empata um CDB de 16% a.a. com IR de 15%):

```
Taxa Isenta mínima = Taxa Tributada × (1 − Alíquota IR)
                   = 16,0% × 0,85 = 13,6% a.a.
```

> 📌 Use sempre a alíquota do **seu prazo real de permanência** — errar o prazo é o erro mais comum na comparação.

---

## 4. Diretrizes e Limites do FGC (Fundo Garantidor de Créditos)

Base: Lei 7.958/1989; Lei 12.703/2012 (teto de R$ 1 milhão/quadriênio).

### 4.1 Limites de cobertura

| Limite | Valor | Detalhe |
|---|---|---|
| **Cobertura padrão** | **Até R$ 250.000,00** | **Por CPF/CNPJ por conglomerado financeiro** — engloba **principal + juros** acumulados até a data da intervenção/liquidação |
| **Teto global quadrienal** | **R$ 1.000.000,00** | Máximo somado de pagamentos do FGC a cada **4 anos consecutivos** por CPF/CNPJ |

### 4.2 Instrumentos cobertos × não cobertos

| ✅ **Cobertos pelo FGC** | ❌ **NÃO cobertos** |
|---|---|
| Conta corrente | **Títulos Públicos Federais** (Tesouro Direto — risco soberano 100% União; não há FGC porque não há risco de banco) |
| Depósito a prazo (**CDB, RDB**) | **Debêntures** (inclui incentivadas) |
| Poupança | **Fundos de investimento** (regulados CVM) |
| **LCI** e **LCA** | **Letras Financeiras (LF)** |
| | **CRIs e CRAs** (securitizadoras não são bancos) |

> 📌 **Correção comum:** CDB e LCI/LCA de bancos são cobertos (R$ 250 mil/banco); CRI/CRA e debêntures **não** — o risco é de crédito puro do emissor. Diversificar emissores é a mitigação.

### 4.3 Exemplo prático de cobertura

| Papel | Banco A | Banco A (acumulado) | Efeito |
|---|---|---|---|
| CDB R$ 200k + LCI R$ 80k | R$ 280k | R$ 280k | Cobertos até R$ 250k; **R$ 30k perdidos** em caso de falência |

---

## 5. Regras Básicas de Renda Variável para Pessoa Física

### 5.1 Ações — Swing Trade (posições com prazo > D+2)

| Regra | Detalhe |
|---|---|
| **Isenção** | Alienações **mensais** com total de vendas **até R$ 20.000,00** → **isentas de IR** (Lei 11.033/2004, art. 23) |
| **Acima do limite** | **15%** sobre o **ganho de capital líquido** (vendas − custo de aquisição) das operações do mês — incidindo sobre o **total** do ganho quando o limite for ultrapassado |
| Base | Preço de venda − (preço de compra + corretagem/emolumentos) |
| Dedução de perdas | **Compensação limitada**: perdas de operações comuns limitadas aos ganhos do mesmo mês/ano-calendário (regras da IN RFB 1.585/2015) |

> ⚠️ O limite de R$ 20 mil é **por mês-calendário, somando todas as vendas de ações à vista** (não por lote nem por ativo). Excediu no mês → todo o ganho do mês fica tributado.

### 5.2 Day Trade (compra e venda no mesmo pregão)

| Regra | Detalhe |
|---|---|
| **Alíquota** | **20%** sobre **qualquer lucro líquido** |
| **Isenção de R$ 20 mil** | **NÃO se aplica** |
| Recolhimento | DARF até o último dia útil do 2º mês subsequente ao da operação (código 6015) |

### 5.3 Fundos Imobiliários (FIIs) — Lei 14.754/2023

| Rendimento | Tratamento (desde 2024) |
|---|---|
| **Dividendos / rendimentos de aluguel** | **Isentos de IR para PF** — se observados os **critérios legais** (distribuição de, no mínimo, 95% dos lucros tributáveis; mais de 50 cotistas; não ser "FII de destino" com concentração vedada, etc.) |
| **Ganho de capital na alienação de cotas** | **20% fixos** sobre o ganho — **sem isenção de R$ 20 mil** |
| Recolhimento ganho FII | DARF até o último dia útil do mês seguinte ao da venda (código 6015) |

> ⚠️ **Alerta:** o FII perdeu a isenção de ganho de capital que ações têm — FII é instrumento de **renda (dividendos isentos)**, não de swing trade. Day trade em FII segue 20%.

---

## 6. Tabela-Resumo Geral (referência rápida)

| Ativo | IR | Alíquota | Isenção R$ 20k | FGC |
|---|---|---|---|---|
| CDB / RDB / DP | Regressiva | 15–22,5% (+IOF <30d) | — | ✅ 250k/banco |
| Tesouro Direto | Regressiva | 15–22,5% | — | ❌ (risco União) |
| LCI / LCA | **Isento** (pós-carência 12/9m) | 0% | — | ✅ (bancos) |
| CRI / CRA / Deb. incentivada | **Isento** | 0% | — | ❌ |
| Fundo RF/multimercado | Regressiva + **come-cotas** | 15/20% antecipado | — | ❌ |
| Ações (swing) | Regressiva | 15% acima de R$ 20k/mês | ✅ | ❌ |
| Day trade | — | 20% sempre | ❌ | ❌ |
| FII cotas | Ganho | 20% | ❌ | ❌ |
| FII dividendos | **Isento** (critérios Lei 14.754/2023) | 0% | — | ❌ |

---

## 7. Fontes e Referências Datadas

| Fonte | Conteúdo | Data |
|---|---|---|
| Lei 11.033/2004 | Tabela regressiva; isenção R$ 20k ações | Vigente |
| Decreto 6.558/2008 (+ alterações) | IOF decrescente (96% D1 → 0% D30) | Vigente (2025: IOF sobre câmbio/exteriores — não afeta renda fixa doméstica) |
| Lei 12.431/2011 | Debêntures de infraestrutura isentas | Vigente |
| Resolução CMN 5.118/2024 | Carência mínima LCI 12m / LCA 9m | 2024 |
| Lei 14.754/2023 | FII: dividendos isentos sob critérios; ganho 20% | Efeito 2024+ |
| Lei 13.259/2016 | Alíquota progressiva ganho de capital (15–22,5%) | Vigente |
| Lei 7.958/1989; Lei 12.703/2012 | FGC: R$ 250k/ conglomerado; teto R$ 1 mi/4 anos | Vigente |
| IN RFB 1.585/2015 | Operações comuns x day trade; compensação de perdas | Vigente |

> **Nota de manutenção:** alíquotas de IOF, tabelas do FGC e regras CMN têm alterações frequentes. Conferir BCB/CVM/Receita antes de decisões de grande porte.
