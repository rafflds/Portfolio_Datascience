# <font size=20 color=Teal>Algoritmos Supervisionados(Python)

## Índice

- [Documentação](#Documentação)
- [Análise Exploratória de Dados](#Análise-Exploratória-de-Dados)
- [Pré-Processamento de Dados](#Pré-Processamento-de-Dados)
- [Desenvolvimento de Modelos:](#Desenvolvimento-de-Modelos:)
- [Avaliação de Modelos](#Avaliação-de-Modelos)  
- [Visualização de Resultados](#Visualização-de-Resultados)

***
## Documentação
***
<font size=5>**Bibliotecas utilizadas:**
- **Pandas**
- **Pickle**
- **Sklearn** (Pipeline, SimpleImputer, StandardScaler, KNeighbors, classification_report, DecisionTreeClassifier, RandomForestClassifier, SVC, GridSearchCV)
- **scipy** (shapiro)
- **Seaborn, Matplotlib, Yellowbrick**(ConfusionMatrix), **Warnings**

<font size=5>**Descrição do problema:**
> Criar e treinar uma máquina, para indica se a pessoa é, uma boa ou má pagadora de empréstimos. Base de dados bastante simples, não ocorreu nenhuma dificuldade.



<font size=5>**Solução:**
1. **Separar o projeto por etapas** (para melhorar a compreenção).
2. **Análise Exploratória de Dados**
  * Visualizar os dados da base. Dados todos numericos, havia uma coluna chamada 'id' que foi retirada. Foi realizado a mudança do nome das colunas para maior compreenção.
  * Quantidade de registros, tirar uma base estatística
  * Verificar os valores faltantes. Havendo 3 na coluna 'idade'
3. **Pré-Processamento de Dados**
  * Foi verificado os valores faltantes. Encontrado 3 na coluna 'idade'. Substituido os valores faltantes pela média dos registros (idade). Na mesma coluna existia valores com idades negativa. O tratamento foi a substituição dos dados negativos por positivos

  * Separei o a base de dados em 2 variáveis: 'data' e 'label'. Label é a variável dependente que você está tentando prever com base nas features. Depois usei a biblioteca do **Sklearn (train_test_split)**, para realizar as amostras de treino e teste. Foram separadas 30% para teste, o restantes (70%), será treinado.

  * Usar a biblioteca **'Pickle'**, para criar uma nova base de dados, com o devido tratamento já realizado. Está nova base de dados criada, será usada para o aprendizado de máquina dos modelos seguintes.

4. **Desenvolvimento de Modelos:**
  * 1° Modelo usado foi **K-Nearest Neighbour**. Peguei a base de dados salvar anteriormente, treinei o modelo em cima desta base. Optei por criar de Pipeline com o sequência de etapas de processamento e normalização dos dados. Salvei o modelo para agilizar testes futuros.

  * Ocorreu os mesmos passo realizados anteriormente, nestes modelos: **Decision Tree, Random Forest, SVC.**

  * Para via de comparação, decidir usar a biblioteca **GridSearch**. Com base em seus resultados, deu para análisar se obtive bons resultados com as minha escolhas de parâmetros.

5. **Avaliação dos Modelos**  
> Resultados dos modelos por ordem crescente (com parâmetros escolhidos por mim):
 - 1° Random Forest - 98.6%
 - 2° KNN, SVM - 98.3%
 - 3° Decision Tree - 98.1%

> Resultados dos modelos por ordem crescente (com parâmetros escolhidos por GridSearch):
  - 1° Random Forest - 99%  (superior)
  - 2° Decision Tree - 98.7%  (superior)
  - 3° SVM - 94.5%  (pior q o meu modelo, além de ser muito lento)
  - 4° KNN - 85.5% (pior modelo treinado pelo GridSearch)







