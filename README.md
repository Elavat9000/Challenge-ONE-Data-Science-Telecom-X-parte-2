# 📊 Telecom X – Predicción de Cancelación de Clientes

Este proyecto analiza y predice la cancelación de clientes (**churn**) en una empresa de telecomunicaciones. A través de técnicas de ciencia de datos y machine learning, se identifican patrones de cancelación y se proponen estrategias de retención.

---

## 📁 Estructura del proyecto



## 🎯 Objetivos

- Predecir si un cliente cancelará su servicio.
- Identificar los factores que más influyen en la cancelación.
- Evaluar distintos modelos de clasificación.
- Proponer estrategias basadas en datos para reducir el churn.

---

## 🗂️ Dataset

- Fuente: [`datos_tratados.csv`](https://raw.githubusercontent.com/Elavat9000/Challenge-ONE-Data-Science-Telecom-X-parte-2/refs/heads/main/Data/datos_tratados.csv)
- Registros: ~7,000 clientes
- Variables: Demográficas, tipo de servicio, contratos, pagos, duración y cargos mensuales/totales.

---

## 📊 Análisis exploratorio (EDA)

- Se visualizó la correlación entre variables y su relación con `Churn`.
- Se analizaron patrones con gráficos como:
  - Boxplots (`TotalCharges vs Churn`)
  - Scatterplots (`Tenure vs Churn`)
  - Gráficos de barras para variables categóricas (`Contract`, `PaymentMethod`, etc.)
- Se aplicó **SMOTE** para balancear las clases.

---

## 🤖 Modelos utilizados

| Modelo            | Accuracy | Precisión | Recall | F1-score | Entrenamiento |
|-------------------|----------|-----------|--------|----------|----------------|
| DummyClassifier   | 0.7345   | 0.0000    | 0.0000 | 0.0000   | -              |
| KNN               | 0.7487   | 0.5280    | 0.5045 | 0.5160   | 0.8422         |
| Random Forest     | 0.7847   | 0.6123    | 0.5152 | 0.5595   | 0.9978         |

> **Nota:** Se ajustaron hiperparámetros y se detectó overfitting en ambos modelos, con mejores resultados generales para **Random Forest**.

---

## 🔍 Variables más influyentes

- `Contract`
- `tenure` (tiempo en la empresa)
- `MonthlyCharges`
- `TotalCharges`
- `PaymentMethod`
- `InternetService`

Estas fueron seleccionadas a partir de:
- Importancia de variables (Random Forest + Permutation Importance)
- Análisis gráfico y correlacional

---

## 💡 Conclusiones

- El modelo más robusto fue **Random Forest**, con un F1-score de **0.62**.
- Clientes con contratos mensuales, poco tiempo en la empresa y cargos elevados tienen mayor probabilidad de cancelar.
- El **overfitting** fue controlado mediante ajuste de hiperparámetros y validación cruzada.
- Aplicar balanceo de clases fue clave para mejorar el recall y F1.

---

## 🧠 Estrategias de retención sugeridas

- Promociones para clientes nuevos (evitar pérdida temprana)
- Incentivar contratos anuales o bianuales
- Reducción o flexibilidad en cargos mensuales elevados
- Fomentar el pago automático para reducir fricciones

---

## ⚙️ Tecnologías utilizadas

- **Lenguaje:** Python 3
- **Librerías:** pandas, numpy, seaborn, matplotlib, scikit-learn, imbalanced-learn
- **Entorno:** Google Colab Notebook

---

## 🚀 Cómo ejecutar el proyecto
