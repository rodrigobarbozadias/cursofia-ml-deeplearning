# Segmentação de clientes com K-Means e redes neurais densas

Projeto desenvolvido como trabalho final da pós-graduação em **Analytics e Inteligência Artificial da FIA Business School**.

## Objetivo

Construir e comparar soluções de segmentação de clientes a partir de uma base de varejo com aproximadamente 3.900 registros, combinando aprendizado não supervisionado, engenharia de atributos e modelos de classificação.

O trabalho não trata os clusters como um resultado final isolado. A análise também investiga se as estruturas encontradas são estatisticamente coerentes, interpretáveis para o negócio e recuperáveis por modelos supervisionados.

## Abordagem

- preparação dos dados e análise exploratória;
- engenharia de atributos comportamentais e demográficos;
- segmentação com K-Means;
- comparação de soluções com diferentes valores de *k* por meio do silhouette score;
- redes neurais densas para avaliar a separabilidade dos clusters;
- regularização com dropout e L2, early stopping e redução da taxa de aprendizado;
- comparação com Regressão Logística, Random Forest, XGBoost, LightGBM e CatBoost;
- interpretação dos perfis de clientes e discussão das limitações metodológicas.

## Principais resultados

- **K=2** apresentou o maior silhouette score (0,5186), mas produziu uma segmentação excessivamente ampla para o objetivo do projeto.
- **K=3** ofereceu melhor equilíbrio entre separação, simplicidade e interpretação gerencial.
- A rede neural densa de referência atingiu **98,08% de acurácia de validação** para a solução com três clusters.
- A arquitetura regularizada para K=3 manteve **97,31% de acurácia** e alcançou **ROC-AUC macro de 0,9990**.
- Para K=6, as redes densas tiveram desempenho consideravelmente inferior, indicando uma estrutura mais difícil de recuperar com essa família de modelos.

Os resultados dos classificadores baseados em árvores para os rótulos derivados do K-Means são interpretados como evidência de separabilidade interna, e não como validação externa de um desfecho independente.

## Notebook

- [`Rodrigo_B_Dias_Cluster_TCC.ipynb`](./Rodrigo_B_Dias_Cluster_TCC.ipynb)

As saídas das células foram removidas da versão publicada para reduzir o tamanho do arquivo e permitir sua visualização direta no GitHub. O código completo, as etapas de modelagem e as interpretações em Markdown foram preservados.

## Tecnologias

Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, TensorFlow/Keras, Yellowbrick, XGBoost, LightGBM, CatBoost e Feature-engine.

## Estrutura analítica

1. análise exploratória e preparação da base;
2. construção das variáveis para segmentação;
3. avaliação de diferentes soluções de clustering;
4. validação das soluções K=6 e K=3 com redes neurais densas;
5. benchmarking com modelos clássicos e ensembles;
6. interpretação dos segmentos e reflexão sobre limitações e próximos passos.
