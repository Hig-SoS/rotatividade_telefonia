# Previsão de Churn de Clientes (Telecom)

## 1. Visão Geral

Este projeto tem como objetivo desenvolver um modelo de machine learning capaz de prever a evasão (churn) de clientes em uma empresa de telecomunicações.

A proposta é identificar clientes com alta probabilidade de cancelamento, permitindo que a empresa adote ações preventivas, como ofertas personalizadas, ajustes de plano ou campanhas de retenção.

O trabalho contempla todas as etapas do pipeline de ciência de dados: preparação, análise exploratória, modelagem e avaliação.

---

## 2. Problema de Negócio

A evasão de clientes representa uma das principais fontes de perda de receita no setor de telecomunicações.

Manter clientes existentes é significativamente mais barato do que adquirir novos.

Objetivo do projeto:
Construir um modelo de classificação que identifique clientes com alta probabilidade de churn, priorizando alta capacidade de detecção (recall) sem comprometer a qualidade geral do modelo (ROC-AUC).

---

## 3. Descrição dos Dados

O conjunto de dados é composto por múltiplos arquivos integrados por meio da variável `customerID`:

- contract.csv — Informações contratuais
- personal.csv — Dados demográficos
- internet.csv — Serviços de internet
- phone.csv — Serviços de telefonia

Variável alvo:
- Churn (classificação binária: cliente cancela ou não cancela)

---

## 4. Tecnologias Utilizadas

- Python
- Pandas e NumPy para manipulação de dados
- Matplotlib e Seaborn para visualização
- Scikit-learn para modelagem e pipelines
- XGBoost
- LightGBM

---

## 5. Metodologia

### 5.1 Preparação dos Dados
- Junção das bases de dados
- Tratamento de valores ausentes
- Codificação de variáveis categóricas
- Padronização quando necessário

### 5.2 Análise Exploratória de Dados (EDA)
- Análise da distribuição do churn
- Identificação de padrões comportamentais
- Investigação de variáveis com maior impacto na evasão

### 5.3 Modelagem

Divisão dos dados:
- 75% treino
- 25% teste (com amostragem estratificada)

Modelos avaliados:
- Regressão Logística
- Random Forest
- XGBoost
- LightGBM

Métricas de avaliação:
- ROC-AUC (métrica principal)
- Recall
- Precision
- Ajuste de threshold (0.2) para priorizar recall

---

## 6. Resultados

| Modelo               | ROC-AUC | Recall | Precision |
|----------------------|---------|--------|----------|
| Regressão Logística  | 0.825   | 91.6%  | 41.1%    |
| Random Forest        | 0.806   | 84.2%  | 45.3%    |
| XGBoost              | 0.801   | 89.1%  | 41.3%    |
| LightGBM             | 0.797   | 89.1%  | 40.7%    |

Melhor modelo: Regressão Logística

Motivos:
- Maior ROC-AUC
- Alto recall (capta a maior parte dos clientes que cancelam)
- Maior interpretabilidade em comparação aos modelos baseados em árvore

---

## 7. Impacto para o Negócio

A aplicação desse modelo permite:

- Identificar clientes com alto risco de cancelamento
- Direcionar campanhas de retenção de forma estratégica
- Reduzir perdas financeiras associadas ao churn
- Otimizar o uso do orçamento de marketing

Ao priorizar recall, o modelo reduz o número de clientes que cancelam sem serem previamente identificados.

