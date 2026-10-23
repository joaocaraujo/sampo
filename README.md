# Sampo — Sistema Operacional de Inteligência Financeira Pessoal

> **Arquitetura:** *Orchestrator-Workers* em arquivos Markdown + Context Injection.
> **Sem código proprietário. Custo financeiro zero. Portável entre IAs.**

## 1. Visão do Produto

Sampo é um sistema operacional de inteligência financeira pessoal construído inteiramente em arquivos Markdown. Um orquestrador central (`cfo-mestre.md`) injeta contexto sob demanda em agentes especialistas de responsabilidade única, todos alimentados por uma base de conhecimento canônica e validada.

**Filosofia — separação estrita:**

| Camada | Conteúdo | Status Git |
|---|---|---|
| **Motor** | Orquestrador, agentes, base de conhecimento | Público (reutilizável) |
| **Dados** | `users/<id>/perfil.md` — perfil, faturas, dívidas | **Privado — blindado via `.gitignore`** |

---

## 🏛️ Por que Sampo? (A Filosofia por trás do Nome)

No épico finlandês *Kalevala*, o ferreiro mítico Ilmarinen forja o **Sampo** — um moinho mágico e autônomo com tampa multicolorida. Uma vez construído, ele gira perpetuamente nos bastidores, fornecendo simultaneamente três moendas essenciais para a prosperidade do seu povo:
1. **Grãos:** O sustento imediato (gestão do fluxo de caixa, orçamento dos 40% e custos essenciais);
2. **Sal:** A conservação e blindagem contra degradação (reserva de emergência, expurgo de tarifas abusivas e amortização de passivos);
3. **Ouro:** A criação de riqueza contínua e assimetria positiva (alocação patrimonial, juros compostos e eficiência tributária).

Este repositório foi batizado de **Sampo** porque reflete exatamente essa engenharia: um motor financeiro autônomo, modular e portátil que processa regras complexas nos bastidores para que você possa viver a vida com clareza matemática e liberdade.

---

## 2. Mapa da Árvore de Diretórios

```
sampo/
├── README.md                        ← este documento
├── .gitignore                       ← bloqueia users/ (carga sensível)
│
├── 00-Orquestrador/                 ← MOTOR LÓGICO CENTRAL
│   ├── cfo-mestre.md                ← orquestrador principal (CFO)
│   ├── skill-creator.md             ← gerador de novos agentes
│   └── radar-antecipacao.md         ← varredura preventiva de sazonalidades
│
├── 01-Agentes-Especialistas/        ← WORKERS (single responsibility)
│   ├── raio-x-financeiro.md         ← diagnóstico patrimonial integral
│   ├── ingestor-conteudo.md         ← captura de fontes externas
│   ├── validador-conhecimento.md    ← filtro anti-mito (Bacen/CVM/matemática)
│   ├── auditor-cartao-credito.md    ← auditoria de faturas e anuidades
│   ├── estrategista-dividas-bacen.md← negociação de dívidas / restrição Serasa
│   ├── simulador-imobiliario-caixa.md← simulação SFH/FGTS (§ ver §4)
│   ├── arquiteto-investimentos-br.md← carteira, tributação, FGC
│   ├── consultor-clt-pj-tributario.md← comparativo CLT vs. PJ
│   ├── engenheiro-milhas-beneficios.md← milhas, pontos, anuidades, cashback
│   ├── avaliador-veicular-mobilidade.md← TCO, comprar vs. assinar vs. app
│   └── auditor-consorcio.md         ← auditoria de cotas, lance, desistência
│
├── 02-Base-Conhecimento-Global/     ← MEMÓRIA CANÔNICA (validada)
│   ├── prioridades-financeiras/     ← ordem-reserva-carro-casa.md
│   ├── orcamento-e-custos/          ← regra-dos-40-porcento.md
│   ├── tributacao-e-trabalho/       ← tabelas-trabalho-irpf-inss.md; regras-pj-simples-mei.md; manual-definitivo-mei.md
│   ├── regulatorio-brasil/          ← diretrizes-credito-imobiliario.md; tributacao-investimentos-br.md;
│   │                                  diretrizes-direitos-bancarios-tarifas.md; mecanica-consorcios-brasil.md;
│   │                                  planejamento-sucessorio-seguros.md
│   ├── cripto-e-ativos-digitais/    ← regras-criptoativos-brasil.md
│   ├── mentalidade-e-habitos/       ← Graham, Kiyosaki, Housel, Babilônia
│   ├── investimentos/               ← Investidor Inteligente (Graham)
│   └── mitos-e-falacias/            ← lições do validador (gerada pelo pipeline)
│
└── users/                           ← DADOS SENSÍVEIS (NUNCA versionados)
    └── meu-perfil/
        └── perfil.md                ← ficha técnica do usuário
```

---

## 3. Matriz de Agentes Especialistas

| Agente | Papel Central (Single Responsibility) | Gatilho de Ativação | Arquivos de Dependência |
|---|---|---|---|
| **cfo-mestre** | Orquestração global, roteamento, onboarding | Sempre (ponto de entrada) | Todos os agentes + `users/<id>/perfil.md` |
| **raio-x-financeiro** | Diagnóstico patrimonial integral (ativos, passivos, fluxo) | "Faça meu Raio-X" / onboarding pós-perfil | `perfil.md`, `orcamento-e-custos/` |
| **auditor-cartao-credito** | Auditoria de faturas, taxas, anuidades, rolagem | "Audite minha fatura" | `perfil.md`, `tributacao-e-trabalho/` |
| **estrategista-dividas-bacen** | Plano de negociação de dívidas, limpeza Serasa | "Tenho dívidas / restrição" | `perfil.md`, `mitos-e-falacias/` |
| **simulador-imobiliario-caixa** | Simulação SFH, FGTS, SAC/Price, custos D0 | "Simule financiamento / comprar imóvel" | `regulatorio-brasil/diretrizes-credito-imobiliario.md` |
| **arquiteto-investimentos-br** | Alocação, tributação (LCI/FII/FGC), ordem de aportes | "Onde investir / montar carteira" | `regulatorio-brasil/tributacao-investimentos-br.md`, `investimentos/` |
| **consultor-clt-pj-tributario** | Comparativo CLT vs. PJ, custo empregador, MEI | "CLT ou PJ? / abrir MEI" | `tributacao-e-trabalho/*` |
| **engenheiro-milhas-beneficios** | Milhas, pontos, anuidades, cashback vs. milhas, spread internacional | "Clube de pontos / anuidade / milhas" | `perfil.md`, `orcamento-e-custos/` |
| **avaliador-veicular-mobilidade** | TCO veicular, comprar vs. assinar vs. app, break-even KM/mês | "Comprar carro / carro por assinatura / Uber ou ter carro" | `prioridades-financeiras/ordem-reserva-carro-casa.md`, `regulatorio-brasil/diretrizes-direitos-bancarios-tarifas.md` · trava `TRAVA_ENTRADA_RESERVA` |
| **auditor-consorcio** | Auditoria de cota, lance embutido, consórcio vs. financiamento, desistência | "Vale a pena consórcio / auditar cota / desistir de consórcio" | `regulatorio-brasil/mecanica-consorcios-brasil.md`, `prioridades-financeiras/ordem-reserva-carro-casa.md` · bloqueio "sem juros" e lance com reserva |
| **ingestor-conteudo** | Captura e normalização de fontes externas | "Aprenda esta fonte" | `02-Base-Conhecimento-Global/` |
| **validador-conhecimento** | Filtro anti-mito antes de qualquerinclusão na base | Sempre após o ingestor | Bacen, CVM, matemática financeira, leis datadas |
| **skill-creator** | Geração de novos agentes especialistas | "Crie um agente de X" | `00-Orquestrador/cfo-mestre.md` (padrão) |
| **radar-antecipacao** | Varredura de sazonalidades (IPTU, IPVA, férias, 13º) | "Radar / o que vem por aí" | `perfil.md`, `prioridades-financeiras/` |

---

## 4. Pipeline de Ingestão e Governança Anti-Mito

Nenhum conhecimento entra na base sem passar pelo validador. Conselhos vazios ("invista em cripto", "compre agora") são bloqueados; erros detectados viram lições canônicas.

```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────────────────┐    ┌──────────────────────────┐
│ Fonte Externa   │───▶│ Ingestor de      │───▶│ Validador Anti-Mito         │───▶│ Base Conhecimento Global │
│ (livro, artigo, │    │ Conteúdo         │    │ (Bacen / CVM / Matemática   │    │ (inclusão somente se: datado, │
│  vídeo, aula)   │    │ (normalização)   │    │  / leis brasileiras)        │    │  citável, verificável)   │
└─────────────────┘    └──────────────────┘    └──────────────┬──────────────┘    └──────────────────────────┘
                                                              │
                                                              ▼ REPROVADO
                                               ┌──────────────────────────────┐
                                               │ mitos-e-falacias/            │
                                               │ (erro vira lição datada)     │
                                               └──────────────────────────────┘
```

**Critérios do validador (bloqueio automático):**
1. Sem fonte datação ou citável → reprova.
2. Alegação de retorno acima do benchmark de mercado sem lastro → reprova.
3. Contradição com regulamentação vigente (Bacen/CVM/Receita) → reprova e registra em `mitos-e-falacias/`.
4. Matemática inconsistente (juros compostos, equivalência de taxas) → reprova.

---

## 5. Quickstart — Instalação e Uso Rápido

### Passo 1 — Clonar e verificar o blindagem

```bash
git clone <repo-url> sampo
cd sampo
# OBRIGATÓRIO: confirmar que .gitignore contém a linha:
#   users/
```

Nunca versione `users/` — contém dados financeiros sensíveis do titular.

### Passo 2 — Onboarding (criação do perfil)

1. Abrir `00-Orquestrador/cfo-mestre.md`, copiar o conteúdo completo.
2. Colar em qualquer IA (Claude, etc.) e instruir: **"Inicie o Onboarding para criar meu perfil."**
3. O CFO conduzirá a ficha técnica até gerar `users/<id>/perfil.md`.

### Passo 3 — Chamadas de rotina (exemplos)

| Objetivo | Comando ao CFO |
|---|---|
| Auditoria de fatura | "Audite minha última fatura de cartão" → `auditor-cartao-credito` |
| Simulação habitacional | "Simule financiamento Caixa de R$ X com entrada Y e FGTS Z" → `simulador-imobiliario-caixa` |
| Comparativo profissional | "Compare CLT R$ X vs. PJ R$ Y" → `consultor-clt-pj-tributario` |
| Varredura sazonal | "Radar: o que vence nos próximos 90 dias?" → `radar-antecipacao` |
| Diagnóstico completo | "Faça meu Raio-X financeiro" → `raio-x-financeiro` |

### Passo 4 — Auto-expansão do sistema

Dizer ao CFO: **"Crie um agente especialista em [tema]"** → `skill-creator.md` gera novo arquivo em `01-Agentes-Especialistas/` seguindo o padrão de single responsibility + dependências declaradas na matriz (§3).

---

## 6. Regras de Ouro e Compliance Operacional

### O que o Sampo **NUNCA** faz:

| Vetado | Motivo |
|---|---|
| ❌ Executa transações financeiras reais (compras, vendas, transferências) | Sistema é analítico e consultivo — a decisão e a execução são do usuário |
| ❌ Promete ganhos acima de benchmarks de mercado | Qualquer promessa de retorno é mito — bloqueado pelo validador |
| ❌ Recomenda investimento em cenário de **juros rotativos de dívida** | Quitar dívida com taxa > rentabilidade esperada é prioridade absoluta (regra dos 40%) |
| ❌ Recomenda investimento com **dívida ativa / restrição Serasa** | Regularização precede alocação — domínio do `estrategista-dividas-bacen` |
| ❌ Substitui consultoria jurídica/contábil formal | Documentos datados são referência; decisões tributárias críticas exigem profissional habilitado |
| ❌ Versiona ou exfiltra dados de `users/` | Blindagem `.gitignore` é inegociável |

### Compliance operacional:
- Todo documento da base carrega **data de vigência** e **fonte legal** (Lei, Resolução CMN, decreto).
- Recomendações citam o agente e o artefato canônico que a sustentam.
- Dados do usuário nunca saem de `users/<id>/` — inclusive em respostas exportáveis.

---

> **Manutenção:** atualizar `README.md` sempre que um agente novo entrar na matriz (§3) ou uma nova subpasta canônica surgir em `02-Base-Conhecimento-Global/`.
