# Mecânica dos Consórcios no Brasil — Estrutura Legal, Custo Real e Armadilhas

> **Documento canônico — Sampo**
> Escopo: composição matemática da parcela, atualização monetária, formas de contemplação, armadilha do lance embutido, regras de desistência/cancelamento e comparação quantitativa consórcio × SAC × Investimento.
> **Vigência dos dados: 2026** (última revisão: 23/10/2026).
> Fontes primárias: Lei nº 11.795/2008 (Lei do Consórcio), Resolução CMN nº 3.919/2020, Tema 312 do STJ (REsp 1.599.511, j. 26/08/2020).

---

## 1. Estrutura Jurídica e Composição da Parcela

### 1.1 Natureza jurídica

O consórcio **não é crédito**: é **comunhão de pessoas e recursos** (Lei 11.795/2008, art. 2º) formada para aquisição coletiva de bens, **sem incidência de juros** sobre o preço do bem, administrada por empresa autorizada e fiscalizada pelo **Banco Central do Brasil (BCB)**.

| Elemento | Regra |
|---|---|
| Gestora | Administradora de consórcios autorizada/registrada no BCB (Res. CMN 3.919/2020) |
| Grupo | Prazo fixo (em meses), carta de crédito unitária, valor nominal total fixado na constituição |
| Contraprestação | Parcelas periódicas compostas por FC + TA + FR (+ seguro, se contratado) |
| Contrato | Regido pela Lei 11.795/2008; controvérsias de adesão pós-2009 subordinadas ao Tema 312/STJ (§4) |

### 1.2 Decomposição matemática da parcela

Definições:

- `C` = valor nominal da carta de crédito (preço do bem no "mês zero", sem indexação)
- `n` = número de meses do grupo
- `TA%` = taxa de administração total (% de C, diluída no prazo ou antecipada)
- `FR%` = fundo de reserva total (% de C)
- `S` = prêmio mensal do seguro (prestamista / quebra de garantia), se aplicável

**Componentes (parcela-base do mês 1, antes da primeira indexação):**

| Componente | Fórmula | Natureza | Destino do valor |
|---|---|---|---|
| **Fundo Comum (FC)** | `FC = C / n` | Amortização real do bem — percentual fixo do valor do grupo pago por todos os membros a cada mês | Forma o caixa que paga a carta dos contemplados |
| **Taxa de Administração (TA)** | `TA_mensal = (C × TA%) / n` (linear) | Remuneração da administradora | Receita da administradora — **não** amortiza o bem |
| **Fundo de Reserva (FR)** | `FR_mensal = (C × FR%) / n` | Colchão coletivo contra inadimplência do grupo | Reserva do grupo; **saldo devolvido proporcionalmente** ao encerramento (Lei 11.795/2008, art. 30 e arts. 26–27) |
| **Seguro** | `S` (fixo ou % da parcela) | Proteção a terceiros (banco/imobiliária/consolidadora, conforme uso do bem) | Seguradora — **facultativo por lei**, ainda que vendido como “obrigatório” na adesão |

**Parcela-base:**

```
Parcela₁ = (C / n) × (1 + TA% + FR%) + S
```

**Exemplo decomposto** — Carta C = R$ 300.000,00 · n = 200 meses · TA 18% (linear) · FR 2% · sem seguro:

| Componente | Cálculo | Valor (R$) | % da parcela |
|---|---|---:|---:|
| FC | 300.000 / 200 | 1.500,00 | 83,3% |
| TA | (300.000 × 0,18) / 200 | 270,00 | 15,0% |
| FR | (300.000 × 0,02) / 200 | 30,00 | 1,7% |
| **Parcela-base** | | **1.800,00** | **100%** |

### 1.3 Linear × antecipada (taxa de adesão)

| Modalidade | Quando cobra | Efeito no custo efetivo |
|---|---|---|
| **Linear** | Diluída em n parcelas iguais (ex.: 18% / 200) | Custo menor em valor presente — TA paga ao longo do tempo |
| **Antecipada / adesão** | Percentual alto cobrado nas primeiras parcelas (ex.: 20–30% nos 3–6 primeiros meses) | **Custo efetivo muito superior** — mesmo valor nominal, PV muito maior; infla o CEC (§1.4) |

### 1.4 A falácia do “sem juros”: Custo Efetivo do Consórcio (CEC)

O consórcio **não cobra juros sobre o saldo devedor**, mas cobra **TA + FR + seguro + perda de liquidez**. A soma desses custos constitui **custo financeiro real** — a taxa de desconto que iguala os fluxos de pagamento ao valor do bem recebido (VPL = 0).

**Fórmula do CEC (taxa mensal `i` tal que):**

```
0 = Bem_recebido_t  −  Σ_{k=1..t} Parcela_k / (1+i)^k  −  Σ_{k=t+1..n} Parcela_k / (1+i)^k
```

Ou, na prática de comparação de mercado (aproximação de taxa equivalente):

```
CEC ≈ TAXA_EQUIVALENTE que justifica pagar (TA% + FR% + Seguro_total%)
      sobre C durante n meses, em troca de receber o bem com atraso aleatório (contemplação)
```

> ⚠️ **Regra prática:** TA de 18–25% linear em 120–240 meses equivale, em média, a **~8% a 14% a.a. de custo efetivo** apenas nos encargos fixos — antes de contar indexação e custo de oportunidade da espera. Consórcio “sem juros” **não** é financiamento gratuito; é **financiamento com taxa embutida não rotulada**.

---

## 2. Mecânica de Atualização Monetária — O Efeito Gangorra

### 2.1 Indexadores legais por tipo de bem

| Tipo de consórcio | Indexador típico da carta/saldo | Base |
|---|---|---|
| **Imobiliário** (imóvel pronto, terreno, construção) | **INCC-DI** (imóveis prontos/terrenos); **CUB/CUB-Brasil** (construção por administração) | Variação acumulada mês a mês, divulgada pela CFI/BCB |
| **Veículos** | **IGP-M**, **IPCA** ou **Tabela FIPE** (conforme contrato) | Escolhido na constituição do grupo; monitorar qual foi pactuado |
| Demais bens | Índices pactuados (IPCA, IGP-M, etc.) | Contrato |

### 2.2 Efeito gangorra — por que a parcela sobe para sempre

A regra central (Lei 11.795/2008 + praxe regulatória):

> **Toda reajustada da carta de crédito pelo índice reajusta, na mesma proporção, o saldo devedor remanescente de TODOS os consorciados** — contemplados e não contemplados.

Consequências:

1. **Grupo inteiro:** `C_t = C₀ × Π(1 + índice_k)` — a base de FC, TA e FR mensais é recalculada sobre a carta reajustada.
2. **Contemplado:** recebe o bem no mês `t` (com o valor já reajustado), **mas continua pagando parcelas reajustadas até o fim do grupo** — o FC remanescente amortiza o “saldo” da carta já entregue; TA e FR seguem incidindo sobre a base reajustada.
3. **Não contemplado:** paga parcelas crescentes sem ter o bem — o grupo financia os contemplados, e a espera prolonga a exposição à indexação.

**Simulação da parcela sob gangorra** (mesmo grupo do §1.2, INCC 4,0% a.a. composto):

| Ano | Parcela-base reajustada (R$) | Δ vs. mês 1 |
|---|---:|---:|
| 0 | 1.800,00 | — |
| 5 | 2.190,00 | +21,7% |
| 10 | 2.660,00 | +47,8% |
| 15 | 3.230,00 | +79,4% |
| 16,7 (encerramento) | 3.470,00 | +92,8% |

> ⚠️ **Alerta:** o “consórcio sem juros” tem **parcela com juros compostos do índice** — em ciclos inflacionários altos (ex.: 2021–2022, INCC > 10% a.a.), a parcela de imobiliários praticamente **dobra em 7–8 anos**, mesmo para quem já recebeu o imóvel.

---

## 3. Formas de Contemplação e a Armadilha do Lance Embutido

### 3.1 Sorteio — probabilidade estatística

Assembleia ordinária mensal (Lei 11.795/2008, art. 30). Contemplação por sorteio:

```
P(sorteio mensal) = 1 / n_participantes_ativos
P(não contemplado em N meses) = (1 − p)^N
```

**Exemplo:** grupo com 200 cotas ativas — `p = 0,5%` ao mês. Tempo mediano até sorteio ≈ `ln(2) / p` ≈ **138 meses (~11,5 anos)**. Em 5 anos, probabilidade acumulada de sorteio ≈ `1 − (0,995)^60` ≈ **26%** — ou seja, **~74% de chance de ainda não ter o bem**.

### 3.2 Lance livre (com recursos próprios)

O consorciado oferta **capital próprio** (não vem da carta) para antecipar a contemplação. Custo de oportunidade: o capital desmobilizado à vista deixa de compor a carteira do consorciado — comparar sempre com a rentabilidade alternativa (CDI, IPCA+) do mesmo período.

### 3.3 Lance embutido (armadilha de custo)

**Mecanismo:** o consorciado ofertá **parte da própria carta** como lance (ex.: 30%). A administradora contempla com o saldo **líquido** da carta, mas **cobra a TA sobre o valor NOMINAL integral**.

**Exemplo prático (aritmética da distorção):**

| Item | Cálculo | Valor (R$) |
|---|---|---:|
| Carta nominal | C | 300.000,00 |
| Lance embutido ofertado | 30% × C | −90.000,00 |
| **Crédito líquido liberado** | C − lance | **210.000,00** |
| TA total cobrada (18%) | 18% × **C nominal** | **54.000,00** |
| FR total (2%) | 2% × C | 6.000,00 |
| Custo total (TA+FR) sobre valor líquido | 60.000 / 210.000 | **28,6% do bem efetivamente recebido** |

**Fórmula de distorção do CEC no lance embutido:**

```
Custo Real Efetivo = (TA + FR + Seguros)           ← cobrados sobre C nominal
                     ─────────────────────────────
                     C − Lance                      ← valor líquido efetivamente liberado

CEC_distorção ≈ TA%_efetivo = TA% / (1 − %lance)
Ex.: 18% / (1 − 0,30) = 25,7%  (vs. 18% nominal anunciado)
```

> ⚠️ **Alerta máximo:** lance embutido **infla a taxa de administração efetiva** na razão direta do percentual do lance. Lance de 50% com TA 20% vira **TA efetiva de 40%** sobre o valor líquido — acima do teto de qualquer financiamento bancário de mercado. **Nunca** aceitar lance embutido sem recalcular `TA% / (1 − lance%)`.

---

## 4. Desistência, Cancelamento e Exclusão — Lei 11.795/2008 e Tema 312/STJ

### 4.1 Modalidades de saída

| Modalidade | Disparador | Base legal |
|---|---|---|
| **Desistência formal** | Pedido voluntário do consorciado | Lei 11.795/2008, art. 42 e cláusulas contratuais |
| **Cancelamento por inadimplência** | Atraso/reincidência nos pagamentos (regra contratual) | Lei 11.795/2008, art. 43 |
| **Exclusão** | Deliberação da assembleia / inadimplência reiterada | Lei 11.795/2008, arts. 43–44 |

### 4.2 Regra de devolução de valores — **Tema 312 do STJ**

**Tema 312 (REsp 1.599.511, Rel. Min. Nancy Andrighi, j. 26/08/2020)** — jurisprudência vinculante para contratos firmados **após a vigência da Lei 11.795/2008 (2009 em diante)**:

| Regra | Detalhe |
|---|---|
| **Sorteio de desistentes** | O consorciado que desiste/excluído **tem direito de participar dos sorteios mensais específicos para desistentes** na assembleia ordinária — se contemplado, recebe a carta (líquida de retenções) antes do fim do grupo |
| **Prazo de devolução (não contemplado por sorteio)** | A devolução dos valores quitados ocorre **apenas em até 30 dias após o encerramento formal do grupo** — não há direito a ressarcimento imediato no ato da desistência (cláusula contratual válida) |
| **Retenções permitidas** | (a) **TA do período** em que o consorciado participou (proporcional ao tempo/pagamentos); (b) **cláusula penal compensatória** — **apenas se a administradora comprovar prejuízo efetivo causado ao grupo** (ônus da prova da administradora) |
| **FR** | Saldo do fundo de reserva é devolvido **proporcionalmente** conforme regra do grupo (já prevista na Lei 11.795/2008) |

> ⚠️ **Alerta prático:** desistir de consórcio **pós-2009** sem ser contemplado no sorteio de desistentes = **capital preso até o fim do grupo** (pode ser 10–15 anos). Cálculo de entrada em consórcio deve tratar o valor quitado como **ativo ilíquido de longo prazo** no pior cenário.

### 4.3 Checklist antes de aderir

- [ ] Confirmar tipo de indexação (INCC/CUB vs. IPCA/IGP-M/FIPE) e simular gangorra em cenário inflacionário alto
- [ ] Simular **CEC real** (TA + FR + seguro) — comparar com taxa SAC/Price de financiamento equivalente
- [ ] Simular lance embutido com `TA% / (1 − lance%)` antes de aceitar
- [ ] Calcular `P(sorteio)` e prazo mediano com o nº real de cotas ativas do grupo
- [ ] Ler cláusula de desistência: prazo de devolução, retenções, adesão ao Tema 312
- [ ] Verificar se o seguro é **efetivamente facultativo** (rescisão do seguro sem cancelar a cota)

---

## 5. Matriz Comparativa Tripla: Consórcio × Financiamento SAC × Investimento Acumulado

### 5.1 Premissas da simulação (base única)

| Premissa | Valor |
|---|---|
| Bem alvo (valor presente, mês 0) | R$ 300.000,00 |
| Consórcio | n = 200 meses · TA 18% linear · FR 2% · parcela-base R$ 1.800 · gangorra 4,0% a.a. (INCC/IGP médio) |
| Financiamento SAC | Entrada 20% (R$ 60.000) · empréstimo R$ 240.000 · 240 meses · taxa 11,0% a.a. · carência de juros zero · TR desconsiderada (simplificação) |
| Investimento (alternativa) | Aporte mensal equivalente à parcela (R$ 1.800) · rentabilidade **10,0% a.a.** (CDI ~ líquido de IR) · bem comprado à vista quando capital ≥ preço reajustado |
| Indexação do bem (nos 3 cenários) | 4,0% a.a. — mesma base INCC/mercado para todos |
| Horizonte de comparação | Data de aquisição do bem + fluxo residual liquidado |

### 5.2 Cenário 1 — Contemplação nos primeiros 12 meses (sorteio/lance oportuno)

| Métrica | Consórcio | SAC (financiaria no mês 0) | Investimento (não alcança o bem) |
|---|---|---|---|
| Bem em posse | **Mês 12** (reajustado ~R$ 312.000) | Imóvel dado em garantia desde o início; posse plena ao fim (ou antes, se quitar) | **Não adquire o bem no horizonte curto** — acumula só ~R$ 22,8k em 12 meses |
| Pagamentos até mês 12 | ~R$ 22.400 | 12 × (1.000 + juros ~2.000) ≈ R$ 36.000 + entrada R$ 60k | R$ 21.600 investidos |
| Custo total líquido (TA+FR vs. juros) | TA 54k + FR 6k diluídos no prazo, **sem curva exponencial** | Juros SAC totais ≈ R$ 251k sobre o saldo (curva decrescente, mas alta no início) | — |
| Veredito | **Consórcio supera o SAC** — sem carregar juros compostos sobre saldo decrescente; TA linear é custo fixo previsível | Desvantagem: paga juros sobre saldo integral desde o mês 1 | Fora da corrida: 12 meses não acumulam capital suficiente |

> **Leitura:** contemplação rápida é o **único cenário em que o consórcio ganha de forma clara** — o FC é pequeno, a TA linear é diluída, e a gangorra ainda não corroeu a base.

### 5.3 Cenário 2 — Contemplação na metade do prazo (mês ~100)

| Métrica | Consórcio | SAC | Investimento |
|---|---|---|---|
| Capital já desembolsado no mês 100 | ~R$ 230k (parcelas crescentes com gangorra) | ~R$ 180k + entrada 60k (juros SAC ~R$ 120k já pagos) | ~R$ 230k aportados + juros compostos ≈ **R$ 300k+ acumulados** |
| Posse do bem | **Mês 100** | Contrato ativo desde o início; saldo devedor SAC ~R$ 175k | Poderia **comprar à vista ~mês 85–95** (bem reajustado ~R$ 445k? não — 300k × 1,04^8,3 ≈ R$ 421k; acumulado insuficiente até ~mês 100 — ajuste: com aportes de 1.800 e 10% a.a., FV mês 100 ≈ R$ 360k, compra próxima do mês 95–105) |
| Custo de oportunidade | Capital amortizado no grupo, **ilíquido** (sem resgate sem desistência) | Juros já pagos irrecuperáveis | Carteira líquida; diferença residual = **empate técnico** |
| Veredito | **Empate técnico** vs. SAC (paga TA/FR sem juros, mas espera metade do grupo) vs. **desvantagem clara vs. investimento** — o investidor tem o mesmo bem com carteira residual ou antecipa a compra sem custo de “espera do sorteio” | | |

> **Leitura:** contemplação na metade do prazo **neutraliza a vantagem estrutural** do consórcio: a TA já pagou parte relevante do custo, e o investidor em CDI/IPCA+ igualou o bem com liquidez.

### 5.4 Cenário 3 — Contemplação no terço final / encerramento (mês ≥ 160)

| Métrica | Consórcio | SAC | Investimento |
|---|---|---|---|
| Desembolso acumulado no mês 160 | **~R$ 374k** — já pagou **mais que o bem original**, **sem receber o bem ainda** (só sorteio chance de 1/200 por mês restante) | ~R$ 290k + entrada — saldo devedor SAC ~R$ 55k; imóvel quase quitado | FV de 1.800/mês a 10% a.a. em 160 meses ≈ **R$ 598k** — compraria o bem reajustado (~R$ 513k) **com folga de ~R$ 85k** |
| Posse do bem | Mês ≥ 160 (ou só no encerramento, sorteio final) | Plena ao fim do SAC | **Mês ~130–140** (compra à vista quando FV ≥ preço reajustado) |
| Custo total vs. alternativa | Prejuízo severo: pagou parcelas crescentes (gangorra) + TA/FR sobre base reajustada por 160+ meses | Pior que o investimento (juros ~R$ 250k) | **Melhor resultado:** bem adquirido anos antes + sobra de rentabilidade composta |
| Veredito | **Prejuízo severo** vs. acúmulo em títulos (CDI/IPCA+) — o investidor teria comprado o bem à vista **antes** e com sobra | | |

> ⚠️ **Alerta final:** a **variável dominante** do consórcio não é a TA — é **QUANDO você é contemplado**. Sorteio tardio transforma o produto em poupança forçada carregada de TA/FR e gangorra, com liquidez bloqueada pelo Tema 312.

### 5.5 Síntese de decisão

| Fator | Consórcio | SAC | Investimento + vista |
|---|---|---|---|
| Custo nominal rotulado | Sem juros rotulados | Juros explícitos (ex.: 11% a.a.) | Custo = taxa alternativa (oportunidade) |
| Risco de prazo | **Alto** (sorteio aleatório) | Baixo (cronograma fixo) | **Zero** — decisão do investidor |
| Liquidez do capital | Bloqueada (Tema 312) | N/A (não é capital próprio) | **Alta** (carteira resgatável) |
| Efeito gangorra | **Sim** — parcela sobe até o fim | Parcela SAC **decresce** (amortização constante) | Bem reajusta, mas capital reajusta junto (CDI/IPCA+) |
| Melhor uso | Contemplação rápida (< 2–3 anos) + disciplina de aporte equivalente | Entrada disponível + certeza da aquisição | Objetivo flexível; maximiza retorno composto |
| Pior uso | Espera longa, lance embutido, grupo inflacionário | Financiar 100% sem entrada (custo explode) | — |

---

## 6. Referências Legislativas e Jurisprudenciais (datadas)

| Fonte | Conteúdo-chave tratado aqui |
|---|---|
| **Lei nº 11.795, de 05/11/2008** (Lei do Consórcio) | Natureza da comunhão (art. 2º); assembleias (art. 30); TA (art. 17); FR (arts. 26–27, 30); contemplação (arts. 33–36); desistência/cancelamento (arts. 42–45) |
| **Resolução CMN nº 3.919, de 22/07/2020** | Regulamenta a Lei 11.795/2008; requisitos de autorização das administradoras; limites de TA/FR por tipo de bem (teto histórico: 24% imóveis, 25% veículos/demais — conferir tabela vigente); regras de assembleia e prestação de contas |
| **Tema 312 do STJ (REsp 1.599.511, Rel. Min. Nancy Andrighi, j. 26/08/2020)** | Validade de cláusula que condiciona devolução de valores ao término do grupo (contratos pós-2009); participação obrigatória em sorteios de desistentes; prazo de devolução em até 30 dias após encerramento do grupo |
| **Lei nº 4.595, de 31/12/1964** (revogada nos arts. de consórcio) | Regime anterior — base histórica para contratos antigos (pré-2009) |
| **Índices CFI/BCB** | Divulgação oficial de INCC-DI e CUB para indexação de consórcios imobiliários |

---

*Documento gerado pelo curador de conhecimento — Sampo. Simulações usam premissas fixas didáticas; recalcular com taxas/índices vigentes antes de decisão real.*
