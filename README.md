# TFC-DEISI2109-WindOp
Recolha de Dados
Visão Geral
A recolha de dados teve como objetivo prever o estado operacional do parque eólico flutuante WindFloat Atlantic (ao largo de Viana do Castelo, Portugal).

O conjunto de dados cobre o período de junho de 2020 a julho de 2024.

Fontes de dados: imagens de satélite Sentinel-2, dados meteoceanográficos e dados de produção da ENTSO-E.

Imagens de Satélite
Fonte: Imagens Sentinel-2 (resolução de 10 metros, baixo erro geométrico, disponibilidade gratuita).

Objetivo: Detetar as três plataformas flutuantes do WindFloat Atlantic.

Desafio: As plataformas são difíceis de distinguir devido à resolução e às condições meteorológicas (nuvens).

Solução:

Desenvolvimento de um modelo de Redes Neuronais Convolucionais (CNN).

Criação de um conjunto de dados manualmente etiquetado para treino do modelo.

O modelo CNN passou a detetar automaticamente as plataformas nas imagens pré-processadas.

Cálculo dos Centroides
Após a deteção das plataformas, foram calculadas as posições dos centroides (latitude e longitude).

Os centroides permitiram rastrear deslocamentos e correlacioná-los com condições meteoceanográficas.

Os deslocamentos foram expressos como vetores bidimensionais.

Dados Meteoceanográficos
Fontes:

Base de dados ECHOWAVE (TU Delft) para os períodos disponíveis.

Base de dados Copernicus para colmatar lacunas.

Parâmetros recolhidos:

Velocidade e direção do vento

Altura e período de onda

Dados de Produção do WindFloat Atlantic
Fonte: APIs abertas da ENTSO-E.

Justificação: Sendo o WindFloat Atlantic o único parque eólico offshore em operação em Portugal, os dados de produção eólica offshore podem ser diretamente atribuídos a este parque.
