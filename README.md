#Predição do Estado Operacional de Turbinas Offshore com Sensores Remotos
#Introdução
Este projeto propõe uma abordagem para prever o estado operacional das turbinas do parque eólico offshore WindFloat Atlantic, utilizando imagens de satélite e dados meteoceanográficos abertos.
Através de técnicas de Machine Learning e Sensores Remotos, pretende-se reduzir a dependência de sistemas tradicionais de monitorização física, contribuindo para melhorar as estratégias de Operação e Manutenção (O&M) e a eficiência operacional.

#Objetivo
Prever o estado operacional de turbinas offshore usando apenas dados de satélite e meteoceanográficos.

Desenvolver modelos de machine learning robustos para classificação binária (turbina a operar / não a operar).

Demonstrar a viabilidade da aplicação de sensores remotos em operações offshore de energias renováveis.

#Recolha de Dados
##Imagens de Satélite:

Sentinel-2 (Programa Copernicus).

Resolução de 10 metros, revisita de 2 dias.

Aplicação de uma CNN para detetar automaticamente as plataformas flutuantes.

##Dados Meteoceanográficos:

ECHOWAVE (TU Delft) e Copernicus.

##Dados de vento (velocidade e direção) e ondas (altura e período).

##Dados de Produção:

APIs abertas da ENTSO-E.

Dados atribuídos diretamente ao WindFloat Atlantic (único parque offshore em Portugal).

##Dados Derivados:

Cálculo de centroides das plataformas e respetivos deslocamentos (offsets).

Integração de dados temporais, meteorológicos e espaciais num dataset final em CSV.

#Tratamento de Dados
##Pré-processamento:

Extração de timestamps e coordenadas das imagens e máscaras processadas.

Arredondamento dos timestamps para a hora mais próxima.

##Fusão de Dados:

Integração de produção elétrica, dados de vento e de ondas para cada timestamp.

Modelação da produção teórica das turbinas com curvas de potência específicas (Vestas V164 8.0 MW).

##Criação do Dataset:

Variáveis incluídas: intensidade e direção do vento, deslocamentos dos centroides, produção real, etc.

Dataset estruturado para análise e treino de modelos de machine learning.

#Treino de Modelos:

Modelos usados: Logistic Regression e SVM com kernel radial (RBF).

Avaliação com métricas: Acurácia, Recall, F1-Score, ROC-AUC.

Validação cruzada K-Fold para robustez.

#Resultados
Logistic Regression demonstrou maior estabilidade e melhor desempenho global.

SVM obteve elevada precisão em alguns cenários, mas com maior variabilidade entre folds.

Confirmada a correlação entre deslocamento das plataformas e condições de vento.

Demonstração de viabilidade para aplicações remotas em O&M offshore
