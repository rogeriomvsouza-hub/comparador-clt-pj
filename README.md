# Comparador CLT × PJ

Ferramenta web para comparar o salário líquido nos regimes CLT e PJ, calcular equivalência salarial e identificar o enquadramento no Simples Nacional pelo CNAE.

## Como usar

Baixe o arquivo `comparador-clt-pj.html` e abra diretamente no navegador — nenhuma instalação necessária.

## Funcionalidades

- **Recálculo em tempo real** a cada campo editado
- **CNAE com lookup automático** — identifica o Anexo do Simples Nacional e bloqueia o regime quando o CNAE não é elegível (45+ CNAEs mapeados)
- **Simples Nacional** — Anexos III, IV e V com alíquota efetiva sobre RBT12
- **Lucro Presumido** — ISS configurável (2–5%), PIS, COFINS, IRPJ, CSLL
- **CLT completo** — INSS 2024/2025 progressivo, IRRF, 13º, férias + 1/3, FGTS, PLR
- **Pro-labore PJ** — INSS contribuinte individual 11% + patronal 20% (LP e Simples IV)
- **Equivalência salarial** — busca por bissecção o salário CLT equivalente ao líquido PJ e vice-versa
- **Comparativo visual** — gráfico de barras mensal/anual (Chart.js)
- **Banner de resultado** — destaca qual regime é mais vantajoso e a diferença anual
- Formatação monetária brasileira (`1.234,56`)

## Cálculos implementados

| Item | Detalhe |
|---|---|
| INSS CLT | Progressivo 2024/2025 — faixas 7,5% / 9% / 12% / 14%, teto R$ 908,87 |
| IRRF | Tabela progressiva — isento até R$ 2.259,20 |
| PLR | Tabela exclusiva Lei 10.101/2000 — isento até R$ 7.640 |
| Simples III | 6% a 33% sobre RBT12 |
| Simples IV | 4,5% a 33% sobre RBT12 |
| Simples V | 15,5% a 30,5% sobre RBT12 |
| Lucro Presumido | Presunção 32% — IRPJ 15% + adicional 10%, CSLL 9%, PIS 0,65%, COFINS 3% |

## Tecnologias

- HTML + CSS + JavaScript puro (sem frameworks, sem build)
- [Chart.js 4.4.3](https://www.chartjs.org/) via CDN
- [Inter](https://fonts.google.com/specimen/Inter) via Google Fonts

## Premissas fiscais

- Lucros PJ distribuídos **isentos de IR** — Lei 9.249/1995, art. 10
- INSS patronal (CPP) 20% incide sobre pro-labore no **Lucro Presumido** e no **Simples Anexo IV**
- Simples Anexo V com **Fator R**: se pro-labore ≥ 28% da RBT, pode migrar para Anexo III
- 13º e férias calculados sobre a base fiscal ajustada (com outros proventos/descontos)
- FGTS exibido como informativo — depositado pelo empregador, não compõe o líquido

---

Desenvolvido por [Rogério Souza](https://github.com/rogeriomvsouza-hub)
