# 📊 Análisis Avanzado e Integración de Datos BCP (Bank & Customer Profiling)

## 📌 Descripción del Proyecto

Este proyecto aborda la extracción, limpieza, transformación e integración de datos (ETL) de dos fuentes independientes de una entidad bancaria:

1. **bank.ipynb**: Datos operativos de campañas de telemarketing, interacción comercial y variables macroeconómicas.
2. **customers.ipynb**: Información socioeconómica, estructura familiar y comportamiento digital de los clientes.

El objetivo principal ha sido unificar ambos entornos de datos en un dataset maestro de 30 columnas y 43,000 registros, eliminando incoherencias, tratando valores nulos e imputando datos clave para habilitar análisis predictivos y segmentaciones de clientes de alto valor.

---

## 🛠️ Tecnologías y Librerías Utilizadas

* **Lenguaje:** Python
* **Entorno de Desarrollo:** VS Code / Jupyter Notebooks
* **Procesamiento de Datos:** pandas, numpy
* **Visualización:** matplotlib, seaborn
* **Lectura de Ficheros:** openpyxl

---

## 📐 Estructura del Repositorio

* **data/**: Ficheros de datos (bank.csv y customer-details.xlsx)
* **bank.ipynb**: Notebook de ETL y análisis inicial de datos bancarios
* **customers.ipynb**: Notebook de ETL, cruce e integración final (df_merged)
* **README.md**: Documentación general del proyecto

---

## 🔄 Flujo de Trabajo ETL (Extract, Transform, Load)

### 1. Limpieza y Normalización de Datos (bank)
* **Tratamiento de Nulos:** Imputación de variables continuas mediante la mediana para minimizar el impacto de valores extremos.
* **Normalización de Categóricas:** Asignación del identificador 'unknown' a registros incompletos.
* **Formateo de Fechas:** Conversión de la columna date al estándar nativo datetime.

### 2. Transformación e Ingeniería de Características (customers)
* **Eliminación de Redundancias:** Depuración de índices duplicados.
* **Nuevas Variables Creadas:**
  * Total_Dependents: Suma directa de menores y adolescentes.
  * Has_Kids: Flag binario (1/0) que categoriza la presencia de hijos.

### 3. Integración Final de Datasets
* **Cruce Integrado:** Realización de un Inner Join entre df_bank (id_) y df_customer (ID).

---

## 📊 Arquitectura del Dataset Integrado (df_merged)

El dataset final consolidado reúne 30 variables organizadas en 5 dimensiones estratégicas:

* **Socioeconómica:** Income, age, job, education (Capacidad financiera y perfil demográfico).
* **Estructura Familiar:** Kidhome, Teenhome, Total_Dependents, Has_Kids (Composición del hogar).
* **Salud Financiera:** housing, loan, default, NumWebVisitsMonth (Endeudamiento y adopción digital).
* **Operativa Comercial:** contact, duration, campaign, poutcome (Métricas de llamadas e historial).
* **Macroeconómica / Objetivo:** euribor3m, cons.price.idx, y (Entorno económico y Variable Objetivo).

---

## 🚀 Casos de Uso y Aplicaciones Futuras

1. **Modelado Predictivo de Conversión:** Entrenamiento de algoritmos de Machine Learning utilizando 'y' para identificar los clientes con mayor probabilidad de contratación.
2. **Segmentación por Valor de Cliente (CLV):** Identificación de clústeres de clientes basados en la relación entre ingresos y hábitos digitales.
3. **Optimización de Campañas:** Análisis de sensibilidad sobre la variable duration para optimizar la eficiencia del call center.

---

## 👤 Autora
* **Laura** — Desarrollo de ETL y Análisis de Datos
