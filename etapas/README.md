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

---
### Informações sobre ansiedade

Foi feito uma pesquisa em alguns artigos relacionados a ansiedade, algumas informações úteis foram tiradas como por exemplo de que ansiedade é algo natural do ser humano, que o prepara para algumas situações como por exemplo antes de alguma prova, apresentação de trabalho etc. Nestes casos, trata-se de uma característica normal da vida dos indivíduos, ou seja, diante das situações difíceis, importantes ou novas é normal as pessoas apresentarem diferentes graus de ansiedade (Lucena-Santos, Pinto-Gouveia & Oliveira, 2015).

Entretanto, essa função evolutiva pode perder a sua função de preparo e desenvolver um quadro patólogico, consequentemente. Este sentimento estimula o indivíduo a entrar em ação, porém, em excesso, faz exatamente o contrário, impedindo as reações (Hales, Yudofsky & Gabbard, 2012).

Com isso a ansiedade até um certo ponto é algo benéfico. O embróglio é descobrir em que nível (0-10) a ansiedade pode se tornar patológica.


A maneira prática de se diferenciar ansiedade normal de ansiedade patológica é basicamente avaliar se a reação ansiosa é de curta duração, autolimitada e relacionada ao estímulo do momento ou não. Contudo, devido a natureza da base de dados de não informar sobre a presença ou não de ansiedade, e sobre se é repetitiva ou não, a análise será feita com base no nível de ansiedade informada. 

#### Qual nível será considerado como ansiedade patológica?

Para a consideração desse problema, devemos a partir dos estudos e pesquisa de artigos, definir um nível de ansiedade que será considerado como patológico. Além disso é crucial identificar um parâmetro ideal para a base de dados, ou seja deve-se levar em conta além da pesquisa a base de dados em si, para que o modelo seja o mais preciso possível.

Após análise da distribuição dos dados, identificou-se que um valor limiar de 6 é apropriado para distinguir ansiedade normal de ansiedade patológica.

#### Por que 6?

A base de dados possui 736 entradas, e a distribuição dos dados de ansiedade é a seguinte:

![Distribuição dos dados de Ansiedade](/images/nivel_ansiedade.png)


Gráfico 1: Distribuição dos dados de Ansiedade

Como pode ser observado a base de dados está bem distribuída. Tem-se 361 entradas com nível de ansiedade maior que 6, e 375 entradas com nível de ansiedade menor ou igual a 6.

O valor mais próximo de 50% foi para > 6, ou seja seria considerada como ansiedade patológica apenas os valores [7,8,9,10] e como ansiedade normal os valores [0,1,2,3,4,5,6].

Por isso foi escolhido o valor 6, pois assim a base de dados ficará bem distribuída, e o modelo será o mais preciso possível.



#### Relação entre ansiedade e outras doenças

Do ponto de vista fisiológico, a ansiedade é um estado de funcionamento cerebral que acarreta sintomas neurovegetativos, tais como, insônia, taquicardia, palidez, aumento da respiração, tensão muscular, tremor, tontura, desconforto gastrointestinal, dentre uma série de outras condições (Zamignani & Banaco, 2005; Leahy, 2011).

Além disso a ansiedade é considerada como um sentimento primário, desencadeado por uma ameaça real ou imaginária, que pode ser percebida como perigosa, desconhecida ou estranha. Com isso a ansiedade não é causada por nenhuma outra variável, mas ela pode ser a causa de outras variaveis!

---
#### Referências

Castillo, A. R. G., Recondo, R., Asbahr, F. R., & Manfro, G. G.. (2000). Transtornos de ansiedade. Brazilian Journal of Psychiatry, 22, 20–23. https://doi.org/10.1590/S1516-44462000000600006


LENHARDTK, Gabriela; CALVETTI, Prisla Ücker. Quando a ansiedade vira doença?: Como tratar transtornos ansiosos sob a perspectiva cogntivo-comportamental. Aletheia,  Canoas ,  v. 50, n. 1-2, p. 111-122, dez.  2017 .   Disponível em <http://pepsic.bvsalud.org/scielo.php?script=sci_arttext&pid=S1413-03942017000100010&lng=pt&nrm=iso>. acessos em  14  nov.  2023.

Neves Guimarães de Carvalho, R., Pereira dos Santos , I. ., Silva Motta , . L., Rodrigues Silva, J. ., Pereira, E. da S., Ferreira de Sousa, J. ., Netto Bellot , . C. ., Duarte de Oliveira, N., & Luiz Lima da Silva, J. . (2022). A ANSIEDADE E O SER ANSIOSO. RECIMA21 - Revista Científica Multidisciplinar - ISSN 2675-6218, 3(12), e3122486. https://doi.org/10.47820/recima21.v3i12.2486

---

### Informações sobre depressão

---

Após a leitura de alguns artigos relacionados a depressão, foi possível tirar algumas informações úteis como por exemplo que a depressão é uma doença que afeta o humor, causando uma tristeza profunda e persistente, que pode durar semanas, meses ou até anos. A depressão pode ser classificada como leve, moderada ou grave, dependendo da intensidade dos sintomas. A depressão é uma doença que pode afetar qualquer pessoa, independentemente da idade, sexo ou condição social. No entanto, as mulheres são mais propensas a desenvolver depressão, pois são mais vulneráveis a alterações hormonais. Além disso, a depressão pode ser causada por fatores genéticos, ambientais, psicológicos e biológicos (Rufino, Leite, Freschi, Venturelli, De Oliveira, Diogo, Morato, Filho, 2018).

A maioria dos pacientes com depressão diz não mais obter gozo
com as atividades anteriores, e muitos dizem perder o interesse e o afeto pelas pessoas
(ATKINSON et al., 2002).

#### Qual nível será considerado como depressão patológica?

Esse é o mesmo problema que tivemos com a ansiedade, ou seja, devemos a partir dos estudos e pesquisa de artigos, definir um nível de depressão que será considerado como patológico. Além disso é crucial identificar um parâmetro ideal para a base de dados, ou seja deve-se levar em conta além da pesquisa a base de dados em si, para que o modelo seja o mais preciso possível.

O diagnóstico da depressão é feito a partir da presença de determinados sintomas que se
manifestam numa certa duração e intensidade também toma como base a história de vida do
paciente. Como o estado depressivo pode ser um sintoma secundário a várias doenças, sempre é
importante estabelecer o diagnóstico diferencial (GRUBITS; GUIMARÃES, 2007).

É crucial distinguir a depressão clínica da tristeza transitória resultante de eventos desafiadores inerentes à vida cotidiana, como a perda de um ente querido, desilusões amorosas, conflitos familiares e dificuldades financeiras. Indivíduos que não sofrem da doença podem experimentar tristeza em resposta a adversidades, mas geralmente conseguem superá-las. Em contrapartida, nos casos de depressão clínica, a tristeza e a falta de ânimo persistem, mesmo na ausência de uma causa aparente. O interesse por atividades prazerosas e que costumavam proporcionar bem-estar diminui drasticamente.

O diagnóstico de depressão geralmente requer a presença de vários sintomas por um período prolongado, como pelo menos duas semanas.

Eis o problema da base de dados, devido a sua natureza de fornecer apenas um valor que vai de 0 a 10, não é possível saber se a pessoa está com depressão clínica ou não. Portanto devido a natureza da base de dados, deve-se estipular um valor de nível de depressão que será considerado como patológico.

Após análise da distribuição dos dados, identificou-se que um valor limiar de 5 é apropriado para distinguir depressão normal de depressão patológica.

#### Por que 5?

A depressão, ao contrário da ansiedade, não é considerada uma resposta natural inerente à condição humana. Embora as pessoas possam experimentar tristeza em resposta a eventos adversos, a depressão é percebida como uma condição que não faz parte intrínseca da natureza humana, mas sim algo que pode se desenvolver em determinadas circunstâncias.

![Distribuição dos dados de Depressão](/images/nivel_depressao.png)

Gráfico 2: Distribuição dos dados de Depressão

Como pode ser observado a base de dados está bem distribuída. Diferente da ansiedade temos grandes valores próximos a 0, e valores considerados a partir de 6.

![Gráfico de Pizza](/images/grafico_de_pizza_depressao.png)

Gráfico 3: Gráfico de Pizza de Depressão

Analisando a distribuição através do gráfico de pizza, tem-se que 54,3% dos dados estão entre 5 e 10, e 45,7% dos dados estão entre 0 e 4. Ou seja, se considerarmos o valor 5 como patológico, teremos uma base de dados bem distribuída, e o modelo será o mais preciso possível.



#### Referências

Rufino, S., Leite, R. S., Freschi, L., Venturelli, V. K., De Oliveira, E. S., Diogo, A., Morato, M., Filho. (2018). Revista Saúde em Foco - Edição nº 10. Revista Saúde em Foco, nº 10, 841-842. Obtido em https://portal.unisepe.com.br/unifia/wp-content/uploads/sites/10001/2018/11/095_ASPECTOS-GERAIS-SINTOMAS-E-DIAGN%C3%93STICO-DA-DEPRESS%C3%83O.pdf

