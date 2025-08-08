#  Previsão de Diabetes com Aprendizado de Máquina

Este projeto foi desenvolvido com o objetivo de aplicar técnicas de Ciência de Dados para prever a ocorrência de **diabetes** a partir de variáveis clínicas. A proposta é simular um **pipeline real de machine learning**, desde a análise exploratória até a validação estatística de modelos otimizados.

>  Projeto 100% desenvolvido de forma independente, com foco em desempenho, interpretabilidade e aplicabilidade clínica.

---

##  Visão Geral

- **Tipo de problema**: Classificação binária
- **Dataset**: Público (PIMA Indians Diabetes Database - 768 registros)
- **Objetivo**: Prever a presença de diabetes com base em características como glicose, idade, IMC, etc.

---

##  Etapas do Projeto

###  1. Análise Exploratória de Dados (EDA)
- Avaliação de distribuições por variável
- Verificação de desbalanceamento da variável-alvo
- Análise de correlações
- Boxplots por classe

###  2. Pré-processamento
- Substituição de valores clinicamente inválidos por `NaN`
- Imputação com `KNNImputer`
- Tratamento de outliers via IQR
- Normalização (`MinMaxScaler`)
- Split estratificado em treino e teste

###  3. Modelagem
Modelos treinados, otimizados e validados:
- ** Regressão Logística**
- ** Decision Tree**
- ** Random Forest**
- ** KNN**
- ** AdaBoost**
- ** Voting Classifier (Hard/Soft)**
- ** Stacking Classifier**

###  Técnicas Avançadas
- Validação cruzada com `StratifiedKFold`
- Otimização de hiperparâmetros com `BayesSearchCV`
- Tratamento de desbalanceamento com `SMOTE` e `NearMiss`
- Ajuste de thresholds personalizados

---

##  Resultados

###  Métricas com Thresholds Otimizados (Classe Positiva - Diabetes)

| Modelo               | Threshold | Accuracy | Precision | Recall | F1-Score | AUC    |
|----------------------|-----------|----------|-----------|--------|----------|--------|
| Regressão Logística  | 0.42      | 0.74     | 0.57      | 0.94   | 0.72     | 86.58% |
| Random Forest        | 0.44      | 0.77     | 0.63      | 0.89   | 0.73     | 87.82% |
| Voting               | 0.42      | 0.73     | 0.57      | 0.91   | 0.70     | 87.13% |
| Stacking             | 0.28      | 0.76     | 0.61      | 0.90   | 0.73     | 87.00% |

>  *Random Forest foi o modelo com melhor desempenho geral.*
>  *Regressão Logística apresentou maior recall — ideal para contextos clínicos sensíveis.*

---

##  Teste Estatístico (McNemar)
Foi aplicado o **teste de McNemar** para verificar se havia diferença significativa entre Random Forest e Stacking:

- **p-valor = 0.8312**
-  *Não houve diferença estatisticamente significativa entre os dois modelos.*

---

##  Principais Bibliotecas Utilizadas

- `scikit-learn`
- `imblearn`
- `matplotlib`, `seaborn`, `plotly`
- `pandas`, `numpy`
- `statsmodels`
- `scikit-optimize (skopt)`

---

##  Conclusão

Este projeto demonstra um pipeline robusto, com preocupação em:
- Integrar **técnicas clássicas e modernas** de ML
- Garantir **avaliabilidade e desempenho**
- Aplicar **validação estatística** para decisões fundamentadas

>  **Random Forest** e **Regressão Logística** com thresholds ajustados são as melhores escolhas dependendo do objetivo clínico (precisão vs. recall).

---

## Estrutura do Projeto

```
 previsao-diabetes/
├── data/                # Dataset original
├── notebooks/           # Notebooks por etapa
├── modelos/             # Modelos otimizados
├── plots/               # Gráficos gerados
├── README.md
└── requirements.txt

---

##  Autor

Desenvolvido por Laís Araújo
