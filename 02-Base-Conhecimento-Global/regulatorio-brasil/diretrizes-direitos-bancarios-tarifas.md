# DIRETRIZES — DIREITOS BANCÁRIOS, TARIFAS E PROTEÇÃO AO CONSUMIDOR

**Domínio:** `02-Base-Conhecimento-Global/regulatorio-brasil/`
**Uso:** base canônica para `auditor-cartao-credito.md`, `estrategista-dividas-bacen.md`, `simulador-imobiliario-caixa.md` e contestações de tarifas.
**Agentes injetáveis:** todo agente que audite cobrança bancária, contrato ou portabilidade.

---

## 1. PACOTE DE SERVIÇOS ESSENCIAIS GRATUITOS

**Fundamento:** Resolução CMN nº 3.919/2010.

Todo banco é obrigado a oferecer **conta corrente e poupança sem tarifa mensal de manutenção**, incluindo franquia gratuita mensal:

| Serviço | Franquia gratuita obrigatória | Observações |
|---|---|---|
| Saques | **4/mês** | Guichê ou autoatendimento |
| Transferências entre contas da própria instituição | **2/mês** | Demais transferências podem ser tarifadas |
| Extratos | **2/mês com movimentação do mês anterior** + extrato anual consolidado de tarifas | |
| Consultas de saldo/extrato via internet banking / app | **Ilimitadas** | Canal digital sempre gratuito |
| Cartão de débito | **Fornecimento gratuito** | |
| Talões de cheque | **10 folhas/mês** | Mediante preenchimento dos requisitos |

### Protocolo de migração para Serviços Essenciais

Fluxo para cancelar cesta de serviços paga e migrar imediatamente:

1. Solicitar por chat, SAC ou aplicativo: *"Solicito o cancelamento da cesta de serviços [nome/código] e a migração imediata para o Pacote de Serviços Essenciais gratuitos, conforme Resolução CMN nº 3.919/2010."*
2. Exigir **número de protocolo** registrado na resposta.
3. Confirmar por extrato que a cobrança cessou na competência seguinte; se cobrado, exigir estorno em dobro (Seção 3).

---

## 2. VENDA CASADA E ABUSOS CONTRATUAIS

**Fundamento:** Art. 39, I, da Lei nº 8.078/1990 (CDC); Súmula 473 do STJ.

### Tipificações clássicas em financiamentos e empréstimos

| Abuso | O que é | Base legal |
|---|---|---|
| Venda casada de seguro | Condicionar taxa de juros menor ou aprovação do crédito à contratação de seguro de vida do próprio banco | Art. 39, I, CDC |
| Venda casada de capitalização / previdência / consórcio | Imposição de produto financeiro próprio como exigência de crédito | Art. 39, I, CDC |
| Imposição de seguradora | Impor a apólice da instituição credora em operação com seguro obrigatório (ex.: crédito imobiliário) — consumidor escolhe livremente a seguradora | **Súmula 473 STJ** |
| Seguro prestamista automático | Inclusão na CCB sem opção destacada e consentimento expresso — contratação é **facultativa** | Vedação expressa; CCB exige destaque e aceite |

**Regra prática:** qualquer produto financeiro vinculado a crédito que não seja exigência legal de mercado é recusável sem perda de condição de aprovação.

---

## 3. TARIFAS ILEGAIS E REPETIÇÃO DE INDÉBITO

**Fundamento:** Art. 42 do CDC (repetição de indébito).

### Tarifas excluídas do sistema

| Tarifa | Situação | Fundamento |
|---|---|---|
| **TAC** (Tarifa de Abertura de Crédito) | Ilegal em contratos firmados **após 30/04/2008** | Súmula 565 STJ + Recurso Repetitivo **Tema 618** |
| **TEC** (Tarifa de Emissão de Carnê/Boleto) | Ilegal em contratos firmados **após 30/04/2008** | Súmula 565 STJ + Tema 618 |
| Taxa de liquidação antecipada | Ilegal cobrar — quitação total ou parcial antecipada com **redução proporcional de juros** é direito gratuito de pessoas físicas | Resolução CMN nº 3.516/2007 |

### Restituição em dobro

- **Art. 42, parágrafo único, do CDC:** valor cobrado indevidamente deve ser devolvido **em dobro**, acrescido de correção monetária e juros legais.
- Exceção: banco comprovar **engano justificável** (a prova é dele, não do consumidor).
- Aplica-se também à manutenção de cesta paga após pedido de migração (Seção 1) e a TAC/TEC pagas após 30/04/2008.

**Prazo de referência:** pedido de devolução via SAC; recusa → Ouvidoria → Bacen (BACENJUD) → Small Claims (Juizado Especial Cível).

---

## 4. PORTABILIDADE DE CRÉDITO

**Fundamento:** Resolução CMN nº 5.057/2022.

### Obrigatoriedade de fornecimento de dados

A instituição credora **original** deve fornecer, em até **1 dia útil** após requisição:
- saldo devedor contábil;
- planilha descritiva com o **CET** (Custo Efetivo Total).

### Regras invioláveis

| Regra | Detalhe |
|---|---|
| Valor | Novo financiamento **não pode superar** o saldo devedor remanescente |
| Prazo | Nova operação **não pode ultrapassar** o prazo restante do contrato original (salvo autorização explícita em renegociação distinta) |
| Custos | Custos de transferência interbancária **não podem ser repassados** ao consumidor |

**Uso no sistema:** portabilidade só entra em plano de ação do `estrategista-dividas-bacen.md` após conferir saldo e CET originais vs. proposta — qualquer extrapolação de valor/prazo ou repasse de custo é contestável.

---

## 5. ENCERRAMENTO DE CONTAS

**Fundamento:** Resolução CMN nº 4.753/2019.

| Direito | Regra |
|---|---|
| Canais | Encerramento pelos **mesmos canais** de contratação (inclusive digitais/app) |
| Pacotes tarifários | Cessação da cobrança **no ato da solicitação** |
| Prazo | Encerramento formal definitivo em até **30 dias corridos** + termo comprobatório |

Conta com saldo residual? Exigir transferência/levantamento e cancelamento de débitos automáticos vinculados antes do encerramento.

---

## 6. MODELOS DE TEXTO PARA PROTOCOLO (SAC / OUVIDORIA / BACEN)

> Substituir `[...]`. Exigir sempre **número de protocolo** e guardar comprovante.

### 6.1 Migração para Serviços Essenciais

```
Prezados,

Solicito o cancelamento imediato da cesta de serviços [NOME/CÓDIGO] da minha
conta [AGÊNCIA/Nº] e a migração para o Pacote de Serviços Essenciais
gratuitos, nos termos da Resolução CMN nº 3.919/2010.

Solicito protocolo desta requisição e estorno da cobrança indevida da
competência [MÊS/ANO], com devolução em dobro conforme Art. 42, parágrafo
único, do CDC, caso já tenha sido faturada.

Atenciosamente,
[NOME] — CPF [XXX.XXX.XXX-XX]
```

### 6.2 Contestação de TAC/TEC ou tarifa ilegal

```
 contesto a cobrança da tarifa [TAC/TEC/NOME] no contrato nº [...],
firmado em [DATA — pós 30/04/2008], por ilegalidade (Súmula 565 do STJ e
Tema 618 do STJ).

Solicito: (1) cancelamento da cobrança; (2) devolução em dobro dos valores
já pagos, com correção monetária e juros legais, Art. 42, parágrafo único,
do CDC.

Protocolo: [N]. Prazo de resposta: imediato.
```

### 6.3 Venda casada de seguro/produto vinculado a crédito

```
Registro que a aprovação/taxa do contrato nº [...] foi condicionada à
contratação de [SEGURO/TÍTULO/PREVIDÊNCIA/CONSÓRCIO] da própria instituição,
configurando venda casada (Art. 39, I, CDC) e, no caso de seguro
obrigatório, violação da Súmula 473 do STJ.

Solicito: (1) revisão do contrato sem o produto vinculado; (2) reaplicação
da taxa pactuada; (3) restituição dos valores pagos pelo produto, em dobro.

Protocolo: [N].
```

### 6.4 Recusa de taxa de liquidação antecipada

```
Solicito a quitação antecipada [total/parcial] do contrato nº [...] com
redução proporcional de juros, direito gratuito de pessoas físicas (Resolução
CMN nº 3.516/2007). Qualquer cobrança de taxa de liquidação será contestada
como tarifa indevida, com devolução em dobro (Art. 42 do CDC).

Protocolo: [N].
```

### 6.5 Portabilidade — recusa ou atraso em fornecer dados

```
Requisiti em [DATA] o saldo devedor contábil e a planilha descritiva com CET
do contrato nº [...]. Não recebi resposta em 1 dia útil, em desacordo com a
Resolução CMN nº 5.057/2022.

Solicito o envio imediato dos dados, sob pena de registro de reclamação no
Banco Central (BACENJUD), e lembro que a portabilidade não pode superar o
saldo devedor nem o prazo restante, com custos de transferência não
repassáveis a mim.

Protocolo: [N].
```

### 6.6 Encerramento de conta recusado/dificultado

```
Solicito o encerramento definitivo da conta [AGÊNCIA/Nº] pelos canais
digitais disponíveis à contratação, conforme Resolução CMN nº 4.753/2019,
com cessação imediata da cobrança de pacotes tarifários e emissão de termo
comprobatório em até 30 dias corridos.

Protocolo: [N].
```

### 6.7 Escalonamento (sequência obrigatória)

```
1. SAC/chat → obter protocolo → resposta.
2. Sem resolução em [X] dias → OUVIDORIA (mesmo banco) → novo protocolo.
3. Sem resolução → BACENJUD (Banco Central, https://www.bcb.gov.br) informando
   os protocolos anteriores.
4. Dano de menor valor → Juizado Especial Cível (Small Claims).
```

---

## 7. MAPA DE ARTIGOS CITADOS

| Norma | Dispositivo | Matéria |
|---|---|---|
| Lei nº 8.078/1990 (CDC) | Art. 39, I | Venda casada |
| Lei nº 8.078/1990 (CDC) | Art. 42 + parágrafo único | Repetição de indébito em dobro |
| Resolução CMN nº 3.919/2010 | — | Pacote de Serviços Essenciais gratuitos |
| Resolução CMN nº 3.516/2007 | — | Liquidação antecipada gratuita (PF) |
| Resolução CMN nº 5.057/2022 | — | Portabilidade de crédito |
| Resolução CMN nº 4.753/2019 | — | Encerramento de contas |
| Súmula 473 STJ | — | Livre escolha da seguradora |
| Súmula 565 STJ / Tema 618 STJ | — | Ilegalidade de TAC/TEC (pós 30/04/2008) |

---
*Base canônica — atualizações só após validação por `validador-conhecimento.md`.*
