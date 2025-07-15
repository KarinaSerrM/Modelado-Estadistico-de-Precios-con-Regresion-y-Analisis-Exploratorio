# Modelado Predictivo de Precios de Vivienda con Regresión Lineal

Este repositorio contiene un proyecto de ciencia de datos enfocado en predecir precios de vivienda utilizando variables estructurales y de calidad. Se aplica regresión lineal múltiple y se optimiza el modelo considerando multicolinealidad y significancia estadística.

## Conjunto de datos

- `House_Pricing.csv`: contiene 1,460 registros con 81 variables que describen características físicas, constructivas y transaccionales de las viviendas.

## Flujo de trabajo

### 1. Carga y limpieza de datos
- Imputación de valores faltantes con mediana (`LotFrontage`)
- Eliminación de duplicados
- Verificación de consistencia y estructura del conjunto

### 2. Análisis exploratorio
- Estadísticas descriptivas: media, desviación estándar, cuartiles
- Visualización de distribuciones y outliers mediante histogramas y boxplots
- Variables clave: `SalePrice`, `GrLivArea`, `TotalBsmtSF`, `LotArea`, `YearBuilt`, entre otras

### 3. Correlación
- Matriz de correlación y heatmap
- Identificación de variables con alta correlación con `SalePrice`:  
  - `OverallQual` (0.79)  
  - `GrLivArea` (0.71)  
  - `TotalBsmtSF` (0.61)  
  - `1stFlrSF` (0.61)  
  - `YearBuilt` (0.52)

### 4. Modelado regresivo
- Modelo OLS inicial con todas las variables numéricas
- Evaluación de significancia estadística (`p < 0.05`) y multicolinealidad con VIF
- Selección de las 4 variables más significativas:
  - `OverallQual`, `GrLivArea`, `TotalBsmtSF`, `YearBuilt`

### 5. Modelo final
- R² ajustado: 0.757  
- Error Cuadrático Medio (MSE): 1,527,145,740 → raíz ≈ $39,078.71  
- Interpretación de coeficientes e impacto en el precio de venta
- Todas las variables seleccionadas son estadísticamente significativas

## Herramientas utilizadas

- Python 3.x  
- pandas  
- numpy  
- matplotlib  
- seaborn  
- statsmodels  
- scipy

## Conclusiones

- La calidad general de la vivienda (`OverallQual`) es el principal factor predictivo.
- El modelo ajustado ofrece buen desempeño con menor multicolinealidad.
- El flujo de trabajo desde el EDA hasta la validación fortalece el análisis de precios inmobiliarios.
