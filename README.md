# Amazon Product Performance & Customer Insights

**Tech Challenge — Fase 4 · Pós-graduação em Data Analytics (FIAP POSTECH) · Grupo 12**

Dashboard em Power BI, análise estatística e machine learning sobre **1.348 produtos** e **9.255 avaliações** de um marketplace, para responder onde a liderança deve concentrar a atenção comercial.

## Principal resultado

**Mais desconto não gera mais tração.** Dois grupos de produtos com desconto quase igual (58% e 61%) têm resultados opostos: um acumula **28 vezes mais avaliações** que o outro, e o grupo com menos avaliações é o único com nota abaixo do limiar de satisfação (3,9 contra 4,2).

| Achado | Número | Ação recomendada |
| --- | --- | --- |
| Risco de vitrine | **19 produtos** muito avaliados e com nota abaixo de 4,0 | Revisão prioritária, lista nominal no painel |
| Potencial subexplorado | **61 produtos** bem avaliados e pouco comentados (187 pela nota bruta, 126 descartados pela correção de Wilson) | Testar mais exposição |
| Concentração do engajamento | **22,7% do catálogo** (306 produtos) concentra 80% das avaliações | Governança focada nesses produtos |
| Insatisfação localizada | **25,1%** do catálogo tem nota abaixo de 4,0; fones (52,4%) e climatização (37,9%) lideram | Começar a revisão por essas subcategorias |

Correlação entre desconto e nota: ρ = −0,150 (p = 3,1 × 10⁻⁸). A associação é real, mas fraca.

## O que o projeto entrega

- **Dashboard Power BI** com página inicial e sete páginas analíticas em cinco áreas, com filtros sincronizados (categoria, faixa de desconto, engajamento e satisfação) e drill-through com a ficha de cada produto.
- **Medidas DAX conferidas com Python:** cada medida tem um valor de referência calculado em Python, e um validador com **107 asserções** falha se algum número divergir da base de origem.
- **Machine learning:**
  - Classificação de atributos ligados à baixa satisfação (AUC 0,70 ± 0,01 em validação cruzada agrupada).
  - Segmentação descritiva do catálogo em 4 perfis comerciais com k-means (preço, desconto, volume e nota).
  - Contraste de termos por TF-IDF entre avaliações de nota baixa e alta (Customer Insights).
- **Relatório técnico** (107 páginas), **sumário executivo** (2 páginas), **manual de leitura do dashboard** e **vídeo executivo**.

## Ferramentas

Power BI (DAX, Power Query), Python (pandas, Scikit-learn), estatística (correlação de Spearman com correção de Bonferroni, intervalo de Wilson), NLP (TF-IDF).

## Arquivos

| Arquivo | Conteúdo |
| --- | --- |
| `TC4.1.pbix` | Dashboard. Abra no Power BI Desktop; os dados já estão carregados no arquivo. |
| `executive_summary_phase4_v1_powerbi.pdf` | Sumário executivo em 2 páginas |
| `technical_report_phase4_v1_powerbi.pdf` | Relatório técnico completo |
| `manual_leitura_dashboard_v1.pdf` | O que cada elemento de cada página representa e como lê-lo |
| `LEIA-ME.txt` | Instruções originais da entrega |

## Links

- Vídeo executivo (5:57): <https://www.youtube.com/watch?v=1njmpUPOe9c>
- Código, notebooks e validações do grupo: <https://github.com/lgmricardo/Techchallenge4-G12>
- Versão publicada no Power BI online (exige conta FIAP): [abrir](https://app.powerbi.com/links/Xz4qIpwkDQ?ctid=11dbbfe2-89b8-4549-be10-cec364e59551&pbi_source=linkShare)

## Como navegar no dashboard

- A barra no topo de cada página leva a qualquer outra. No Power BI Desktop, use Ctrl + clique nos botões.
- Os quatro filtros das páginas 2a, 2b, 2c e 3 valem para as quatro páginas ao mesmo tempo.
- Para ver a ficha de um produto: botão direito numa linha das listas da página 2b > Detalhamento > Detalhe do produto.

## Limitações da base

- **Não há variável de venda.** `rating_count` é volume de avaliações, nunca receita ou demanda. Nenhuma recomendação é expressa em dinheiro.
- O texto vem limitado a **até 8 avaliações por produto**, então Customer Insights descreve o que aparece na vitrine.
- **97,2% do portfólio** está em três famílias: Electronics, Home & Kitchen e Computers & Accessories.
- Valores em rupia indiana, sem conversão.

## Fonte dos dados

[Amazon Sales Dataset](https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset) (Kaggle).

## Grupo 12

Efraim Oliveira · Érica Tarsis · Ricardo Moraes · Rodrigo Bernardino · Thiago Galvão
