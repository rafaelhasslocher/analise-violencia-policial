# MVP-Analise-Violencia-Policial

## 0 - Considerações Iniciais

Este repositório contém o MVP desenvolvido para aprovação na Sprint "Engenharia de Dados" da Pós-Graduação Lato Sensu em Ciência de Dados e Analytics do CCE PUC-Rio.

Para a construção desse MVP, utilizou-se a ferramenta "Databricks Community Edition" para a execução do notebook `mvp-analise-violencia-policial.ipynb`, criação de schemas de dados e armazenamento das tabelas utilizadas ao longo do projeto. Nesse sentido, cabe mencionar que, caso necessário, o notebook deverá ser executado necessariamente na ferramenta destacada.

No notebook, utilizou-se as bibliotecas `numpy`, `pandas`, `matplotlib`, `seaborn` para o trabalho da base e visualização dos dados como um todo. A biblioteca `spark` foi utilizada para a gestão das tabelas da pipeline.

## 1 - Objetivo do Trabalho

Nos últimos anos, os noticiários vêm sendo tomados por notícias que relatam episódios de violência praticados por militares e policiais. Em 2019, o músico Evaldo Rosa foi assassinado [[1]] por militares do exército enquanto dirigia o carro da família, sendo alvejado por 257 tiros de fuzil, dos quais 62 atingiram o veículo. O excessivo número de disparos chamou a atenção da mídia e das redes sociais, de modo que o caso se tornou símbolo da luta antirracista e por abordagens policiais humanizadas. Embora condenados a princípio a aproximadamente 30 anos de prisão, em 2024 [[2]] o Superior Tribunal Militar (STM) reduziu a pena dos militares envolvidos para apenas três anos. A decisão causou a indignação, inclusive, à atual presidente do STM [[3]], que classificou a decisão da corte como "lamentável".

Em 2020, nos Estados Unidos, um homem preto de nome George Floyd foi assassinado por um policial branco ao sofrer com a pressão do joelho do oficial sobre seu pescoço por mais de nove minutos [[4]]. O caso ganhou grande notoriedade no país, mobilizando diversos grupos ativistas no pedido de justiça, cujo sentimento de indignação foi "exportado" a diversos países do mundo. 

No ano seguinte, o episódio conhecido como "Massacre do Jacarezinho" chocou o país ao resultar na morte de 28 pessoas, em sua maioria pretas, em uma das áreas mais pobres do Rio de Janeiro [[5]]. Mais do que a revolta, o caso gerou um amplo debate na imprensa e nas redes sociais quanto à abordagem da polícia e em um possível viés racista e higienista em suas operações. 

Embora os episódios citados acima tenham causado grande repercussão e comoção, os dados mostram que a realidade ainda é dura: em 2024, as mortes por policiais em serviço cresceram mais de 84% em relação ao ano anterior [[6]]. Um estudo da UNICEF sobre os dados concluiu que crianças e adolescentes negros são 3,7 vezes mais vítimas de intervenções letais da PM do que brancos. Na contramão desses dados, noticia-se queda na quantidade de sindicâncias e Inquéritos Policiais Militares, estes estando no menor volume registrado dos últimos oito anos.

Para o desenvolvimento desse trabalho, a temática central estará envolvida na análise dos dados referentes a homicídios pelas mãos de policiais. Nesse sentido, colocam-se as seguintes perguntas principais:

1. Há suporte nos dados para evidenciar que policiais são mais propensos a cometer homicídios sobre pessoas não brancas nos Estados Unidos?

2. Quais são as condições dos homicídios ocorridos nos Estados Unidos? Há uma concentração específica das ocorrências?

3. Há outras métricas que podem influenciar a ação dos policiais além do componente racial nos Estados Unidos?

## 2 - Escolha dos Dados

Para o desenvolvimento desse trabalho, foram utilizadas mútltiplas fontes de dados.

A tabela fato do modelo ("PoliceKillingsUS.csv") e as cinco primeiras tabelas dimensão ("MedianHouseholdIncome2015.csv", "PercentagePeopleBelowPovertyLevel.csv", "PercentOver25CompletedHighSchool.csv", "ShareRaceByCity.csv") foram extraídas da plataforma Kaggle e podem ser acessadas no seguinte link: https://www.kaggle.com/datasets/kwullum/fatal-police-shootings-in-the-us.

A licença para a utilização dessas tabelas é definida na plataforma como "CC-NY-NC-SA 4.0". Após pesquisa sobre a definição das licenças [[7]], identificamos que ela permite o compartilhamento e adaptação dos dados desde que sejam utilizados para fins não-comerciais e com créditos adequados. Dessa forma, entendemos que as bases são adequadas para os fins deste trabalho.

A sexta tabela dimensão apresentada no arquivo `mvp-analise-violencia-policial.ipynb` ("sub-est2019_all.csv") do site da agência de Censo dos Estados Unidos e pode ser encontrada no seguinte link: https://www.census.gov/data/tables/time-series/demo/popest/2010s-total-cities-and-towns.html (na seção "Datasets", acessar o link "United States").

A sétima tabela dimensão ("fips_codes.csv") também foi retirada do site da agência de Censo dos Estados Unidos, conforme seguinte link: https://www.census.gov/library/reference/code-lists/ansi.html (na seção "County and County Equivalents Entities", selecionar "United States" no menu suspenso).

Quanto às definições de licença das duas últimas tabelas, é possível verificar no próprio site [[8]] que os dados do Censo americano são de uso aberto, de modo que também não foi identificado impeditivo à sua utilização.

Todas as tabelas foram baixadas da plataforma e unificadas neste mesmo repositório Github, de modo a facilitar a referência ao longo do código.

## 3 - Análise dos Dados e Conclusões

Todo o processo de análise de dados e do desenvolvimento das respostas colocadas no objetivo são discutidas no arquivo `mvp-analise-violencia-policial.ipynb`.

## 4 - Autoavaliação

Ao longo do processo de desenvolvimento do MVP, minha maior dificuldade foi no gerenciamento de tempo. Por se tratar de um assunto muito debatido pela sociedade, há um grande número de dados, análises e matérias jornalísticas divulgadas, de modo que foi necessário realizar alguma triagem para o desenvolvimento do MVP. Por essa razão, uma parte considerável do tempo disponível foi utilizada para a pesquisa e o entendimento do que deveria constar no estudo apresentado no MVP.

Pelo descrito acima, há alguns pontos que eu gostaria de desenvolver mas que, pelo gerenciamento do tempo, não foi possível. Como exemplo, cito:

- Mergulhar de forma mais aprofundada nos dados demográficos dos Estados Unidos, especialmente após a verificação de componentes além do racial como influentes à distribuição dos óbitos;

- Segregação do notebook em parcelas menores, utilizando a orientação a objetos para a definição das etapas de ETL para um projeto mais fluido e organizado;

- Cruzamento com outros horizontes temporais de análise (mais amplos ou não), de modo a descartar a possibilidade de que os dados possam apresentar algum viés na comparação com outros dados.

Apesar dos itens colocados acima, fiquei satisfeito com a minha entrega e com o preenchimento dos requisitos do MVP, de modo que esses pontos poderiam ser abordados em estudo futuro.

## 5 - Evidências das Tabelas Criadas

#### **Tabela "bronze.fato":**

<img src="https://github.com/rafaelhasslocher/analise-violencia-policial/blob/main/imagens/bronze.fato.png?raw=true">

#### **Tabela "bronze.codigos_cidades":**

<img src="https://github.com/rafaelhasslocher/analise-violencia-policial/blob/main/imagens/bronze.codigos_cidades.png?raw=true">

#### **Tabela "bronze.dimensao_escolaridade":**

<img src="https://github.com/rafaelhasslocher/analise-violencia-policial/blob/main/imagens/bronze.dimensao_escolaridade.png?raw=true">

#### **Tabela "bronze.dimensao_linha_pobreza":**

<img src="https://github.com/rafaelhasslocher/analise-violencia-policial/blob/main/imagens/bronze.dimensao_linha_pobreza.png?raw=true">

#### **Tabela "bronze.dimensao_percentual_racas":**

<img src="https://github.com/rafaelhasslocher/analise-violencia-policial/blob/main/imagens/bronze.dimensao_percentual_racas.png?raw=true">

#### **Tabela "bronze.dimensao_populacao":**

<img src="https://github.com/rafaelhasslocher/analise-violencia-policial/blob/main/imagens/bronze.dimensao_populacao.png?raw=true">

#### **Tabela "bronze.dimensao_renda_mediana":**

<img src="https://github.com/rafaelhasslocher/analise-violencia-policial/blob/main/imagens/bronze.dimensao_renda_mediana.png?raw=true">

#### **Tabela "silver.fato":**

<img src="https://github.com/rafaelhasslocher/analise-violencia-policial/blob/main/imagens/silver.fato.png?raw=true">

#### **Tabela "silver.dimensao_escolaridade":**

<img src="https://github.com/rafaelhasslocher/analise-violencia-policial/blob/main/imagens/silver.dimensao_escolaridade.png?raw=true">

#### **Tabela "silver.dimensao_linha_pobreza":**

<img src="https://github.com/rafaelhasslocher/analise-violencia-policial/blob/main/imagens/silver.dimensao_linha_pobreza.png?raw=true">

#### **Tabela "silver.dimensao_percentual_racas":**

<img src="https://github.com/rafaelhasslocher/analise-violencia-policial/blob/main/imagens/silver.dimensao_percentual_racas.png?raw=true">

#### **Tabela "silver.dimensao_populacao":**

<img src="https://github.com/rafaelhasslocher/analise-violencia-policial/blob/main/imagens/silver.dimensao_populacao.png?raw=true">

#### **Tabela "silver.dimensao_renda_mediana":**

<img src="https://github.com/rafaelhasslocher/analise-violencia-policial/blob/main/imagens/silver.dimensao_renda_mediana.png?raw=true">

#### **Tabela "gold.fato_homicidios_cidades":**

<img src="https://github.com/rafaelhasslocher/analise-violencia-policial/blob/main/imagens/gold.fato_homicidios_cidades.png?raw=true">

#### **Tabela "gold.fato_homicidios_mil_habitantes":**

<img src="https://github.com/rafaelhasslocher/analise-violencia-policial/blob/main/imagens/gold.fato_homicidios_mil_habitantes.png?raw=true">

#### **Tabela "gold.fato_indice_obitos_raca":**

<img src="https://github.com/rafaelhasslocher/analise-violencia-policial/blob/main/imagens/gold.fato_indice_obitos_raca.png?raw=true">




[1]: https://www.cnnbrasil.com.br/nacional/sudeste/rj/257-tiros-nao-sao-legitima-defesa-diz-viuva-de-homem-morto-por-militares-do-exercito-no-rj/

[2]: https://www.cnnbrasil.com.br/nacional/sudeste/rj/stm-reduz-para-tres-anos-a-pena-de-militares-condenados-por-morte-de-musico-e-catador/

[3]: https://agenciabrasil.ebc.com.br/justica/noticia/2024-12/estado-foi-inimigo-no-caso-evaldo-rosa

[4]: https://www.theguardian.com/us-news/2021/apr/20/derek-chauvin-verdict-guilty-murder-george-floyd

[5]: https://g1.globo.com/rj/rio-de-janeiro/noticia/2022/05/05/jacarezinho-1-ano-apos-28-mortes-10-de-13-investigacoes-do-mp-foram-arquivadas.ghtml

[6]: https://www.cnnbrasil.com.br/nacional/sudeste/sp/mortes-por-policiais-em-servico-cresceram-84-no-ano-passado-em-sp/

[7]: https://creativecommons.org/licenses/by-nc-sa/4.0/

[8]: https://www.census.gov/about/policies/open-gov/open-data.html