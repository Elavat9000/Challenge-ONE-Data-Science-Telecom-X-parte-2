# 📊 Telecom X – Predicción de Cancelación de Clientes

Este proyecto analiza y predice la cancelación de clientes (**churn**) en una empresa de telecomunicaciones. A través de técnicas de ciencia de datos y machine learning, se identifican patrones de cancelación y se proponen estrategias de retención.

---

## 📁 Estructura del Proyecto TelecomX  

Aquí te va el breakdown de cómo está organizado este desmadre:  

```bash
├── /data/                    # 👉 Aquí vive la data limpia y lista pa' chambear
│   └── datos_tratados.csv    # 📊 El CSV con toda la info procesada
│
├── TelecomX_LATAM.ipynb      # 💻 El Jupyter Notebook con todo el análisis (el alma del proyecto)
│
├── README.md                 # 📖 La biblia del proyecto (explicaciones y instrucciones)
│
└── /Imagenes/                # 🖼️ Aquí están los screenshots pa'l reporte
    ├── boxplot_charges_total_churn.png       # 📦 Boxplot de gastos vs. cancelación
    ├── boxplot_tenure_churn.png              # ⏳ Boxplot de antigüedad vs. cancelación
    ├── comparacion_modelos.png               # 🤼 Comparación de KNN vs. Random Forest
    ├── matriz_correlacion_numericas.png      # 🔗 Matriz de correlación (pa' ver relaciones)
    ├── scatterplot_tenure_charges_churn.png  # ✨ Scatterplot de antigüedad vs. gastos
    ├── top15_importancia_knn.png             # 🏆 Variables más importantes en KNN
    └── top15_importancia_rf.png              # 🥇 Variables más importantes en Random Forest




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
## 🔧 Preparación de los Datos

### 📌 Clasificación de Variables

- **Categóricas**: Género, método de pago, tipo de contrato, servicio de internet, etc.
- **Numéricas**: Gasto mensual, gasto total, duración del contrato, etc.
### 🧼 Proceso de Limpieza y Tratamiento

- Eliminación de valores nulos o erróneos.
- Conversión de variables categóricas a formato numérico usando codificación One-Hot.
- Aplicación de **SMOTE** para balancear clases desbalanceadas (clientes cancelados vs. activos).
- Escalado de variables numéricas con `StandardScaler`.

---

### 🔀 División de Datos

- Se dividió el dataset en **conjunto de entrenamiento (train)** y **conjunto de prueba (test)** para evaluar de forma justa el desempeño de los modelos.

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


## 💡 Factores que más influyen en la cancelación

Según el análisis de importancia de variables (usando Random Forest y método manual para KNN):

- **Duración del contrato**
- **Gasto total**
- **Método de pago**
- **Tipo de cliente (con o sin dependientes, pareja)**
- **Servicio técnico o de internet**

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

Puedes abrir y ejecutar el análisis fácilmente desde Google Colab:

👉 [Abrir TelecomX_LATAM.ipynb](https://github.com/Elavat9000/Challenge-ONE-Data-Science-Telecom-X-parte-2/blob/main/Telecom_X_parte_2.ipynb)

**Pasos:**
1. Haz clic en el enlace de arriba.
2. Haz clic en "Open in colab"
3. Inicia sesión con tu cuenta de Google (si no lo has hecho).
4. Ejecuta las celdas del notebook (una por una o con “Ejecutar todo Ctrl+F9”).
5. El dataset se carga desde una URL pública en GitHub, por lo que no necesitas subir nada.

## 📫 Autor

**Francisco Javier Cervantes Mendieta**  
[LinkedIn](https://www.linkedin.com/in/francisco-javier-cervantes-mendieta-327575213/) · [GitHub](https://github.com/Elavat9000)

---

## ⚖️ Licencia

Este proyecto está bajo la [Licencia MIT](https://opensource.org/licenses/MIT).
