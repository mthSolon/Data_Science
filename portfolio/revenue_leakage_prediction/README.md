# English
The project was made in a jupyter notebook (.ipynb). In the project, I created a solution that predicts customer booking cancelation in a hotel and analyze the financial impact of the solution in the revenue leakage. Below, I make a brief summary about the main sections in the notebook.

## 1. **Package Installation and Library Import:**
   - The code begins by installing the `CatBoost` package and importing various libraries, such as `pandas`, `seaborn`, `matplotlib`, `sklearn`, and others for data manipulation, visualization, and implementation of machine learning models.
   - It sets themes for graphs and ignores irrelevant warnings.

## 2. **Data Description:**
   - The code describes the dataset variables, such as the number of adults, children, weekday and weekend nights, meal plan type, reserved room type, and several other characteristics related to guest reservations.

## 3. **Exploratory Data Analysis (EDA):**
1. **Graphical Visualizations:**
   - The code uses seaborn and matplotlib libraries to create graphs that help explore the distribution and correlations of the data.
   - For example, bar charts can be used to visualize the distribution of categorical variables, such as reserved room type or market segment.
   - Scatter plots and histograms can show the relationship between the average room price and the probability of cancellation, as well as analyze other numerical variables like lead_time (time in advance of the reservation).

2. **Outlier and Discrepancy Analysis:**
   - The code investigates potential outliers or unexpected patterns, which can be identified visually or through descriptive statistics.
   - This is crucial for better adjusting the model and ensuring that data variation is not affected by unrepresentative extreme values.

3. **Correlation between Variables:**
   - The EDA may include the analysis of a correlation matrix to identify which variables have the most influence on reservation cancellations.
   - Variables like lead_time and no_of_previous_cancellations likely have a strong correlation with the target variable (cancellation).

### **Conclusion of the Exploratory Analysis:**
EDA allows the identification of initial patterns, such as which customer groups are more likely to cancel their reservations, and provides valuable insights for selecting relevant features in the model.

## 4. **Data Preprocessing:**
   - Transformation of categorical and numerical variables using TargetEncoder and StandardScaler.
   - Splitting the data into training and test sets with train_test_split.
   - Defining pipelines to streamline the preprocessing and modeling workflow.

## 5. **Model Training:**
   - The code trains multiple classification models, such as `DecisionTreeClassifier`, `RandomForestClassifier`, `XGBClassifier`, and `CatBoostClassifier`, to predict whether a reservation will be canceled or not.
   - It performs RandomizedSearchCV for hyperparameter optimization in models like `CatBoostClassifier`.

## 6. **Model Evaluation:**
   - Evaluation using metrics such as accuracy, confusion matrix, classification_report, and cross_val_score to gain insights into model performance.
   - Graphical display of the confusion matrix and decision tree (in the case of DecisionTreeClassifier).

## 7. **Lost Revenue Analysis:**
   - Based on the predictions, the code estimates the revenue loss for false positives (reservations predicted to be canceled but were not) and false negatives (reservations not predicted to be canceled but were).
   - It applies a lost revenue calculation using hypothetical discounts for these groups.

## 8. **Conclusion and Financial Impact:**
   - It calculates the final impact of avoided revenue loss using correct predictions, with different approaches and models, highlighting potential revenue savings of approximately €152,881.62.
   - It explores alternatives such as increasing discounts and using the XGBoost model to maximize profit.

**This analysis, in addition to training and evaluating models, integrates a practical analysis of the financial impact of predictions, which is crucial in revenue leakage problems.**"

# Português
O projeto foi feito em um arquivo jupyter notebook (.ipynb). No projeto, Eu criei uma solução que prevê o cancelamento de reservas em um hotel e analiso o impacto financeiro da solução no vazamento de receita do hotel.
Abaixo eu faço um resumo sobre as principais seções encontradas no notebook.

## 1. **Instalação de Pacotes e Importação de Bibliotecas:**
   - O código começa instalando o pacote `catboost` e importando diversas bibliotecas, como `pandas`, `seaborn`, `matplotlib`, `sklearn` e outras para manipulação de dados, visualização e implementação de modelos de machine learning.
   - Define temas para gráficos e ignora warnings irrelevantes.

## 2. **Descrição dos Dados:**
   - O código descreve as variáveis do dataset, como número de adultos, crianças, noites de semana e fim de semana, tipo de plano de refeição, tipo de quarto reservado, e várias outras características relacionadas às reservas dos hóspedes.
   

## 3. **Análise Exploratória de Dados (EDA):**
1. **Visualizações Gráficas:**
   - O código utiliza as bibliotecas `seaborn` e `matplotlib` para criar gráficos que ajudam a explorar a distribuição e correlações dos dados.
   - Por exemplo, gráficos de barras podem ser usados para visualizar a distribuição de variáveis categóricas, como tipo de quarto reservado ou segmento de mercado.
   - Gráficos de dispersão e histograma podem mostrar a relação entre o preço médio por quarto e a probabilidade de cancelamento, além de analisar outras variáveis numéricas, como `lead_time` (tempo de antecedência da reserva).

2. **Análise de Outliers e Discrepâncias:**
   - O código investiga possíveis outliers ou padrões inesperados, que podem ser identificados visualmente ou através de estatísticas descritivas.
   - Isso é crucial para ajustar melhor o modelo e garantir que a variação nos dados não seja afetada por valores extremos não representativos.

3. **Correlação entre Variáveis:**
   - A EDA pode incluir a análise de uma matriz de correlação para identificar quais variáveis têm maior influência sobre o cancelamento de reservas.
   - Variáveis como `lead_time` e `no_of_previous_cancellations` provavelmente possuem forte correlação com a variável alvo (cancelamento).

### **Conclusão da Análise Exploratório:**
A EDA permite identificar padrões iniciais, como quais grupos de clientes estão mais propensos a cancelar suas reservas, e fornece informações valiosas para a seleção de características (features) relevantes no modelo.

## 4. **Pré-processamento de Dados:**
   - Transformação de variáveis categóricas e numéricas usando `TargetEncoder` e `StandardScaler`.
   - Divisão dos dados em conjunto de treinamento e teste com `train_test_split`.
   - Definição de pipelines para facilitar o fluxo de pré-processamento e modelagem.

## 5. **Treinamento de Modelos:**
   - O código treina múltiplos modelos de classificação, como `DecisionTreeClassifier`, `RandomForestClassifier`, `XGBClassifier`, e `CatBoostClassifier`, para prever se uma reserva será cancelada ou não. 
   - Realiza `RandomizedSearchCV` para otimização de hiperparâmetros em modelos como o `CatBoostClassifier`.

## 6. **Avaliação dos Modelos:**
   - Avaliação usando métricas como acurácia, matriz de confusão, `classification_report`, e `cross_val_score` para obter insights sobre a performance dos modelos.
   - Exibição gráfica da matriz de confusão e árvore de decisão (no caso do `DecisionTreeClassifier`).

## 7. **Análise da Receita Perdida:**
   - Com base nas previsões, o código estima a perda de receita para os falsos positivos (reservas previstas como canceladas, mas que não foram) e falsos negativos (reservas não previstas como canceladas, mas que foram).
   - Aplica um cálculo de receita perdida usando descontos hipotéticos para esses grupos.
   
## 8. **Conclusão e Impacto Financeiro:**
   - Calcula o impacto final da receita evitada usando as previsões corretas, com diferentes abordagens e modelos, destacando uma economia de receita potencial de aproximadamente €152.881,62.
   - Explora alternativas como aumentar descontos e utilizar o modelo `XGBoost` para maximizar o lucro.

**Essa análise, além de treinar e avaliar modelos, integra uma análise prática do impacto financeiro das previsões, algo crucial em problemas de revenue leakage.**