# Regras PJ — Simples Nacional, Custos Operacionais e MEI

> Arquivo: `02-Base-Conhecimento-Global/tributacao-e-trabalho/regras-pj-simples-mei.md`
> Papel: Ground Truth canônico para `01-Agentes-Especialistas/consultor-clt-pj-tributario.md` e demais agentes
> Base legal datada: LC 123/2006 (Simples Nacional, Anexos III e V); Lei Complementar 128/2008 (Fator R, redação atual); Lei 14.803/2024 (MEI — teto anual de R$ 81.000,00 para 2024–2025)
> ⚠️ Revalidação: valores monetários e limites são ano-base 2025 — agente deve citar ano-base e solicitar atualização (teto MEI, DAS, alíquotas) se a execução for em ano posterior

---

## 1. Arquitetura do Simples Nacional — Prestadores de Serviços Intelectuais

### Fator R (Lei 128/2008)

```
Fator R = Folha de Pagamento dos últimos 12 meses (Pró-Labore + encargos patronais sobre pró-labore)
          / Receita Bruta dos últimos 12 meses (RBT12)
```

### Regra de enquadramento

| Condição | Anexo | Alíquota inicial (1ª faixa, RBT12 ≤ R$ 180.000) |
|---|---|---:|
| Fator R ≥ 28% | **Anexo III** | 6,00% (com redutor: RBT12×Tabela/288.000; piso efetivo ≈ 6,00%) |
| Fator R < 28% | **Anexo V** | 15,50% (com redutor da 1ª faixa; piso efetivo ≈ 15,50%) |

- Recálculo do Fator R: mensal, a cada competência; perda do percentual migra a PJ para o Anexo V retroagindo ao início do ano-calendário — risco fiscal relevante.
- Anexos III e V têm tabelas progressivas por faixa de RBT12 (§1ª faixa citada acima); agentes devem usar a faixa correta da receita anual e aplicar o redutor legal.

### Estratégia de enquadramento lícito (Anexo III)

- Fixar **folha (pró-labore + encargos patronais) em ≥ 28% da receita bruta** para manter Fator R ≥ 28% e Anexo III.
- Precisão do cálculo: encargos patronais sobre pró-labore (INSS patronal 20% + RAT típico 1–2% + terceiros ≈ 5,8%) fazem a folha superar o pró-labore. Logo:
  - `folha = pró-labore × (1 + encargos_patronais)`;
  - `pró-labore necessário ≈ 28% / (1 + encargos) ≈ 22%–23% da receita` (com patronal sobre pró-labore apenas).
  - Versão simplificada (pró-labore = 28% da receita, patronal desconsiderada) **também** mantém Fator R ≥ 28% — folha resultante fica acima do mínimo. Ambas as rotas são válidas; agente deve explicitar qual usou e o encargos considerado.
- Os **72% (ou a parcela remanescente) da receita** são distribuíveis como **lucros isentos** (não tributados no IRPF), após o pagamento do DAS e do INSS do pró-labore.
- Pró-labore mínimo: ≥ 1 salário mínimo (obrigação societária/fiscal típica) — e o que for necessário para atingir o Fator R.
- Pró-labore é tributado: INSS do sócio (11% acima da faixa isenta na tabela do MEI próprio ou alíquota da tabela geral se optante) + IRPF progressivo (mesma lógica do CLT).

## 2. Custos Operacionais Fixos Obrigatórios de uma PJ

| Custo | Valor/marcação | Regra |
|---|---|---|
| Assessoria contábil | R$ 150,00 a R$ 300,00/mês (contabilidade digital, mercado 2025) | Custo mensal fixo; anualizar × 12 |
| Certificado Digital e-CNPJ | Renovação anual (provisão mensal = anual ÷ 12) | Obrigatório para assinatura de DAS, notas e gov.br PJ |
| Taxa de Fiscalização Municipal (TFE/TLF) | Anual, valor por alíquota municipal × receita estimada | Obrigatória na maioria dos municípios; conferir prefeitura |
| INSS do sócio sobre pró-labore | 11% sobre pró-labore (faixa isenta até ≈ 1 salário mínimo, tabela MEI-próprio) ou 14%–20% na tabela geral, conforme regime | Recolhimento obrigatório do sócio com pró-labore |
| DAS Simples Nacional | `alíquota efetiva (faixa correta do anexo) × receita bruta mensal` | Único guia unificado (federal + parcela estadual/municipal conforme anexo) |

**Fórmula de liquidez PJ:**
`Líquido Anual PJ = Receita Anual − Σ DAS − Σ Custos Fixos − INSS_prólabore − IRPF_prólabore` (lucros isentos não geram IRPF).

## 3. Legislação e Diretrizes do MEI

| Item | Regra (ano-base 2025) |
|---|---|
| **Teto de faturamento** | R$ 81.000,00/ano (Lei 14.803/2024, vigência 2024–2025). Proporcionalidade mensal se abertura no ano-calendário: `teto_proporcional = 81.000 × (meses_restantes / 12)` |
| **DAS-MEI** | Guia única fixa mensal (comércio/indústria, serviços e transportador); valores 2025 ≈ R$ 70–80/mês conforme CNAE (contribuição previdenciária + ICMS/ISS + FGTS) — valor exato: portal gov.br/mei, agente não inventa número |
| **Recolhimento** | Até o dia 20 do mês subsequente; atraso multa + juros |
| **Benefício previdenciário** | Aposentadoria por idade no salário mínimo (salvo contribuição complementar); sem tempo de contribuição adicional — DAS "pago sem uso" tem custo de oportunidade alto |
| **Atividades vedadas** | Lista positiva de CNAEs. **Vedação expressa a atividades regulamentadas e intelectuais**: advocacia, medicina, engenharia, arquitetura, contabilidade (como atividade principal), consultoria técnica e **TI consultiva** (desenvolvimento de software pode ser enquadrável sob CNAE específico — caso a caso; consultoria/analista de sistemas: verificar lista vigente antes de afirmar enquadramento) |
| **Auditoria de ociosidade** | Critério de cancelamento: MEI ativo com faturamento zero/no notas em ≥ 6–12 meses → prejuízo acumulado `= Σ DAS pagos sem faturamento`; recomendar **CANCELAMENTE** ou meta de ativação com prazo ≤90 dias |
| **Transição ao teto** | Faturamento projetado >80% do teto → alerta de migração para ME (Lucro Presumido) ANTES do fechamento do ano; perder o teto gera obrigações retroativas |

## 4. Regras de Uso para Agentes

1. Todo cálculo citar ano-base destas tabelas; sem ano-base, recusar resultado como fato.
2. Valores DAS/teto: confirmar no portal oficial se houver divergência — este arquivo é referência, não fonte primária de guia.
3. Fator R é calculado sobre **receita bruta** (não lucro) e **folha total** (não só pró-labore).
4. Lucros isentos só existem **depois** de pró-labore tributado + DAS — 100% da receita como distribuição é irregular.
5. Dado ausente → `— não disponível (fonte ausente: <arquivo>)` + pedido ao usuário/Orquestrador.
