# Regras Criptoativos — Brasil

> **Documento canônico Sampo** | Escopo: regulamentação fiscal, segurança operacional e limites de alocação de criptoativos no Brasil.
> Última revisão: 2026-10-23 | Base legal datada conforme indicado em cada seção.

---

## 1. Marco Regulatório e Obrigações Fiscais (Receita Federal)

### 1.1 Instrução Normativa RFB nº 1.888/2019

| Agente | Obrigação | Detalhes |
|---|---|---|
| **Exchanges brasileiras (VBCEs)** | Reporte automático | Todas as operações (compra, venda, troca, transferência, depósito) comunicadas automaticamente à Receita Federal via eFinanceira/Coleta Nacional — sem ação do usuário |
| **Pessoa física** | Reporte mensal obrigatório | Operações em **exchanges estrangeiras, P2P, DeFi (finanças descentralizadas) e autocustódia com exchange estrangeira** |
| **Gatilho do reporte** | R$ 30.000/mês | Soma do **valor total de operações** (não do lucro) no mês-calendário em exchanges estrangeiras / P2P / DeFi |
| **Prazo do reporte** | Último dia útil do mês subsequente | Ex.: operações de janeiro → declarar até o último dia útil de fevereiro |
| **Sistema** | Coleta Nacional (e-Financeira) | Acesso via portal da Receita com certificado digital ou gov.br |

**Pontos críticos da IN 1.888/2019:**
- Conta exchanges brasileiras: isento de reporte manual (reportam sozinhas).
- Conta exchanges estrangeiras (Binance Global, Coinbase, Kraken, Bybit etc.): reporte manual obrigatório acima do gatilho.
- Carteiras DeFi (Uniswap, Aave, staking em protocolos) e P2P: entram na mesma obrigação.
- **Omissão do reporte**: sujeita a multa de 25% sobre o valor não informado (mín. R$ 100), nos termos do art. 3º da IN 1.888/2019 c/c art. 76 da Lei 8.212/91.

### 1.2 Tributação e Ganho de Capital

#### 1.2.1 Regra tradicional — alienação em território nacional

Alienação (venda, troca por outra cripto, uso em pagamento) de criptoativos custodiados no Brasil:

| Base de cálculo do ganho (LC 155/2001) | Alíquota |
|---|---|
| Até R$ 5.000.000 | 15% |
| De R$ 5.000.000,01 a R$ 10.000.000 | 17,5% |
| De R$ 10.000.000,01 a R$ 30.000.000 | 20% |
| Acima de R$ 30.000.000 | 22,5% |

**Alíquota efetiva aplicada na prática (Lei 8.981/95, art. 21):** **15% sobre o ganho**, enquanto o ganho de alienação total no mês não exceder **R$ 5 milhões** — faixa que cobre >99% das pessoas físicas.

**Isenção mensal (Lei 7.713/88, art. 23, VI — redação aplicada por analogia à venda de ações; jurisprudência e praxe consolidada para cripto):**

- **Isenção de IRPF para alienações totais de até R$ 35.000/mês** — todas as criptomoedas somadas (vendas de BTC + ETH + altcoins etc. no mesmo mês somam para o teto).
- Acima de R$ 35.000 em vendas no mês: **todo o ganho** do mês é tributável a 15% (não apenas a parcela excedente).
- Base de cálculo do ganho: `ganho = valor da alienação − (custo de aquisição + despesas)`.
- Custo de aquisição: valor pago em R$ na compra (inclui corretagem/taxas); média ponderada ou PEPS (first-in first-out) — a Receita não impõe método único, mas exige coerência.

#### 1.2.2 Impacto da Lei nº 14.754/2023 (ativos no exterior)

A Lei 14.754/2023 (sancionada 12/09/2023, vigência 01/01/2024) alterou o tratamento de ativos mantidos no exterior:

| Cenário | Regime | Alíquota | Isenção R$ 35k/mês |
|---|---|---|---|
| Cripto em exchange **brasileira** (VBCE registrada) | Ganho de capital nacional | 15% | ✅ Aplica-se |
| Cripto em exchange **estrangeira** (custódia no exterior) | Ganho de capital / Lei 14.754 | 15% | ❌ **Não aplica-se** |
| Carteira offshore / estrutura no exterior qualificada como **aplicação financeira** | Renda (regime de 15%) | 15% | ❌ Não aplica-se |
| Cripto em **autocustódia** (hardware wallet) | Jurisprudência em definição; posição conservadora: tratar como alienação nacional com isenção | 15% | Debate aberto |

**Regra prática:** a partir de 2024, **qualquer cripto custodiada em entidade no exterior** (exchange estrangeira) **perde a faixa de isenção de R$ 35.000/mês** e é tributada a 15% sobre **todo o ganho**, desde o primeiro real de lucro.

> **Alerta Sampo:** a jurisprudência sobre carteiras de autocustódia (self-custody) ainda não é pacífica. Posição conservadora: tributar desde o primeiro ganho se houver qualquer conexão com exchange estrangeira no ciclo de custódia.

#### 1.2.3 Declaração de Bens e Direitos — DIRPF (Grupo 08)

Obrigatório declarar saldos de criptoativos na DIRPF (Anual, exercícios seguintes à data-base 31/12) quando o **saldo por tipo de criptoativo ≥ R$ 5.000** em 31/12.

| Código | Item |
|---|---|
| 08-01 | Bitcoin (BTC) |
| 08-02 | Altcoins (criptomoedas que não sejam BTC) |
| 08-03 | Stablecoins (USDT, USDC, DAI etc.) |
| 08-10 | NFTs |
| 08-99 | Outros criptoativos |

- Campo declarado: **custo de aquisição** (não o valor de mercado).
- Manter comprovantes (extratos de exchange, tx hashes, prints de data) por, no mínimo, **5 anos** (prazo decadencial do art. 150 do CTN).

### 1.3 Exemplo Numérico — Apuração Fiscal

**Cenário:** João vende BTC em exchanges brasileiras e estrangeiras ao longo de 2026.

| Mês | Operação | Vendas totais | Custo aquisição | Ganho |
|---|---|---|---|---|
| Março | Vende 0,05 BTC em exchange BR | R$ 25.000 | R$ 10.000 | R$ 15.000 |
| Julho | Vende 0,1 BTC em exchange BR | R$ 40.000 | R$ 15.000 | R$ 25.000 |
| Agosto | Vende 0,05 BTC em exchange BR | R$ 10.000 | R$ 5.000 | R$ 5.000 |
| Outubro | Vende 0,02 BTC em exchange **estrangeira** | R$ 8.000 | R$ 3.000 | R$ 5.000 |

**Apuração:**

1. **Março:** vendas R$ 25.000 ≤ R$ 35.000 → **isento**. IR = R$ 0.
2. **Julho:** vendas R$ 40.000 > R$ 35.000 → **todo o ganho tributável**. IR = 15% × R$ 25.000 = **R$ 3.750**.
3. **Agosto:** vendas R$ 10.000 ≤ R$ 35.000 → **isento**. IR = R$ 0.
4. **Outubro (exchange estrangeira, pós Lei 14.754/2023):** **sem isenção de R$ 35k**. IR = 15% × R$ 5.000 = **R$ 750**.

**Total do ano: R$ 4.500 de IR.** Carnê-Leão/Ganho de Capital (DAA) recolhimento até o último dia útil do mês seguinte à alienação.

**Reporte Coleta Nacional (IN 1.888):** a exchange brasileira reporta automaticamente março/julho/agosto. A venda de outubro (exchange estrangeira): se a soma mensal de **todas** as operações em exchanges estrangeiras no mês ultrapassar R$ 30.000 → reporte manual obrigatório. No exemplo, R$ 8.000 < R$ 30.000 → sem obrigação de reporte nesse mês específico.

---

## 2. Segurança Operacional e Risco de Custoódia

### 2.1 O Risco de Exchange (Custódia de Terceiros)

Ao depositar cripto em exchange, o usuário **não é dono das chaves privadas** — é um credor da plataforma, sujeito à sua saúde financeira e governança.

| Evento | Ano | Lição |
|---|---|---|
| **Mt. Gox** | 2014 | Maior exchange da época; ~850.000 BTC perdidos por hack/gestão; recuperação parcelada >10 anos depois |
| **QuadrigaCX** | 2019 | "Óbito" do CEO com chaves em cold wallet inacessível; ~215M CAD perdidos |
| **Celsius / Voyager / 3AC** | 2022 | Cascata de falências por alavancagem e contagio |
| **FTX** | Nov/2022 | 2ª maior falência da história cripto; ~8 bilhões USD em furos de balanço; uso de fundos de clientes em operações da Alameda Research |

**Fatos regulatórios críticos:**
- **FGC (Fundo Garantidor de Créditos) NÃO cobre exchange de criptoativos** — só instituições autorizadas pelo BC (bancos, cooperativas de crédito, corretoras registradas CVM).
- **Não existe regulação prudencial equivalente à bancária** para exchanges de cripto no Brasil (as VBCEs são registradas na CVM/BC sob regime de cadastro, não de autorização com exigência de capital mínimo e liquidez).
- Falência da exchange = **fila de credores** (quitação fracionada, tipicamente anos).

**Máxima fundamental:**

> **"Not your keys, not your coins."**
> Suas chaves privadas em poder de terceiro = sua cripto em risco de terceiro.

### 2.2 Autocustódia (Self-Custody)

Tomar posse das próprias chaves privadas elimina o risco de contraparte de exchange, transfere a responsabilidade de segurança ao titular.

#### 2.2.1 Cold Wallets / Hardware Wallets (Recomendado para longo prazo)

| Dispositivo | Tipo | Características |
|---|---|---|
| **Ledger** (Nano S Plus, Nano X, Stax) | Hardware wallet | Chip seguro certificado; assina transações offline; conecta via USB/BT |
| **Trezor** (Model One, Model T, Safe 5) | Hardware wallet | Open source; display físico para verificação de endereço; conecta via USB |
| **Coldcard** | Hardware wallet (Bitcoin-only) | Foco exclusivo em BTC; air-gapped por SD card |

**Princípio:** dispositivo **desconectado da internet** guarda as chaves privadas; a assinatura da transação ocorre no dispositivo e só o pacote assinado vai para a rede — a chave nunca expõe.

#### 2.2.2 Hot Wallets (Carteiras Software Conectadas)

| Carteira | Rede | Uso típico |
|---|---|---|
| **MetaMask** | EVM (ETH, BSC, Polygon, Arbitrum, Base…) | Interação DeFi, NFTs, dapps |
| **Phantom** | Solana (+ EVM) | Ecossistema Solana, DePIN, memecoins |
| **Rabby** | EVM multi-chain | Segurança reforçada (simulação de transação) |

**Riscos inerentes:**
- **Phishing** (sites falsos de airdrop/staking, extensões maliciosas, ads de Google falsos)
- **Ataque de contrato malicioso** (aprovação infinita de token → drenagem total do saldo)
- **Comprometimento do device** (malware, keylogger, acesso físico)
- **Seed phrase exposta em dispositivo conectado**

**Regras de uso:**
- Manter apenas o **capital operacional** (necessário para DeFi/swap/NFT) em hot wallet.
- Restringir aprovações de token (usar revogador de aprovações, ex. revoke.cash).
- Verificar domínio por canais oficiais; nunca clicar em links de DM/Telegram.

#### 2.2.3 Gestão das 12/24 Palavras (Seed Phrase)

A seed phrase (mnemônica BIP-39) é o **mestre absoluto** de todos os ativos da carteira. Perdeu a seed = perdeu os fundos. Compartilhou a seed = transferiu a custódia.

**Proibições estritas (nunca fazer):**

| ❌ Proibido | Risco |
|---|---|
| Armazenar em **fotos** (celular/galeria) | Sync automático para nuvem; malware de galeria |
| Salvar em **nuvem** (Google Drive, iCloud, Dropbox) | Vazamento de conta; engenharia social; hack da conta |
| Enviar por **e-mail** (para si ou terceiros) | Interceptação; cópia em servidores do provedor |
| Salvar em **arquivo .txt/.pdf** em computador conectado à internet | Malware; ransomware; keylogger |
| Armazenar em **gerenciador de senhas online** | Contradiz a autocustódia; alvo de ataque |
| Fotografar / filmar / anotar em papel descartável | Exposição física; descarte inadequado |

**Boas práticas:**
- Cópia em **papel ou placa de metal** (ex.: Cryptosteel, Billfodl, Faradite) resistente a fogo/água.
- Guardar em local físico seguro (cofre, banco — awareness: banco não é FGC para a seed, mas protege contra furto físico).
- **Nunca digitar a seed em site/app algum** — nenhum protocolo legítimo pede a seed.
- Duas cópias físicas em locais distintos (mitiga perda por sinistro local).

### 2.3 Matriz Rápida de Custódia

| Critério | Exchange | Hot Wallet | Hardware Wallet |
|---|---|---|---|
| Dono das chaves | ❌ Exchange | ✅ Usuário | ✅ Usuário |
| Risco de contraparte/falência | 🔴 Alto | ✅ Nenhum | ✅ Nenhum |
| Risco de hack remoto | 🔴 Alto | 🟡 Médio | 🟢 Baixo |
| Risco de phishing/uso | 🟡 | 🔴 Alto | 🟢 Baixo |
| Praticidade para trading | ✅ Alta | ✅ Alta | 🔴 Baixa (air-gap) |
| Recomendado para | Capital operacional (<6 meses) | Capital operacional DeFi | **Reserva de longo prazo** |

---

## 3. Matriz de Enquadramento e Limites de Alocação no Portfólio

### 3.1 Assimetria e Volatilidade Extrema

| Indicador | Valor histórico |
|---|---|
| Drawdown máx. BTC (ciclos de baixa) | **>80%** (ex.: 69k → 15,5k em 2022 ≈ −78%; picos históricos com recuperação de 3–4 anos) |
| Drawdown típico altcoins | 90–99% em relação ao pico |
| Volatilidade anualizada BTC | 50–70% (vs. ~15% IBOV, ~20% S&P 500) |
| Correlação com bolsa em crise | sobe (não é hedge confiável) |

**Consequência:** cripto é classe de **alto risco, alto retorno assimétrico** — performance histórica não garante retorno futuro; alocação deve sobreviver ao cenário de −80% sem comprometer o plano financeiro.

### 3.2 Limite de Alocação Racional

| Faixa | Classificação Sampo |
|---|---|
| 0% | Conservador puro / aversão total a volatilidade |
| **1–5% do patrimônio líquido investível** | **Faixa recomendada — teto racional para investidor PF** |
| 5–10% | Agressivo; exige tese forte e estômago para drawdown |
| >10% | Especulativo; não recomendado sem patrimônio consolidado e reserva blindada |

**Composição sugerida dentro da fatia cripto:**
- Núcleo (60–80% da fatia): **Bitcoin (BTC)** — liquidez, liquidez de mercado, histórico de 15+ anos.
- Satélite (20–40% da fatia): **Ethereum (ETH)** — rede DeFi/NFT madura.
- Altcoins além de BTC/ETH: considerar **especulação** e limitar a fração residual da fatia.

### 3.3 Precedência Inegociável — BLOQUEIO_INVESTIMENTO

> **PROIBIDO qualquer aporte em criptoativos se qualquer uma das condições abaixo estiver vigente:**

| Condição de bloqueio | Status exigido para liberar aporte |
|---|---|
| **Reserva de Emergência** | Integralizada (6 meses de custo de vida fixo em liquidez — CDB DI, Tesouro Selic, equivalente) |
| **Passivos com CET > Selic** | Quitados (cartão rotativo, cheque especial, crédito pessoal com taxa acima da Selic — spread atual ~≈13–15% a.a.) |

**Lógica:** a classe com drawdown de 80% é incompatível com capital que pode ser resgatado sob pressão no pior momento do ciclo. Capital de emergência e passivos caros têm prioridade absoluta sobre qualquer retorno especulativo.

**Ordem de aplicação Sampo:**
1. Quitar passivos com CET > Selic (cartão, consignado caro, crédito pessoal).
2. Integralizar Reserva de Emergência (6 meses).
3. Objetivos de curto/médio prazo (<3 anos) em ativos de baixo risco.
4. Aporte em cripto **dentro do teto de 1–5%** do patrimônio investível.
5. Aportes recorrentes (DCR) em BTC/ETH para diluir timing.

### 3.4 Alerta Anti-Golpe

> **Qualquer plataforma, guru, robô ou "estrategista" que prometa:**
> - rentabilidade **fixa mensal garantida** em criptoativos;
> - arbitragem automatizada com "risco zero";
> - retorno diário/semanal "comprovado" via indicadores;
> - capitalização em BTC/ETH com garantia institucional;
>
> **enquadra-se tecnicamente como esquema de pirâmide / fraude financeira** (art. 171 do Código Penal — estelionato; e eventual enquadramento na Lei 12.846/2013 — Lei Anticorrupção/Lei da Má-Fé, para organização).

**Sinais de alerta clássicos:**
1. Rentabilidade fixa e constante — mercados reais têm variância; rentabilidade fixa mensal em ativo volátil é matematicamente impossível sustentada.
2. Pressão por captação de novos investidores (estrutura piramidal).
3. Dificuldade de resgate ("taxa de saque", "liberação em X dias", KYC interminável).
4. Influenciador promovendo sem CNPJ/registro na CVM.
5. Promessa de "recuperação de dinheiro perdido em golpes" (golpe secundário).
6. Comunidade em Telegram/WhatsApp com depoimentos genéricos e pressão de tempo ("últimas vagas").

**Regra Sampo:** promessa de retorno garantido em cripto = **red flag terminal**. Nunca aportar. Denunciar à CVM (Disque Denúncia) e Polícia Federal.

---

## 4. Checklist de Conformidade Anual (Pessoa Física)

- [ ] Extrair relatórios de todas as exchanges (BR e estrangeiras) — histórico completo de operações.
- [ ] Verificar soma mensal de operações em exchanges estrangeiras / P2P / DeFi > R$ 30.000 → reporte na **Coleta Nacional** até o último dia útil do mês seguinte.
- [ ] Apurar ganho de capital por alienação (todas as vendas/trocas do ano) — considerar isenção mensal R$ 35k apenas para custódia **nacional**.
- [ ] Recolher DARF do ganho de capital (0605 — Ganho de capital alienação bens comuns; ou DAA) até o último dia útil do mês seguinte à operação.
- [ ] Declarar saldos ≥ R$ 5.000 por tipo de criptoativo na **DIRPF (Grupo 08)** com custo de aquisição.
- [ ] Arquivar comprovantes (extratos, hashes, recolhimentos) por 5 anos.

---

## 5. Fontes Legais de Referência

| Instrumento | Conteúdo-chave |
|---|---|
| **IN RFB nº 1.888/2019** (12/11/2019) | Obrigações de reporte à Receita — exchanges e pessoas físicas (gatilho R$ 30.000/mês) |
| **Lei nº 8.981/1995, art. 21** | Ganho de capital — alíquota 15% até R$ 5 mi de ganho |
| **LC nº 155/2001** | Tabela progressiva do ganho de capital (15% a 22,5%) |
| **Lei nº 7.713/1988, art. 23, VI** | Isenção alienações até R$ 35.000/mês (aplicada por analogia) |
| **Lei nº 14.754/2023** (12/09/2023, vigência 01/01/2024) | Tributação de ativos no exterior; 15% sem isenção R$ 35k para ativos custodiados fora |
| **Instrução Normativa RFB nº 1.700/2017 / atualizações** | DIRPF — Bens e Direitos Grupo 08 (criptoativos), código e obrigatoriedade ≥ R$ 5.000 |
| **Lei nº 12.846/2013 (Lei Anticorrupção)** | Má-fé em relações de consumo/mercado — base para enquadramento de fraudes |
| **Código Penal, art. 171** | Estelionato — esquemas de pirâmide com promessa de rentabilidade fixa |

---

*Documento canônico — Sampo Knowledge Base. Dúvidas fiscais patrimoniais relevantes: consultar contador/advogado tributarista antes de declarar ou recolher.*
