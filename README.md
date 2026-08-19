# Análisis de Población Vehicular — Proyecto de Minería de Datos

Proyecto de minería de datos aplicado a un dataset real de venta de vehículos usados, con el objetivo de explorar patrones de precio y kilometraje, segmentar el mercado mediante clustering, y modelar la relación entre variables usando distintas técnicas de regresión.

## Dataset

599 registros de vehículos con las siguientes variables: modelo, año, kilometraje (Kmh), color, tipo de transmisión, tipo de combustible y precio.

## Tecnologías utilizadas

- **Python**
- **pandas** — limpieza y manipulación de datos
- **matplotlib / seaborn** — visualización exploratoria
- **scikit-learn** — modelos de clustering, regresión y reducción de dimensionalidad
- **numpy**

## Estructura del análisis

### 1. Modelado de datos en esquema estrella
Diseño de un modelo dimensional (esquema estrella) para representar el dataset de forma analítica.

### 2. Limpieza y transformación de datos
- Detección de registros duplicados
- Tratamiento de valores nulos (NaN)
- Corrección de tipos de dato (conversión de campos numéricos almacenados como texto)

### 3. Análisis exploratorio (EDA)
Cinco visualizaciones para entender la distribución y evolución del dataset:
- Distribución de vehículos por tipo de transmisión
- Evolución de tipos de vehículo por año (barras apiladas)
- Proporción de los 10 modelos más comunes (gráfica de pastel)
- Evolución del número de vehículos por año de modelo
- Top 20 modelos más comunes

### 4. Clustering (K-Means + PCA)
- Segmentación de vehículos según kilometraje y precio mediante K-Means
- Determinación del número óptimo de clusters con el método del codo
- Reducción de dimensionalidad con PCA y comparación de clustering antes/después

### 5. Modelos de regresión
Se probaron y compararon distintos enfoques para predecir el kilometraje a partir de otras variables:
- Regresión lineal simple (Precio → Kilometraje)
- Regresión lineal múltiple (Año y Precio → Kilometraje)
- Regularización: Ridge, Lasso y ElasticNet

**Resultados (R² sobre datos de prueba):**

| Modelo | R² |
|---|---|
| Regresión lineal simple | 0.16 |
| Regresión lineal múltiple | 0.39 |
| Ridge | 0.39 |
| Lasso | 0.39 |
| ElasticNet | 0.39 |

Los valores de R² moderados reflejan que el precio y el año por sí solos explican solo una parte de la variación en el kilometraje — es un resultado esperado dado el tamaño y la naturaleza del dataset, y muestra el límite real del modelo en vez de forzar una métrica artificialmente alta.

## Cómo ejecutarlo

El proyecto está desarrollado en un notebook de Jupyter.

```bash
pip install pandas matplotlib seaborn scikit-learn numpy
jupyter notebook
```

Abrir el archivo `.ipynb` y ejecutar las celdas en orden.

## Estado actual

Proyecto académico: incluye limpieza de datos, modelado dimensional, análisis exploratorio, clustering y varios modelos de regresión con evaluación de métricas (R², MSE, RMSE, MAE).
