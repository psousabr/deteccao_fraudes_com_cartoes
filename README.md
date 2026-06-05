# 🛡️ Detecção de Fraudes em Transações Financeiras

## 📌 Objetivo
Este projeto tem como objetivo aplicar técnicas de **Análise de Dados e Machine Learning** para identificar transações financeiras fraudulentas.  
Fraudes são raras e desbalanceadas em relação às transações legítimas, por isso o desafio é construir modelos que consigam detectar esses casos sem perder precisão.

---

## 🔎 Etapas do Projeto

### 1. **Coleta e Preparação dos Dados**
- Dataset utilizado: [creditcard.csv](https://storage.googleapis.com/download.tensorflow.org/data/creditcard.csv).
- Criação de novas variáveis (feature engineering), como:
  - `Amount_log` → transformação logarítmica do valor da transação.
  - `Amount_scaled` → padronização com `StandardScaler`.

### 2. **Problema de Classificação Desbalanceada**
- Apenas **0,17%** das transações são fraudes.
- Técnicas aplicadas:
  - **Undersampling** → reduzir a quantidade de transações normais.
  - **Oversampling (SMOTE)** → aumentar artificialmente os casos de fraude.

### 3. **Modelos Utilizados**
- **Regressão Logística**  
  - Modelo inicial para classificação binária.  
  - Métricas: precisão, recall, F1-score.  
  - AUC obtido: **0.927**.

- **Random Forest**  
  - Classificador baseado em múltiplas árvores de decisão.  
  - Utilizado com `class_weight="balanced"` para lidar com desbalanceamento.

- **XGBoost**  
  - Algoritmo avançado de boosting.  
  - Parâmetro `scale_pos_weight` ajustado para dar mais peso às fraudes.  
  - Resultados: recall e precisão superiores, com F1-score de **0.85** para a classe fraude.

### 4. **Avaliação dos Modelos**
- **Métricas principais**:
  - **Recall** → mais importante, pois indica quantas fraudes foram detectadas.
  - **Precision** → evita falsos positivos.
  - **F1-Score** → equilíbrio entre recall e precision.
- **Curvas de avaliação**:
  - **ROC Curve** → análise da taxa de verdadeiros positivos vs falsos positivos.
  - **Precision-Recall Curve** → útil em cenários desbalanceados.

### 5. **Explicabilidade**
- **Importância das variáveis** → análise de quais atributos mais influenciam o modelo.
- **SHAP Values** → explicação individual das decisões do modelo, mostrando como cada variável impacta a classificação.

---

## 🚀 Conclusão
O projeto demonstra como aplicar técnicas de **ciência de dados e aprendizado de máquina** para detectar fraudes em transações financeiras.  
Mesmo com dados altamente desbalanceados, o uso de **feature engineering, balanceamento de classes e modelos avançados (XGBoost)** permite alcançar alta performance e confiabilidade.

---

Feito com muito ☕ por Joice Pinheli
