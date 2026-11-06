# Credit Card Fraud Detection | Machine Learning

## Sobre o Projeto

Este projeto tem como objetivo desenvolver e avaliar modelos de Machine Learning para identificar transações fraudulentas com cartões de crédito, utilizando técnicas de análise exploratória de dados (EDA), pré-processamento e classificação supervisionada.

O principal desafio consiste no forte desbalanceamento entre as classes, uma característica comum em problemas de detecção de fraudes financeiras. Nesse cenário, a escolha das métricas de avaliação é fundamental para medir a capacidade dos modelos de identificar transações fraudulentas sem gerar um volume excessivo de falsos positivos.

## Objetivos

- Explorar e compreender os dados por meio de Análise Exploratória de Dados (EDA).
- Identificar padrões e características associados às transações fraudulentas.
- Investigar o desbalanceamento entre as classes.
- Comparar diferentes algoritmos de classificação.
- Avaliar o desempenho dos modelos utilizando métricas adequadas para problemas de classificação desbalanceada.
- Selecionar e refinar o modelo com melhor desempenho.

## Tecnologias e Bibliotecas

- **Python:** linguagem utilizada no desenvolvimento.
- **Pandas e NumPy:** manipulação e preparação dos dados.
- **Matplotlib e Seaborn:** visualização e análise gráfica.
- **Scikit-learn:** pré-processamento, treinamento e avaliação dos modelos.
- **SciPy:** aplicação de testes estatísticos.
- **Jupyter Notebook / Google Colab:** ambiente de desenvolvimento.

## Dataset

O conjunto de dados utilizado possui:

- 284.807 transações financeiras.
- 31 variáveis.
- 492 transações fraudulentas.
- 284.315 transações legítimas.

As variáveis V1 a V28 correspondem a atributos transformados por PCA. As demais variáveis incluem:

- **Time:** tempo decorrido entre cada transação e a primeira transação do conjunto de dados.
- **Amount:** valor da transação.
- **Class:** variável-alvo, sendo 0 para transações legítimas e 1 para transações fraudulentas.

O conjunto apresenta forte desbalanceamento, com aproximadamente 0,17% de transações fraudulentas.

## Etapas do Projeto

### 1. Análise Exploratória de Dados (EDA)

- Análise da estrutura e consistência dos dados.
- Verificação de valores ausentes.
- Análise da distribuição da variável-alvo.
- Identificação de variáveis numéricas e categóricas.
- Investigação de outliers utilizando o método IQR.
- Análise de distribuições, correlações e relações entre variáveis.
- Aplicação do teste estatístico Mann-Whitney U para comparação dos valores das transações.

### 2. Pré-processamento

- Verificação e tratamento de valores ausentes.
- Padronização das variáveis Time e Amount.
- Análise de valores extremos, preservando os outliers potencialmente relevantes para a identificação de fraudes.
- Separação entre variáveis preditoras e variável-alvo.
- Divisão dos dados em conjuntos de treinamento e teste com amostragem estratificada.

### 3. Modelagem

Foram desenvolvidos e comparados três algoritmos de classificação:

- Regressão Logística (Logistic Regression).
- Árvore de Decisão (Decision Tree).
- Random Forest.

Os modelos foram configurados com `class_weight='balanced'` para considerar o desbalanceamento entre as classes.

Após a comparação inicial, o Random Forest foi selecionado para uma etapa adicional de refinamento de hiperparâmetros.

### 4. Avaliação dos Modelos

Foram utilizadas as seguintes métricas:

- **Accuracy:** proporção de classificações corretas.
- **Precision:** proporção de fraudes identificadas que realmente eram fraudes.
- **Recall:** capacidade de identificar as transações fraudulentas.
- **F1-score:** equilíbrio entre precisão e recall.
- **AUC-ROC:** capacidade de discriminação entre as classes.

Também foram utilizadas a matriz de confusão e a curva ROC para avaliar o desempenho do modelo final.

## Resultados

O modelo Random Forest refinado apresentou os seguintes resultados registrados no notebook:

| Métrica | Resultado |
|---|---:|
| Acurácia | 99,91% |
| Precisão | 78,38% |
| Recall | 80,56% |
| F1-score | 79,45% |
| AUC-ROC | 97,84% |

O resultado demonstra uma boa capacidade de discriminação entre transações legítimas e fraudulentas, mantendo um equilíbrio entre a identificação de fraudes e a redução de falsos positivos.

## Conclusão

O projeto demonstrou a aplicação de técnicas de Ciência de Dados e Machine Learning em um problema relevante do setor financeiro.

A comparação entre os algoritmos permitiu identificar o Random Forest como o modelo de melhor desempenho geral na avaliação inicial. Posteriormente, o modelo foi refinado e apresentou resultados consistentes nas métricas de classificação.

O estudo reforça a importância da análise exploratória, do tratamento adequado dos dados e da escolha de métricas específicas para problemas com classes desbalanceadas.

## Estrutura do Repositório

```text
credit-card-fraud-detection/
│
├── Trabalho_final.ipynb
├── Base_M43_Pratique_CREDIT_CARD_FRAUD.csv
└── README.md
```

## Como Executar

1. Clone o repositório:

```bash
git clone URL_DO_REPOSITORIO
```

2. Instale as bibliotecas necessárias:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy jupyter
```

3. Disponibilize o arquivo CSV na mesma pasta do notebook.

4. Abra o Jupyter Notebook:

```bash
jupyter notebook
```

5. Execute as células do notebook em sequência.

---

**Projeto desenvolvido para aplicação prática de conceitos de Análise de Dados, Estatística e Machine Learning em detecção de fraudes financeiras.**
