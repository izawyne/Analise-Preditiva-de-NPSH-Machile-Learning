# 📊 Análise Preditiva de NPSH: Impacto de Variáveis Correlacionadas no Desempenho do Modelo

## 🎯 Objetivo do Projeto

Este projeto tem como objetivo desenvolver um modelo preditivo robusto para estimar o NPSH (Net Positive Suction Head) de bombas em uma planta química, utilizando parâmetros operacionais como variáveis de entrada. O banco de dados contém informações de:

- Vazão (m³/h)  
- Diâmetro do rotor (m)  
- Velocidade (RPM)  
- Temperatura (°C)  
- Altura (m)  
- NPSH (m)

---

## 🧪 Estratégia do Projeto

Para investigar o impacto da multicolinearidade e avaliar a importância da variável “Velocidade” na previsão do NPSH, foram desenvolvidos dois modelos preditivos com **SVR (Support Vector Regression)**:

### 🔹 Modelo 1: Com a variável “Velocidade”
Utiliza todas as variáveis disponíveis no banco de dados como preditores, incluindo a variável “Velocidade”.

### 🔹 Modelo 2: Sem a variável “Velocidade”
Remove a variável “Velocidade” para verificar se sua exclusão afeta significativamente o desempenho preditivo.

Essa abordagem permite analisar se a presença de variáveis altamente correlacionadas compromete a capacidade de generalização do modelo.

---

## ⚙️ Detalhes Técnicos

- **Modelo:** SVR (Support Vector Regression)
- **Normalização:** `MinMaxScaler`
- **Ajuste de Hiperparâmetros:** `GridSearchCV` com validação cruzada k-fold (k=10)
- **Métricas de Avaliação:**
  - MSE (Mean Squared Error)
  - MAE (Mean Absolute Error)
  - RMSE (Root Mean Squared Error)
  - R² (Coeficiente de Determinação)

---

## 📈 Resultados

### ✅ Modelo com todas as variáveis:
- MSE: `0.0036`  
- MAE: `0.0528`  
- RMSE: `0.0603`  
- R²: `0.9901`  
- MSE (generalização): `0.0036`

### ⚠️ Modelo sem a variável “Velocidade”:
- MSE: `0.3983`
- MAE: `0.5491`  
- RMSE: `0.6312`  
- R²: `-0.0806`  
- MSE (generalização): `0.3984`

---

## ✅ Conclusão

A comparação dos modelos mostrou que a variável “Velocidade” é extremamente relevante para prever o NPSH com precisão. Sua exclusão causou uma queda significativa na performance do modelo, evidenciando os efeitos da multicolinearidade, mas também ressaltando sua importância como preditor.

Este projeto demonstra como a análise cuidadosa de variáveis pode impactar o desempenho de modelos de regressão, além de destacar o uso do SVR como ferramenta eficaz na predição de variáveis críticas em processos industriais.

---

## 👩‍💻 Desenvolvido por

Izabella Wyne  
[LinkedIn](https://www.linkedin.com/in/izabellawyne/) • [GitHub](https://github.com/izawyne)

---
