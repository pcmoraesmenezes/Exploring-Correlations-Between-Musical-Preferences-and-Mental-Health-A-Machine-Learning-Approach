# Etapas

## Etapa 1

Essa primeira etapa está sendo desenvolvida no dia 02/11/2023. Ela será concluída até o dia 10/11/2023. 

Essa primeira etapa consiste em:

- Definir e escolher a base de dados que será utilizada no projeto.

- Definir e escolher a metodologia que será utilizada no projeto.

- Definir e escolher as ferramentas que serão utilizadas no projeto.

Ao término, será feita uma apresentação presencial para o professor da disciplina, onde será apresentado o que foi feito até o momento.

Estes são os tópicos que pretendo abordar na apresentação:

1. Introdução:

- Se apresentar
- Falar brevemente sobre a base de dados escolhida.

2. Motivação da escolha + base de dados escolhida

- Motivação da base de dados escolhida
- Apresentação da base de dados escolhida

3. Objetivo

- Qual o objetivo da analise? (produzir um artigo e resolver o problema em aberto)

4. Metodologia

- Quais tecnicas serão usadas para alcançar os objetivos
5. Conclusão

- Como a resolução desse problema pode ser útil (tanto em um contexto individual como coletivo)

Ao término da primeira etapa, será públicado um relatório no repositório do projeto, contendo o que foi feito até o momento.

A etapa 1 foi concluída no dia 10/11/2023, a base de dados escolhida foi a [Music x Mental Health](/base_de_dados/mxmh_survey_results.csv), ou pode ser encontrada nesse [Link](https://www.kaggle.com/datasets/catherinerasgaitis/mxmh-survey-results).

A apresentação da etapa 1 pode ser encontrada [aqui](/etapas/ESCOLHA%20DO%20TEMA.pdf).

Basicamente o que foi definido na etapa 1 foi:

- As variaveis alvo: Ansiedade, Insonia, Depressão e Transtorno Obsessivo Compulsivo.

- Através dessas variaveis alvo será feita uma analise exploratória, e será feita uma analise de correlação entre o restante das variaveis.

- O objetivo definido foi de criar um modelo de machine learning que consiga prever se uma pessoa tem ou não tem algum dos problemas citados acima, baseado nas respostas do questionário. Ou seja a partir do gênero musical mais ouvido, idade, etc, o modelo deve ser capaz de prever se a pessoa tem ou não tem algum dos problemas citados acima. Lembrando que a base de dados não possuí uma variavel informando se a pessoa tem ou não, na verdade ela possuí uma coluna para o nível de ansiedade, outra para o nível de insonia, etc. Então o que será feito é o seguinte, se o nível de ansiedade for maior que 5, então a pessoa tem ansiedade, se o nível de insonia for maior que 5, então a pessoa tem insonia, etc. Ou seja, o modelo será treinado para prever se a pessoa tem ou não tem algum dos problemas citados acima, baseado no nível de ansiedade, insonia, etc.

- A base de dados conta com 736 entradas e 33 colunas.

- O maior objetivo dessa base de dados é verificar uma correlação entre o gênero musical mais ouvido e os problemas citados acima. Por exemplo, será que pessoas que ouvem mais rock tem mais ansiedade? Será que pessoas que ouvem mais pop tem mais insonia? Será que pessoas que ouvem mais rap tem mais depressão? Será que pessoas que ouvem mais eletrônica tem mais transtorno obsessivo compulsivo? E assim por diante.

- Os resultados esperados até o fim da analise são: Espera-se identificar relações significativas entre o gênero musical mais ouvido e os problemas citados acima, e também através da produção e escrita do artigo científico, espera-se que o mesmo seja aceito em alguma conferência ou revista científica.

Com isso terminamos a etapa 1, e agora vamos para a etapa 2.

---

Antes de dar início a etapa 2, uma coisa é importante de se observar, no **[Código](/código/main.ipynb)** vemos que os casos de ansiedade fica bem distribuido para niveis maiores iguais a 6 e niveis menores que 6, depressão mantém a mesma faixa, insonia e transtorno obssessivo compulsivo não estão bem distribuídos, então teremos que fazer um balanceamento dos dados, para que o modelo não fique enviesado. Também será crucial a leitura de artigos relacionados ao tema, para que possamos definir uma métrica de nível, ou seja a partir de qual valor de nível de ansiedade, insonia, depressão e transtorno obsessivo compulsivo, o modelo irá prever que a pessoa tem ou não tem o problema. Possívelmente, as métricas poderão ser distintas para cada problema, por exemplo, para ansiedade, o modelo poderá prever que a pessoa tem ansiedade se o nível de ansiedade for maior que 5, para insonia, o modelo poderá prever que a pessoa tem insonia se o nível de insonia for maior que 4, para depressão, o modelo poderá prever que a pessoa tem depressão se o nível de depressão for maior que 6, e para transtorno obsessivo compulsivo, o modelo poderá prever que a pessoa tem transtorno obsessivo compulsivo se o nível de transtorno obsessivo compulsivo for maior que 4. Mas isso só será definido após a leitura de artigos relacionados ao tema.

Então antes do início da etapa 2, o foco estará na leitura de artigos relacionados ao tema.