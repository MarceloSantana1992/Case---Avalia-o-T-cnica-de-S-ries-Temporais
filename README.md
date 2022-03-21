# Case---Avaliação-Técnica-de-Séries-Temporais
Case resolvido para vaga de "Cientista de Dados com experiência em séries senoidais"

**PASSOS DA AVALIAÇÃO**
Toda metodologia foi aplicada através da linguagegm R de programação, bem como através de seus pacotes.


1) Organização do número de passaggeiros entrantes em série histórica mensal contínua e para cada mês;
  1.1) Organização de série histórica mensal contínua para as outras variáveis disponíveis no dataset;
2) Avaliação de sazonalidade na série histórica mensal contínua de passageiros entrantes;
3) Identificação da existência de tendências, magnitude das mesmas e quebra de estacionariedade;
4) Correlação cruzada entre a série histórica de passageiros entrantes e as séries históricas de outras variáveis disponíveis;
5) Modelo preditivo para t = 6 para a série histórica de passageiros entrantes;
6) Modelo preditivo para passageiros entrantes por país para t = 6;


**1) e 1.1) Contabilização do número de passageiros entrantes na Austrália em cada mês**

Foram substituídos os valores nulos por zero e efetuou-se um loop conjunto tanto para identificação da série histórica mensal como para as séries históricas anuais de cada mês.
**2) Para a avaliação de sazonalidades, 

Foi aplicado o Método Ondadleta de Morlet Contínua.  Nesta abordagem, observa-se a existência de uma região significante (p-value < 0.10) períodos de 0.25 ano, ou 3 meses. Tal fato indica que a sazonalidade ocorre de maneira trimestral, tendo sido mais intensa em finais de ano, como pode ser observado nas regiões signiicantes imediatamente antes do início de 2010, 2014, 2018 e 2020. A significante região existente, com período variando de 4 a 8 meses, após o ano de 2016 pode ter sido motivado por fatores externos.

**3) Para avaliação Identificação da existência de tendências, magnitude das mesmas e quebra de estacionariedade: Aplica=-se o Método de Mann-Kendall, Curvatura de Sen e Teste ded Pettitt;**

Com relação à existência de tendências, o teste modificado de Mann-Kendall apontou que todos os meses, excetuando-se maio, julho, setembro e outubro, tiveram significante tendência positiva. A aplicação da Curvatura de Sen mostrou que o mês de janeiro desctacou-se pela forte alta; O teste de Pettit mostrou que nenhum mês teve quebra em sua estacionariedade em sua série histórica.  

**4) Correlação cruzada entre a série histórica de passageiros entrantes e as séries históricas de outras variáveis disponíveis;**

Para o teste de correlação cruzada, fez-se o branqueamento das séries históricas envolvidas correlação cruzada mostrou que há uma correlação entre passageiros que entram e passageiros que saem com lag de 10 meses. Outras correlações apresentaram-se complexas, podendo ser meramente ocasionais.

**5) e 6) Modelos peditivos **

Com relação à predição de cenários para a série histórica contínua de passageiros entrantes, optou-se por obter estimativas através do Modelo ARIMA. Na avaliação ded resultados, deve-se levar em conta os efeitos da pandemia, visto que foi detectada forte queda nos anos de 2020 e 2021. Nesse sentido, 
optou-se por estimar os valores para os 6 meses posteriores. Para os 6 meses posteriores, observa-se que a tendência é de aumento na quantidade de passageiros em relação ao anon anterior. 
No entanto, tal estimativa descosidera fatores externos (por exemplo, econômicos), bem como recrudescimento da pandemia.
Também foi viabilizado o modelo preditivo para os países individualmente, tendo sido usada a mesma técnica aplicada à série histórica contínua. Em virtude de se tratar de uma pandemia, logog, envolvendo todos os países, a análise para a série histórica contínua pode ser estendida para a série histórica individual.
