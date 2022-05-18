# Otimização do planejamento de uma viagem com uma Tiny House

#### Aluno: [Isabelle Câmara](https://github.com/camaraisa)
#### Orientador: [Felipe Borges](https://github.com/FelipeBorgesC) 



Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

- [Link para o código](https://github.com/camaraisa/TCC/blob/main/TCC%20-%20Conhecendo%20o%20Brasil%20com%20uma%20tiny%20house%20vf.xlsx). 




### Resumo

Segundo Yeska Coelho(2021), Tiny house é um construção modular (de no máximo 40m²) embasada na filosofia do minimalismo e no consumo mais consciente. A construção da Tiny House tem como pilar economia de recursos, baixa produção de resíduos e uma marcenaria inteligente para aproveitar ao máximo os espaços. Coelho(2021) conta que o movimento surgiu nos Estados Unidos, e a partir da crise econômica de 2008 ganhou relevância. Com a economia enfraquecida, a solução era viver em uma casa pequena e que não precisasse pagar impostos ou ter posse de um terreno. 

É relevante citar que em um cenário de Pandemia, muitos empregados estão experimentando o home office. De acordo com a pesquisa FIA Employee Experience (FEEx), de 213 empresas em território nacional, 90% das empresas adotaram alguma modalidade de trabalho remoto a partir de 2020.  

Pensando no cenário atual e nas possibilidades que o trabalho remoto oferece, o presente trabalho tem por objetivo realizar a otimização do planejamento de uma viagem usando uma Tiny House, onde o objetivo é encontrar o menor custo para o viajante passar por todas as capitais brasileiras. O modelo leva em conta o custo da cidade, pois será necessário fazer as compras dos alimentos, distância entre cada capital e o custo da gasolina. 



According to Yeska Coelho (2021), Tiny house is a modular construction (maximum 40m²) based on the philosophy of minimalism and more conscious consumption. The construction of the Tiny House is based on resource savings, low waste production and smart carpentry to make the most of spaces. Coelho (2021) says that the movement emerged in the United States, and from the economic crisis of 2008 it gained relevance. With the economy weakened, the solution was to live in a small house that did not have to pay taxes or own land.

It is relevant to mention that in a pandemic scenario, many employees are experiencing the home office. According to the FIA ​​Employee Experience (FEEx) survey, of 213 companies nationwide, 90% of companies have adopted some form of remote work as of 2020.

Thinking about the current scenario and the possibilities that remote work offers, the present work aims to optimize the planning of a trip using a Tiny House, where the objective is to find the lowest cost for the traveler to pass through all Brazilian capitals. The model takes into account the cost of the city, as it will be necessary to buy food, the distance between each capital and the cost of gasoline.



### 1. Introdução

O trabalho de otimização do planejamento tem como objetivo auxiliar na otimização de uma viagem de Tiny house. O modelo é desenvolvido no excel e pretende responder a duas questões: 
1. Qual o melhor  trajeto para o visitante que deseja viajar por todas as capitais do Brasil tendo Vitória como ponto de partida e ponto de chegada? 
2. Qual o melhor trajeto para um viajante que mora em Cuiabá e precisa passar por C.Grande, Brasilia, Belo Horizonte, Aracaju, Belém e Boa Vista? 

Os dois cenários serão avaliados e comparados com uma versão de rota sem otimização.


### 2. Modelagem

O trabalho de otimização do planejamento é realizado na ferramenta excel com o recurso da aplicação do Solver. O modelo visa o menor valor entre as distância das capitais e ao mesmo tempo procura o menor valor entre o custo da cesta básica por cidade. Para o total geral, os valores são normalizados e somados.

Para desenvolver a modelagem foram levados em conta os seguintes indicadores:

* Distância - Distância entre as cidades

* Valor do combustível - Valor do combustível de cada cidade, fonte do ANP (Agência Nacional do Petróleo, Gás e Biocombustíveis)

* Custo da cesta básica - O custo da cesta básica foi coletado do DIEESE - Departamento Intersindical de Estatística e Estudos Socioeconômicos. Vale citar que as cidades de Cuiabá, Boa Vista, Macapá, Manaus, Palmas, Porto Velho, Rio Branco, Maceió, São Luís, Teresina e Maceió não tinham dados atualizados para janeiro de 2022. Por conta disso, foi avaliado o aumento que ocorreu em São Paulo como padrão, e projetado para essas cidades.


A partir desses indicadores básicos acima, foram criadas as seguintes métricas:

* Tempo da viagem - Distância entre cidades dividida pela velocidade média que a Tiny house pode percorrer. Foi estipulado como 50km como padrão.
 
* Custo do deslocamento - É a distância entre as cidades multiplicada pelo valor do combustível da cidade. Estipulou-se que o consumo do litro da gasolina por quilômetro gasto seria de uma picape que em média gasta 9 km/l

* Quantidade de dias x custo da cidade - Corresponde a quantidade de dias que o viajante vai gastar por conta da distância entre as cidades. Vale citar que foi estipulado 800km como quantidade máxima de quilômetros percorridos por dia.


### 3. Resultados

Para o trabalho, foram analisados 2 cenários:

3.1. Visitante que deseja viajar por todas as capitais do Brasil tendo Vitória como ponto de partida e ponto de chegada. O resultado abaixo mostra o tempo de viagem, o custo do deslocamento e o possível custo da cidade pela quantidade de dias.

| Distancia | Cidade | Total | Tempo de viagem | Valor Combustivel | Custo Deslocamento | Custo cidade | Qtd dias*custo_da_cidade | Total |
|---- | --- | ----| ----| ---- | ---- | --- | --- | --- |
| 524| Vitória| 16838| 10,48| 6,04| 352| 678| 1037| 36862 |
| 489| Belo Horizonte| | 9,78| 6,18| 336| 633| 963| 0 |
| 408| São Paulo|  | 8,16| 5,62| 255| 714| 1072| |
| 251| Curitiba|   | 5,02| 5,73| 160| 637| 931| |
| 376| Florianópolis|  | 7,52| 5,74| 240| 696| 1039| | 
| 1518| Porto Alegre| | 30,36| 6,14| 1036| 673| 1197|  |
| 705| C. Grande|  | 14,1| 5,95| 466| 660| 1040|  |
| 209| Goiânia| | 4,18| 6,27| 146| 625| 907|  |
| 873| Brasília| | 17,46| 6,35| 616| 661| 1069| |
| 1414| Cuiabá| | 28,28| 5,94| 933| 633| 1109|  |
| 544| Rio Branco| | 10,88| 6,45| 390| 532| 816| |
| 901| Porto Velho| | 18,02| 6,06| 607| 617| 1002|  | 
| 785| Manaus| | 15,7| 5,79| 505| 579| 923|  | 
| 1110| Boa Vista| | 22,2| 5,63| 694| 596| 999| |
| 329| Macapá| | 6,58| 5,14| 188| 585| 867|  |
| 481| Belém|| 9,62| 6,03| 322| 564| 857|  |
| 329| São Luis|| 6,58 | 5,9| 216| 589| 872| |
| 634| Teresina| | 12,68| 6,3| 444| 613| 954| | 
| 435| Fortaleza|  | 8,7| 5,93| 287| 607| 916|   |
| 185| Natal| | 3,7| 6,1| 125| 551| 796| | 
| 104| João Pessoa|  | 2,08| 5,79| 67| 539| 768| |
| 285| Recife|  | 5,7| 5,9| 187| 543| 799| |
| 294| Maceió|  | 5,88| 6,04| 197| 595| 876| |
| 277| Aracaju|  | 5,54| 6,09| 187| 508| 746| |
| 1454| Salvador|  | 29,08| 6,06| 979| 540| 952| |
| 1512| Palmas|  | 30,24| 6,15| 1033| 591| 1051|  |
| 412| R. Janeiro| | 8,24| 6,48| 297| 693| 1041| |
|  |   |   |  | 6,04| 0| 678| 948|   


Com a otimização, encontramos 16.838 como menor valor de distância percorrida e 36.862 como melhor valor de custo. Resultando em um total normalizado de 23.

O mesmo questionamento foi avaliado sem aplicação da otimização, ou seja, de acordo com a observação do mapa, construímos uma rota para passar pelas 27 capitais.


| Cidade| Total| Tempo de viagem| Valor Combustivel| Custo Deslocamento| Custo cidade| Qtd dias*custo_da_cidade| Total| 
|---- | --- | ----| ----| ---- | ---- | --- | --- |
| Vitória| 17255| 10,48| 6,04| 352| 678| 1037| 37103| 
| Belo Horizonte| | 19,28| 6,18| 662| 633| 1038| 0| 
| Salvador| | 7,12| 6,06| 240| 540| 804| | 
| Aracaju| | 4,02| 6,09| 136| 508| 736| | 
| Maceió| | 4,04| 6,04| 136| 595| 862| | 
| Recife| | 2,4| 5,9| 79| 543| 776| | 
| João Pessoa| | 3,02| 5,79| 97| 539| 774| | 
| Natal| | 10,74| 6,1| 364| 551| 845| | 
| Fortaleza| | 9,9| 5,93| 326| 607| 925| | 
| Teresina| | 8,92| 6,3| 312| 613| 926| | 
| São Luis| | 27,72| 5,9| 909| 589| 1027| | 
| Palmas| | 25,66| 6,15| 877| 591| 1017| | 
| Belém| | 6,58| 6,03| 220| 564| 835| | 
| Macapá| | 22,2| 5,14| 634| 585| 981| | 
| Boa Vista| | 13,22| 5,63| 413| 596| 932| | 
| Manaus| | 22,98| 5,79| 739| 579| 976| | 
| Rio Branco| | 10,88| 6,45| 390| 532| 816| | 
| Porto Velho| | 29,12| 6,06| 980| 617| 1087| | 
| Cuiabá| | 22,66| 5,94| 748| 633| 1064| | 
| Brasília| | 3,46| 6,35| 122| 661| 954| | 
| Goiânia| | 18,7| 6,27| 651| 625| 1020| | 
| C. Grande| | 15,6| 5,95| 516| 660| 1052| | 
| Curitiba| | 5,02| 5,73| 160| 637| 931| | 
| Florianópolis| | 7,52| 5,74| 240| 696| 1039| | 
| Porto Alegre| | 17,04| 6,14| 581| 673| 1085| | 
| São Paulo| | 8,58| 5,62| 268| 714| 1075| | 
| R. Janeiro| | 8,24| 6,48| 297| 693| 1041| | 
| | | | 6,04| 0| 678| 948| | 

Com a avaliação manual, a distância ficou em 17255, o custo em 37103 e o valor total de 25. Delta de 2% a mais na distância que o otimizado.


3.2. Qual o melhor trajeto para um viajante que mora em Cuiabá e precisa passar por C.Grande, Brasilia, Belo Horizonte, Aracaju, Belém e Boa Vista? 


| Cidade| Tempo de viagem| Valor Combustivel| Custo Deslocamento| Custo cidade| Qtd dias*custo_da_cidade|
|---- | --- | ----| ----| ---- | ---- | 
| Cuiabá| 13,88| 5,94| 458| 633| 995| 
| C. Grande| 22,68| 5,95| 750| 660| 1111| 
| Brasília| 14,32| 6,35| 505| 661| 1043| 
| Belo Horizonte| 31,56| 6,18| 1084| 633| 1135| 
| Aracaju| 32,82| 6,09| 1110| 508| 919| 
| Belém| 28,64| 6,03| 959| 564| 991| 
| Boa Vista| 42,14| 5,63| 1318| 596| 1148| 

O Solver encontrou como menor distância 9.302 e custo de 13.526, resultando em 77 como valor normalizado.


Ao criar o mesmo cenário manualmente, foi colocada a seguinte ordem: Cuiabá, Boa Vista, Belém, Aracaju, Belo Horizonte, Campo Grande e Brasília.

Nesse cenário, temos como distância total 15.677(69%) e custo de 18.565, resultando em 110, como valor normalizado. Delta de 43% a mais.


### 4. Conclusões

Concluímos que o modelo apresenta-se confiável para otimizar uma viagem de Tini House pelas capitais brasileiras. Quando avaliado para todas as capitais e com apoio de um mapa, o delta entre o cenário manual e otimizado é de 2% na distância a mais entre cidades na versão manual. Já em um cenário menor, a otimização do planejamento se fez mais eficaz, chegando a 69% na otimização da distância entre as capitais. Isso ocorre por ser menos óbvia a proximidade das cidades ao olhar no mapa. Diferentemente da observação de todas as capitais.

### 5. Referências bibliograficas

https://casacor.abril.com.br/sustentabilidade/tiny-house/ acessado em 21 de fevereiro de 2022.
https://economia.uol.com.br/noticias/redacao/2021/05/31/ficar-em-casa-da-trabalho-mas-home-office-veio-para-ficar-dizem-pesquisas.htm acessado em 21 de fevereiro de 2022.





Matrícula: 123.456.789

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*