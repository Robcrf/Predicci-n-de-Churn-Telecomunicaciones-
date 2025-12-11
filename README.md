# Predicción de Fuga de Clientes (Churn) en Telecomunicaciones

Este repositorio contiene un proyecto de ciencia de datos enfocado en predecir la fuga de clientes (churn) para una empresa de telecomunicaciones. El objetivo es construir un modelo de Machine Learning que identifique a los clientes con alta probabilidad de cancelar su servicio, permitiendo a la empresa implementar estrategias de retención de manera proactiva.

---

## 📋 Tabla de Contenidos
- [Objetivo del Proyecto](#-objetivo-del-proyecto)
- [Dataset](#-dataset)
- [Metodología](#-metodología)
- [Resultados y Conclusiones](#-resultados-y-conclusiones)
- [Cómo Utilizar este Repositorio](#-cómo-utilizar-este-repositorio)
- [Tecnologías Utilizadas](#-tecnologías-utilizadas)

---

## 🎯 Objetivo del Proyecto

El principal objetivo es reducir la pérdida de ingresos causada por la fuga de clientes. Esto se logra a través de:
1.  **Análisis Exploratorio de Datos (EDA):** Identificar los factores y características clave que más influyen en la decisión de un cliente de abandonar la compañía.
2.  **Modelado Predictivo:** Desarrollar y evaluar múltiples modelos de clasificación para encontrar el que mejor prediga el churn.
3.  **Recomendaciones Estratégicas:** Proporcionar a la empresa insights accionables basados en los hallazgos para mejorar la retención de clientes.

---

## 💾 Dataset

Los datos están segmentados en cuatro archivos CSV, que contienen información sobre los contratos, servicios de internet, datos personales y servicios telefónicos de los clientes.

- `contract.csv`: Detalles del contrato, método de pago y cargos.
- `internet.csv`: Información sobre servicios de internet como seguridad online, soporte técnico, etc.
- `personal.csv`: Datos demográficos del cliente (género, si es adulto mayor, etc.).
- `phone.csv`: Información sobre si el cliente tiene servicio telefónico y líneas múltiples.

El notebook `Telecom_Churn_Prediction_Portfolio_v2.ipynb` unifica y procesa estos archivos para el análisis.

---

## ⚙️ Metodología

El proyecto sigue un flujo de trabajo estructurado de ciencia de datos:

1.  **Carga y Limpieza de Datos:** Se cargan los 4 datasets, se corrigen los tipos de datos y se fusionan en un único DataFrame.
2.  **Ingeniería de Características:** Se crean nuevas variables como `churn` (nuestra variable objetivo) y `tenure_months` (antigüedad del cliente).
3.  **Análisis Exploratorio (EDA):** Se utilizan visualizaciones para entender la distribución de los datos y la relación entre las variables y la tasa de churn.
4.  **Preprocesamiento para Modelado:** Se prepara el dataset para el entrenamiento, aplicando escalado a las variables numéricas y codificación (One-Hot Encoding) a las categóricas.
5.  **Manejo de Desbalance de Clases:** Se utiliza la técnica SMOTENC para sobremuestrear la clase minoritaria (clientes que hacen churn) y asegurar que el modelo aprenda a identificarla correctamente.
6.  **Entrenamiento y Evaluación:** Se entrenan y evalúan 5 modelos de clasificación diferentes (Dummy, Regresión Logística, Árbol de Decisión, Random Forest y XGBoost). El rendimiento se mide utilizando métricas como F1-Score, Precisión y Recall, además de la matriz de confusión.

---

## 📊 Resultados y Conclusiones

### Hallazgos Clave del Análisis
- **Tipo de Contrato:** Los clientes con contratos `Mes a mes` son drásticamente más propensos a cancelar.
- **Antigüedad:** Los clientes nuevos tienen una probabilidad mucho mayor de irse. La lealtad aumenta significativamente con el tiempo.
- **Servicios de Soporte:** La falta de servicios como `Soporte Técnico` y `Seguridad Online` está fuertemente correlacionada con una mayor tasa de churn.

### Rendimiento del Modelo
El modelo **Random Forest** fue seleccionado como el de mejor rendimiento general, logrando un **F1-Score de 0.61** para la clase minoritaria (Churn). Este modelo ofrece un excelente equilibrio entre la capacidad de identificar correctamente a los clientes que se irán (Recall) y no clasificar erróneamente a los clientes leales (Precision).

### Recomendaciones Estratégicas
1.  **Fidelizar a Clientes Nuevos:** Implementar campañas de bienvenida y seguimiento durante los primeros meses.
2.  **Incentivar Contratos a Largo Plazo:** Ofrecer descuentos o beneficios a los clientes con contratos `Mes a mes` para que migren a planes anuales.
3.  **Promover Servicios de Valor:** Ofrecer paquetes que incluyan `Soporte Técnico` y `Seguridad Online` a los clientes de alto riesgo.

---

## 🚀 Cómo Utilizar este Repositorio

1.  **Clona el repositorio:**
    ```bash
    git clone https://github.com/Robcrf/Predicci-n-de-Churn-Telecomunicaciones-.git
    ```
2.  **Navega al directorio del proyecto:**
    ```bash
    cd Predicci-n-de-Churn-Telecomunicaciones-
    ```
3.  **Instala las dependencias:**
    Asegúrate de tener las librerías listadas en la sección de tecnologías. Puedes instalarlas usando pip:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn xgboost imbalanced-learn
    ```
4.  **Ejecuta el Jupyter Notebook:**
    Abre y ejecuta las celdas en `Telecom_Churn_Prediction_Portfolio_v2.ipynb` para replicar el análisis y los resultados.

---

## 🛠️ Tecnologías Utilizadas

- **Python 3**
- **Pandas:** Para manipulación y análisis de datos.
- **NumPy:** Para operaciones numéricas.
- **Matplotlib & Seaborn:** Para visualización de datos.
- **Scikit-learn:** Para preprocesamiento, modelado y evaluación.
- **Imbalanced-learn:** Para manejar el desbalance de clases (SMOTENC).
- **XGBoost:** Para el modelo de Gradient Boosting.
- **Jupyter Notebook:** Como entorno de desarrollo.

---

*Última actualización: 11 de diciembre de 2025*
