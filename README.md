# TelecomX-LATAM
Reto alura TelecomX LATAM parte 1
# Análisis de Evasión de Clientes (Churn) en TelecomX

## 📝 Descripción del Proyecto

Este proyecto tiene como objetivo principal realizar un análisis exhaustivo del fenómeno de la **evasión de clientes (Churn)** en la empresa de telecomunicaciones TelecomX. A través del procesamiento, limpieza, análisis exploratorio y visualización de los datos de clientes, buscamos identificar patrones y factores clave que influyen en la decisión de un cliente de cancelar su servicio. El análisis culmina con la formulación de conclusiones y recomendaciones estratégicas orientadas a la retención de clientes.

## 🗃️ Fuente de Datos

Los datos utilizados para este análisis provienen de un archivo JSON (`TelecomX_Data.json`) que contiene información detallada sobre los clientes de TelecomX, incluyendo sus datos demográficos, servicios contratados, facturación y si han cancelado o no su servicio.

## 🚀 Pasos del Análisis

El análisis se estructuró en las siguientes fases clave:

### 1. Carga y Normalización de Datos

* **Carga del JSON**: El archivo `TelecomX_Data.json` fue cargado en Google Colab.
* **Normalización de Objetos Anidados**: Dado que el JSON contenía objetos anidados (ej., `customer`, `phone`, `internet`, `account`), se utilizó `pd.json_normalize()` para aplanar la estructura y crear un DataFrame tabular.

### 2. Limpieza y Preprocesamiento de Datos

* **Manejo de Valores Ausentes**: Se identificaron y trataron valores faltantes, específicamente en la columna `TotalCharges`, donde los espacios vacíos (`' '`) se convirtieron a `NaN` y luego se imputaron con la media.
* **Revisión de Duplicados**: Se verificó y eliminó cualquier fila duplicada en el conjunto de datos.
* **Estandarización de Variables Categóricas**: Las columnas con respuestas binarias ("Yes", "No") se convirtieron a valores numéricos (1 y 0) para facilitar el análisis y futuros modelos.
* **Creación de Nuevas Características**: Se derivó la columna `Cuentas_Diarias` (facturación diaria) dividiendo `MonthlyCharges` entre 30, ofreciendo una granularidad de análisis adicional.

### 3. Análisis Descriptivo de Datos (EDA)

* **Estadísticas Resumen**: Se calcularon métricas como media, mediana, desviación estándar, mínimo y máximo para las columnas numéricas (`tenure`, `MonthlyCharges`, `TotalCharges`, `Cuentas_Diarias`) para entender su distribución central y dispersión.
* **Distribución de Churn**: Se visualizó la proporción de clientes que cancelaron y los que no, revelando un desbalance significativo en las clases. 
* **Churn por Variables Categóricas**: Se exploró la relación entre `Churn` y variables como género, tipo de contrato, método de pago, etc., utilizando gráficos de barras para identificar perfiles de riesgo. 
* **Churn por Variables Numéricas**: Se analizaron las distribuciones de `tenure`, `MonthlyCharges` y `TotalCharges` para clientes con y sin Churn, utilizando gráficos de densidad para identificar tendencias. 

## 📊 Conclusiones e Insights Clave

* **Early Churners**: Los clientes con bajo **tiempo de contrato** (`tenure`) y **cargos totales bajos** son los más propensos a la evasión.
* **Tipo de Contrato**: Los **contratos mes a mes** están fuertemente asociados con una mayor tasa de Churn.
* **Métodos de Pago y Servicio**: El uso de **fibra óptica** y el **cheque electrónico** como método de pago se correlacionan con una mayor probabilidad de evasión.
* **Costos Mensuales**: Los clientes con **cargos mensuales más altos** muestran una mayor tendencia a cancelar.

## 💡 Recomendaciones Estratégicas

Basado en el análisis, se proponen las siguientes recomendaciones para reducir la evasión de clientes:

1.  **Programas de Onboarding y Retención Temprana**: Dirigir esfuerzos específicos a clientes nuevos y aquellos en sus primeros meses de servicio, ofreciendo soporte proactivo y valor añadido.
2.  **Incentivos para Contratos a Largo Plazo**: Promover activamente los contratos de uno o dos años con beneficios atractivos para reducir la inestabilidad de los contratos mes a mes.
3.  **Análisis de Precios de Fibra Óptica**: Revisar la competitividad y el valor percibido de los planes de fibra óptica, especialmente para clientes con altos cargos mensuales.
4.  **Optimización de Métodos de Pago**: Evaluar la experiencia del cliente con el método de pago por cheque electrónico e incentivar la adopción de métodos de pago más convenientes y de menor riesgo de Churn.

## 🛠️ Tecnologías Utilizadas

* **Python**
* **Pandas**: Para manipulación y análisis de datos.
* **Matplotlib**: Para la creación de gráficos.
* **Seaborn**: Para visualizaciones estadísticas avanzadas.

## 👥 Contacto

Para cualquier pregunta o sugerencia, no dudes en contactar a [Tu Nombre/Correo electrónico o GitHub].
