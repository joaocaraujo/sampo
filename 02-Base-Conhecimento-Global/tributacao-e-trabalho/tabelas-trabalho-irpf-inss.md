# Tabelas de Trabalho — IRPF, INSS e Encargos CLT

> Arquivo: `02-Base-Conhecimento-Global/tributacao-e-trabalho/tabelas-trabalho-irpf-inss.md`
> Papel: Ground Truth canônico para `01-Agentes-Especialistas/consultor-clt-pj-tributario.md` e demais agentes
> Base legal datada: IRPF conforme Lei 15.270/2025 (tabela mensal vigente desde maio/2025); INSS conforme tabela progressiva vigente 2025; encargos conforme CLT/CF art. 7º
> ⚠️ Revalidação: conferir correção anual (variação salarial) antes de uso em ano-base posterior a 2025 — agente deve citar o ano-base em todo cálculo

---

## 1. Tabela Progressiva Mensal do IRPF (ano-base 2025)

| Base de cálculo mensal (R$) | Alíquota nominal | Parcela a deduzir (R$) |
|---|---:|---:|
| Até 2.428,80 (isenção — faixas 1 e 2 zeradas pela L. 15.270/2025) | 0% | 0,00 |
| De 2.428,81 até 2.826,65 | 7,5% | 182,16 |
| De 2.826,66 até 3.751,05 | 15% | 394,16 |
| De 3.751,06 até 4.664,68 | 22,5% | 675,49 |
| Acima de 4.664,68 | 27,5% | 908,73 |

**Dedução por dependente (mensal):** R$ 189,59 (ano-base 2025).

**Base de cálculo:**
`Base = Salário Bruto − Contribuição INSS − Dedução Dependentes (n × 189,59) − Pensão Alimentícia − Contrib. Previdência Oficial`

## 2. Tabela Progressiva de Contribuição INSS — Empregado CLT (ano-base 2025)

| Base de cálculo mensal (R$) | Alíquota nominal |
|---|---:|
| Até 1.518,00 | 7,5% |
| De 1.518,01 até 2.793,88 | 9% |
| De 2.793,89 até 3.751,05 | 12% |
| De 3.751,06 até 4.664,68 | 14% |
| Acima de 4.664,68 até o teto (8.157,41) | 14% |

- **Teto do salário de contribuição (2025):** R$ 8.157,41.
- **Desconto máximo INSS (2025):** ≈ R$ 950,43/mês (progressivo até o teto; acima do teto, permanece no teto).
- **Alíquota efetiva:** `INSS = Σ(faixa × alíquota)` sobre o salário bruto; `alíquota_efetiva = INSS / salário_bruto` (4 casas decimais). Nunca usar alíquota nominal isolada como desconto total.

## 3. Encargos e Benefícios Legais Obrigatórios (CLT)

| Item | Regra | Cálculo |
|---|---|---|
| **FGTS** | 8% mensal sobre a remuneração, pago pelo empregador (não descontado do empregado) | `FGTS anual = 8% × Σ remuneração bruta mensal (inclui 13º)` |
| **Multa rescisória** | 40% do total dos depósitos FGTS (sem correção) em rescisão sem justa causa | `multa = 0,40 × saldo_FGTS_acumulado` |
| **13º Salário** | 1/12 da remuneração integral por mês trabalhado no ano (1ª parcela até 30/11; 2ª até 20/12) | `13º_bruto = (meses_trabalhados / 12) × salário_bruto`; sujeito a INSS e IRRF na competência do pagamento |
| **Férias** | 30 dias de descanso a cada 12 meses (período aquisitivo) + 1/3 constitucional | `férias_brutas = salário_bruto + (salário_bruto / 3)` após 12 meses; indenizadas se não gozadas no período concessivo |
| **Aviso prévio** | 30 dias + 3 dias por ano de serviço, limitado a 90 dias total | `aviso = 30 + min(3 × anos_serviço, 60)` dias (máx. 90); indenizado = 1 salário proporcional; trabalhado mantém verbas normais |

## 4. Procedimento de Cálculo da Renda Líquida CLT

1. `INSS = Σ(tabela progressiva §2)` sobre salário bruto.
2. `Base IRPF = Salário Bruto − INSS − (n_dependentes × 189,59) − Pensão Alimentícia − Previdência Oficial`.
3. `IRPF Devido = (Base IRPF × Alíquota Nominal) − Parcela a Deduzir` (tabela §1; Base ≤ 2.428,80 → IRPF = 0).
4. `Salário Líquido Mensal = Salário Bruto − INSS − IRPF − Descontos de Benefícios (VR/VT/Plano de Saúde com coparticipação, se houver)`.
5. **Anualização do pacote CLT:**
   `Pacote Anual = 12 × Líquido + 13º_Líquido + Férias_Líquidas (+1/3) + FGTS (8% × bruto anual, marcar como valor com liquidez restrita) + Benefícios monetizados (VA/VR/Plano × 12)`.

**Regras de uso para agentes:**
- Todo cálculo citar ano-base das tabelas; tabela de outro ano → recalcular, nunca misturar.
- Dado de salário/pensão ausente → `— não disponível (fonte ausente: users/<id>/perfil.md)`.
- Percentuais acima são nominais/dedutíveis conforme fórmula — proibido aplicar alíquota máxima sobre bruto inteiro.
