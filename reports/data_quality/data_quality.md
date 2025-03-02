# 🧹 Calidad de Datos

## Descripción
Este informe analiza la calidad de los datos, los problemas encontrados y las estrategias de limpieza aplicadas durante el proyecto de predicción de precios de ganado. Se detallan los métodos utilizados para mejorar la calidad del dataset, así como los resultados obtenidos.

---

## Análisis de Valores Nulos, Inconsistencias y Sesgos

### 1. **Valores Nulos**
Se identificaron valores nulos en varias columnas clave del dataset principal (`Bd_Transacciones.csv`), incluyendo:

- **Raza**: 15% de valores nulos.
- **Marca**: 10% de valores nulos.
- **Peso**: 5% de valores nulos.
- **Tipo_Remate**: 8% de valores nulos.

**Estrategias de imputación**:
- Para columnas categóricas como `Raza` y `Marca`, se rellenaron los valores nulos con "Desconocido" y "Sin Marca", respectivamente.
- Para la columna numérica `Peso`, se utilizó la mediana para imputar los valores faltantes.
- Para `Tipo_Remate`, se rellenaron los valores nulos con "Desconocido".

### 2. **Inconsistencias**
Se detectaron inconsistencias en los datos, como:

- **Precio_Kilo**: Algunos registros tenían valores extremadamente bajos o cercanos a cero, lo que no era coherente con el contexto del mercado ganadero.
- **Fecha**: Algunas fechas estaban en formatos inconsistentes o eran inválidas.

**Correcciones aplicadas**:
- Se eliminaron registros con `Precio_Kilo` menor a $1, ya que se consideraron errores o datos no válidos.
- Se estandarizó el formato de la columna `Fecha` utilizando `pd.to_datetime`.

### 3. **Sesgos**
Se analizó la distribución de los datos para detectar posibles sesgos:

- **Distribución de Precio_Kilo**: Se identificó una distribución sesgada hacia la derecha, con algunos valores extremadamente altos (outliers).
- **Distribución de Peso**: Se encontró una distribución relativamente normal, pero con algunos valores atípicos.

**Correcciones aplicadas**:
- Se eliminaron outliers en `Precio_Kilo` utilizando el rango intercuartílico (IQR).
- Se ajustaron los valores extremos en `Peso` utilizando la técnica de clipping.

---

## Métodos Utilizados para Mejorar la Calidad del Dataset

### 1. **Limpieza de Datos**
- **Imputación de valores nulos**: Se utilizaron técnicas de imputación basadas en la mediana para variables numéricas y valores predeterminados para variables categóricas.
- **Eliminación de outliers**: Se aplicó el rango intercuartílico (IQR) para detectar y eliminar valores atípicos en `Precio_Kilo` y `Peso`.

### 2. **Integración de Datos Externos**
- **Datos climáticos**: Se integraron datos de `clima.csv` para enriquecer el dataset con variables como `Temperatura_Minima` y `Precipitacion`.
- **Tipo de cambio del dólar**: Se incorporó el tipo de cambio del dólar desde `dolar.csv` para ajustar los precios según la fluctuación monetaria.

### 3. **Transformación de Variables**
- **Codificación de variables categóricas**: Se aplicó **Label Encoding** para variables como `Raza` y `Marca`, y **One-Hot Encoding** para `Tipo_Remate`.
- **Escalado de variables numéricas**: Se normalizaron variables como `Peso`, `Dolar`, y `Temperatura_Minima` utilizando **StandardScaler**.

---

# ✅ Validación de Datos

## Descripción
Este documento describe los métodos de validación aplicados para garantizar la calidad y coherencia de los datos procesados. Se detallan los errores detectados, las correcciones implementadas y la evaluación final de la calidad del dataset.

---

## Métodos de Validación Aplicados

### 1. **Validación de Integridad**
- **Verificación de valores nulos**: Se verificó que no quedaran valores nulos en las columnas clave después de la imputación.
- **Consistencia de fechas**: Se validó que todas las fechas estuvieran en el formato correcto y fueran coherentes con el rango temporal del proyecto.

### 2. **Validación de Outliers**
- **Detección de outliers**: Se utilizó el rango intercuartílico (IQR) para identificar y corregir valores atípicos en `Precio_Kilo` y `Peso`.
- **Ajuste de valores extremos**: Se aplicó la técnica de clipping para limitar los valores dentro de un rango razonable.

### 3. **Validación de Datos Externos**
- **Consistencia de datos climáticos**: Se verificó que los datos de `clima.csv` estuvieran completos y fueran coherentes con las fechas del dataset principal.
- **Consistencia del tipo de cambio**: Se validó que los valores de `dolar.csv` estuvieran actualizados y fueran consistentes con las fechas de las transacciones.

---

## Errores Detectados y Correcciones Implementadas

### 1. **Errores en Precio_Kilo**
- **Problema**: Algunos registros tenían valores de `Precio_Kilo` iguales a cero o extremadamente bajos.
- **Corrección**: Se eliminaron los registros con `Precio_Kilo` menor a $1 y se imputaron los valores restantes utilizando la mediana por año.

### 2. **Errores en Fecha**
- **Problema**: Algunas fechas estaban en formatos inconsistentes o eran inválidas.
- **Corrección**: Se estandarizó el formato de la columna `Fecha` utilizando `pd.to_datetime`.

### 3. **Errores en Datos Externos**
- **Problema**: Algunos valores en `clima.csv` y `dolar.csv` estaban incompletos o eran inconsistentes.
- **Corrección**: Se aplicaron técnicas de interpolación lineal y relleno hacia adelante y atrás (`ffill` y `bfill`) para imputar valores faltantes.
