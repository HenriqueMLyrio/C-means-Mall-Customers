# C-means-Mall-Customers
## Alunos:
-  Felipe Leão
-  Danilo Scheltes
-  Henrique Lyrio
-  Rafael Santos
## Objetivos:
O objetivo é segmentar clientes com base em idade e renda anual utilizando o algoritmo Fuzzy C-Means (FCM). O número de clusters é definido utilizando a métrica Silhouette Score, e o modelo atribui a cada cliente uma pertinência a cada cluster.
## Passo a passo:
### 1. Carregar o Dataset e Ajustar os Dados
Carregamos o dataset usando o `pandas` a partir do arquivo CSV, disponivel no `kaggle`. Em seguida, selecionamos as primeiras 200 linhas para realizar a análise.
Tratamos os dados ajustando os valores negativos nas colunas `Age` e `Annual Income (k$)`, substituindo-os pela média dessas variáveis. Também preenchemos valores ausentes com a média.
### 2. Escalonamento dos Dados
Utilizamos o `MinMaxScaler` da `sklearn` para normalizar os dados, escalonando as variáveis Age e Annual Income (k$) para o intervalo de 0 a 1. Esse processo é importante para evitar que as variáveis com maiores escalas dominem as distâncias no KMeans.
### 3. Cálculo do Silhouette Score
Para determinar o número ideal de clusters, implementamos uma função que calcula o `Silhouette Score` para diferentes números de clusters, variando de 2 a 10. O Silhouette Score avalia a qualidade da separação entre os clusters, e o número de clusters com o maior Silhouette Score é considerado o melhor.
### 4. Treinamento do Modelo C-Means
Usamos a implementação do Fuzzy C-Means (FCM) para realizar a segmentação dos dados. O FCM permite que cada ponto de dados pertença a múltiplos clusters com diferentes graus de pertinência.
### 5. Visualização dos Resultados
Geramos um gráfico de barras que mostra os Silhouette Scores para diferentes números de clusters, permitindo visualizar o número de clusters ideal.
Em seguida, geramos um gráfico de dispersão que exibe os clusters encontrados pelo KMeans, com cada cluster representado por uma cor diferente e os centróides dos clusters marcados.
### 6. Avaliar a Qualidade do Modelo
Após o treinamento, avaliamos o modelo usando o Silhouette Score para garantir que a segmentação dos clientes esteja bem definida. A visualização dos clusters também ajuda a entender a distribuição dos dados.
