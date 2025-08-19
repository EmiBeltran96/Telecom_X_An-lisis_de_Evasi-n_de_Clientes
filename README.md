# 📊 Telecom X --- Análisis de Evasión de Clientes (Churn)

## 📌 Propósito del proyecto

Este proyecto analiza la **evasión de clientes (churn)** en la empresa
ficticia **Telecom X**.\
El objetivo es **identificar los factores que llevan a los clientes a
cancelar sus servicios** y generar **insights estratégicos** que puedan
ayudar al área de negocio a diseñar acciones para **reducir la tasa de
cancelación**.

El análisis sigue un proceso **ETL (Extracción, Transformación y
Carga)** y un **EDA (Análisis Exploratorio de Datos)**.

------------------------------------------------------------------------

## 📂 Estructura del proyecto

    TelecomX_Churn_Analysis/
    │
    ├── TelecomX_Churn_ETL_EDA.ipynb   # Notebook principal con ETL + EDA
    ├── TelecomX_clean.csv             # Dataset limpio generado en el pipeline
    ├── TelecomX_Data.json             # Datos originales (JSON desde API de GitHub)
    ├── README.md                      # Documentación del proyecto

------------------------------------------------------------------------

## 🔍 Flujo de trabajo (ETL + EDA)

1.  **Extracción de datos**
    -   Carga del dataset JSON desde GitHub.\
    -   Conversión a DataFrame de Pandas.
2.  **Transformación**
    -   Normalización de datos anidados (`customer`, `phone`,
        `internet`, `account`).\
    -   Limpieza de duplicados y valores nulos.\
    -   Conversión de tipos (numéricos y categóricos).\
    -   Creación de nueva variable: **`Cuentas_Diarias`** =
        `account_Charges_Monthly / 30.4`.
3.  **Carga**
    -   Exportación de un CSV limpio para modelado posterior.
4.  **Análisis Exploratorio (EDA)**
    -   Análisis descriptivo de variables numéricas.\
    -   Distribución global de churn.\
    -   Comparación de churn según variables categóricas y numéricas.

------------------------------------------------------------------------

## 📊 Ejemplos de gráficos e insights

### 1. Distribución de churn

👉 Aproximadamente **26% de los clientes cancelan**, mostrando una tasa
significativa de evasión.

### 2. Churn por tipo de contrato

👉 Los clientes con **contratos "Month-to-month"** tienen mucha mayor
probabilidad de churn que los de **1 o 2 años**.

### 3. Tenure vs churn

👉 Los clientes que cancelan suelen tener **tenures más cortos**, es
decir, llevan menos tiempo con la compañía.

------------------------------------------------------------------------

## 🛠️ Instrucciones de ejecución

1.  Clonar el repositorio:

    ``` bash
    git clone https://github.com/EmiBeltran96/Telecom_X_Analisis_de_Evasion_de_Clientes.git
    cd Telecom_X_Analisis_de_Evasion_de_Clientes
    ```

2.  Abrir el notebook en **Google Colab** o Jupyter:

    ``` bash
    jupyter notebook TelecomX_Churn_ETL_EDA.ipynb
    ```

3.  Instalar dependencias necesarias:

    ``` bash
    pip install pandas numpy matplotlib requests
    ```

4.  Ejecutar todas las celdas en orden para reproducir el análisis.

------------------------------------------------------------------------

## ✅ Conclusiones y recomendaciones

-   Los **contratos de corto plazo (Month-to-month)** son el principal
    indicador de churn.\
-   Clientes con **tenure bajo** y **cargos mensuales altos** presentan
    mayor evasión.\
-   La falta de **servicios adicionales (OnlineSecurity, TechSupport)**
    está asociada con mayor probabilidad de cancelación.

👉 **Recomendación:**\
Implementar **programas de fidelización**, ofrecer **descuentos en
contratos de largo plazo**, y **paquetes con servicios de
seguridad/soporte** para reducir la tasa de cancelación.

------------------------------------------------------------------------

💡 Este proyecto es la base para entrenar un **modelo predictivo de
churn**, que permitirá anticipar qué clientes están en riesgo de irse y
tomar acciones preventivas.
