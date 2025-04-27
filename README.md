# Predição do Estado Operacional de Turbinas Offshore com Sensorização Remota

Este projeto propõe uma abordagem para prever o estado operacional das turbinas do parque eólico offshore **WindFloat Atlantic**, utilizando **imagens de satélite** e **dados meteoceanográficos abertos**.

Através de técnicas de **Machine Learning** e **Sensores Remotos**, pretende-se reduzir a necessidade de sistemas tradicionais de monitorização física, contribuindo para melhorar as estratégias de **Operação e Manutenção (O&M)** e aumentar a eficiência operacional.

---

## 📋 Tabela de Conteúdos
- [Objetivo](#objetivo)
- [Recolha de Dados](#recolha-de-dados)
  - [Fontes de Dados Utilizadas](#fontes-de-dados-utilizadas)
  - [Dados Derivados](#dados-derivados)
- [Tratamento de Dados](#tratamento-de-dados)
  - [Integração e Pré-processamento](#integração-e-pré-processamento)
  - [Fusão de Dados](#fusão-de-dados)
  - [Treino de Modelos](#treino-de-modelos)
- [Resultados](#resultados)
- [Instalação](#instalação)
- [Execução](#execução)
- [Resultados Esperados](#resultados-esperados)
- [Contribuições](#contribuições)
- [Licença](#licença)
- [Financiamento](#financiamento)

---

## 🎯 Objetivo
- Prever o estado operacional de turbinas offshore usando dados de satélite e meteoceanográficos.
- Desenvolver modelos de machine learning robustos para classificação binária (turbina a operar / não a operar).
- Demonstrar a viabilidade da utilização de sensores remotos para operações offshore de energias renováveis.

---

## 🌍 Recolha de Dados

### Fontes de Dados Utilizadas
- **Imagens de Satélite Sentinel-2** (Programa Copernicus)
  - Resolução de 10 metros.
  - Revisita de aproximadamente 2 dias.
  - Deteção automática das plataformas com Rede Neural Convolucional (CNN).
  
- **Dados Meteoceanográficos**
  - Bases de dados **ECHOWAVE** (TU Delft) e **Copernicus**.
  - Velocidade e direção do vento, altura e período das ondas.

- **Dados de Produção Elétrica**
  - APIs abertas da **ENTSO-E**.
  - Dados diretamente atribuídos ao WindFloat Atlantic (único parque offshore em Portugal).

### Dados Derivados
- **Máscaras das plataformas** criadas por CNN treinada manualmente.
- **Centroides das plataformas** calculados para analisar deslocamentos.
- **Offsets** entre posições de centroides e posição média.

---

## ⚙️ Tratamento de Dados

### Integração e Pré-processamento
- Scripts Python para:
  - Extrair timestamps e coordenadas das imagens.
  - Arredondar timestamps para a hora mais próxima.
  - Associar imagens a dados meteoceanográficos e de produção.

### Fusão de Dados
- A classe `offshoreDataMerger` junta:
  - Produção elétrica,
  - Dados de vento,
  - Dados de ondas.
- Integração feita com base nos timestamps comuns.

### Treino de Modelos
- **Classificação binária**: turbina em funcionamento vs. turbina parada.
- **Modelos utilizados**:
  - Regressão Logística (Logistic Regression).
  - Máquina de Vetores de Suporte (SVM) com kernel radial (RBF).
- **Avaliação**:
  - Acurácia, Precisão, Recall, F1-Score, ROC-AUC.
  - Validação cruzada (K-Fold).

---

## 📈 Resultados

- A **Regressão Logística** mostrou desempenho mais estável e robusto.
- O modelo **SVM** teve melhor desempenho pontual mas mostrou maior variabilidade nos dados.
- Confirmação da correlação entre deslocamentos dos centroides e as condições de vento.
- A viabilidade da monitorização remota foi demonstrada com sucesso.

---

## 🛠️ Instalação

1. Clonar o repositório:
   ```bash
   git clone https://github.com/seu-utilizador/nome-do-repositorio.git
   cd nome-do-repositorio


SVM obteve elevada precisão em alguns cenários, mas com maior variabilidade entre folds.

Confirmada a correlação entre deslocamento das plataformas e condições de vento.

Demonstração de viabilidade para aplicações remotas em O&M offshore
