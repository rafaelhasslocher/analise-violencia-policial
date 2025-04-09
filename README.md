# MVP-Analise-Violencia-Policial

## 0 - Considerações Iniciais

Este repositório contém o MVP desenvolvido para aprovação na Sprint "Engenharia de Dados" da Pós-Graduação Lato Sensu em Ciência de Dados e Analytics do CCE PUC-Rio.

Para a construção desse MVP, utilizou-se a ferramenta "Databricks Community Edition" para a execução do notebook, criação de schemas de dados e armazenamento das tabelas utilizadas ao longo do projeto. Nesse sentido, cabe mencionar que o notebook deverá ser executado necessariamente na ferramenta destacada.

No notebook, utilizou-se as bibliotecas `numpy`, `pandas`, `matplotlib`, `seaborn` para o trabalho da base e visualização dos dados como um todo. A biblioteca `spark` foi utilizada para a gestão das tabelas da pipeline.

## 1 - Objetivo do Trabalho

Nos últimos anos, os noticiários vêm sendo tomados por notícias que relatam episódios de violência praticados por militares e policiais. Em 2019, o músico Evaldo Rosa foi assassinado [[1]] por militares do exército enquanto dirigia o carro da família, sendo alvejado por 257 tiros de fuzil, dos quais 62 atingiram o veículo. O excessivo número de disparos chamou a atenção da mídia e das redes sociais, de modo que o caso se tornou símbolo da luta antirracista e por abordagens policiais humanizadas. Embora condenados a princípio a aproximadamente 30 anos de prisão, em 2024 [[2]] o Superior Tribunal Militar (STM) reduziu a pena dos militares envolvidos para apenas três anos. A decisão causou a indignação, inclusive, à atual presidente do STM [[3]], que classificou a decisão da corte como "lamentável".

Em 2020, nos Estados Unidos, um homem preto de nome George Floyd foi assassinado por um policial branco ao sofrer com a pressão do joelho do oficial sobre seu pescoço por mais de nove minutos [[4]]. O caso ganhou grande notoriedade no país, mobilizando diversos grupos ativistas no pedido de justiça, cujo sentimento de indignação foi "exportado" a diversos países do mundo. 

No ano seguinte, o episódio conhecido como "Massacre do Jacarezinho" chocou o país ao resultar na morte de 28 pessoas, em sua maioria pretas, em uma das áreas mais pobres do Rio de Janeiro [[5]]. Mais do que a revolta, o caso gerou um amplo debate na imprensa e nas redes sociais quanto à abordagem da polícia e em um possível viés racista e higienista em suas operações. 

Embora os episódios citados acima tenham causado grande repercussão e comoção, os dados mostram que a realidade ainda é dura: em 2024, as mortes por policiais em serviço cresceram mais de 84% em relação ao ano anterior [[6]]. Um estudo da UNICEF sobre os dados concluiu que crianças e adolescentes negros são 3,7 vezes mais vítimas de intervenções letais da PM do que brancos. Na contramão desses dados, noticia-se queda na quantidade de sindicâncias e Inquéritos Policiais Militares, estes estando no menor volume registrado dos últimos oito anos.

Para o desenvolvimento desse trabalho, a temática central estará envolvida na análise dos dados referentes a homicídios pelas mãos de policiais. Nesse sentido, colocam-se as seguintes perguntas principais:

1. Há suporte nos dados para evidenciar que policiais são mais propensos a cometer homicídios sobre pessoas pretas?

2. Quais são as condições dos homicídios ocorridos? Há uma concentração específica das ocorrências?

3. Há outras métricas que podem influenciar a ação dos policiais além do componente racial?

<b><span style="color:red;">Escrever uma conclusão</span></b>

## 2 - Escolha dos Dados




[1]: https://www.cnnbrasil.com.br/nacional/sudeste/rj/257-tiros-nao-sao-legitima-defesa-diz-viuva-de-homem-morto-por-militares-do-exercito-no-rj/

[2]: https://www.cnnbrasil.com.br/nacional/sudeste/rj/stm-reduz-para-tres-anos-a-pena-de-militares-condenados-por-morte-de-musico-e-catador/

[3]: https://agenciabrasil.ebc.com.br/justica/noticia/2024-12/estado-foi-inimigo-no-caso-evaldo-rosa

[4]: https://www.theguardian.com/us-news/2021/apr/20/derek-chauvin-verdict-guilty-murder-george-floyd

[5]: https://g1.globo.com/rj/rio-de-janeiro/noticia/2022/05/05/jacarezinho-1-ano-apos-28-mortes-10-de-13-investigacoes-do-mp-foram-arquivadas.ghtml

[6]: https://www.cnnbrasil.com.br/nacional/sudeste/sp/mortes-por-policiais-em-servico-cresceram-84-no-ano-passado-em-sp/
