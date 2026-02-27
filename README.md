# 📡 TelecomX — Análisis de Evasión de Clientes (Churn)

> Proyecto de análisis exploratorio de datos para identificar los factores que explican la alta tasa de abandono de clientes en Telecom X.

---

## 📌 Propósito del Análisis

TelecomX enfrenta una tasa de evasión de clientes (churn) de aproximadamente **26.5%**, lo que representa una pérdida significativa de ingresos. Este proyecto tiene como objetivo:

- Extraer y limpiar los datos desde una API en formato JSON.
- Realizar un análisis exploratorio (EDA) para identificar patrones de abandono.
- Entregar los datos transformados al equipo de ciencia de datos para un modelo predictivo.

---

## 🗂️ Estructura del Proyecto

```
TelecomX/
│
├── TelecomX_LATAM.ipynb       # Notebook principal con todo el análisis
├── TelecomX_Data.json         # Datos originales extraídos de la API
├── TelecomX_diccionario.md    # Diccionario de variables del dataset
├── TelecomX_clean.csv         # Dataset limpio (generado tras ejecutar el notebook)
└── README.md                  # Este archivo
```

---

## 🔧 Tecnologías Utilizadas

| Herramienta | Uso |
|---|---|
| Python 3 | Lenguaje principal |
| Pandas | Manipulación y limpieza de datos |
| NumPy | Operaciones numéricas |
| Matplotlib | Visualizaciones |
| Seaborn | Gráficos estadísticos |
| Requests | Extracción de datos desde API |

---

## 📊 Proceso ETL

### 1. Extracción
- Los datos se obtienen desde una API en formato JSON.
- El JSON tiene estructura anidada (cliente, teléfono, internet, cuenta).
- Se usa `pd.json_normalize()` para aplanar el dataset.

### 2. Transformación
- Renombramiento de columnas para mayor claridad.
- Conversión de `TotalCharges` de string a numérico.
- Conversión de `SeniorCitizen` de 0/1 a Yes/No.
- Imputación de valores nulos en `TotalCharges` con 0.
- Eliminación de filas con `Churn` vacío.
- Codificación de `Churn` en 0/1.
- Creación de la variable `DailyCharges`.

### 3. Análisis
Se generan 9 visualizaciones clave que cubren:
- Distribución general del churn.
- Churn por variables demográficas.
- Impacto del tipo de contrato.
- Servicio de internet y churn.
- Permanencia y cargos mensuales.
- Método de pago.
- Correlaciones.
- Servicios adicionales.

---

## 💡 Principales Hallazgos

| Factor | Hallazgo |
|---|---|
| **Contrato mes a mes** | +40% de tasa de churn |
| **Fibra óptica** | ~42% de churn (el más alto) |
| **Tenure promedio churn** | ~18 meses vs 37 meses (no churn) |
| **Cheque electrónico** | Método de pago con mayor churn (~45%) |
| **Adultos mayores** | Tasa de churn ~41% |

---

## ▶️ Instrucciones de Ejecución

1. Clona este repositorio:
```bash
git clone https://github.com/tu-usuario/telecomx-churn.git
cd telecomx-churn
```

2. Abre el notebook en Google Colab o Jupyter:
```bash
jupyter notebook TelecomX_LATAM.ipynb
```

3. Ejecuta las celdas en orden (Extracción → Transformación → Análisis → Informe).

4. El dataset limpio se exportará automáticamente como `TelecomX_clean.csv`.

---

## 📋 Diccionario de Variables

| Variable | Descripción |
|---|---|
| `customerID` | ID único del cliente |
| `Churn` | Si el cliente abandonó (1) o no (0) |
| `gender` | Género del cliente |
| `SeniorCitizen` | Si el cliente tiene 65+ años |
| `Partner` | Si tiene pareja |
| `Dependents` | Si tiene dependientes |
| `tenure` | Meses de permanencia |
| `Contract` | Tipo de contrato |
| `MonthlyCharges` | Cargo mensual total |
| `TotalCharges` | Total acumulado pagado |
| `InternetService` | Tipo de internet contratado |
| `PaymentMethod` | Método de pago |

---

## 👤 Autor

Proyecto desarrollado como parte del desafío **TelecomX** del programa **ONE — Alura LATAM**.

---

*📅 2024 | Análisis Exploratorio de Datos*
