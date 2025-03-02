# 📊 Descripción de los Datos

## Descripción
Este documento proporciona información detallada sobre los datos utilizados en el proyecto de predicción de precios de ganado, incluyendo su estructura, fuentes y uso dentro del pipeline de datos.

---

## 1. Estructura de los Datos
El dataset principal contiene registros históricos de transacciones ganaderas, junto con variables adicionales que influyen en las fluctuaciones del mercado. A continuación, se describe la estructura de los datos:

| Variable            | Descripción                                              | Tipo        |
|---------------------|----------------------------------------------------------|-------------|
| **Fecha**           | Fecha de la transacción                                  | Date        |
| **Categoria**       | Categoría del ganado (Bovinos, Caprinos, Ovinos, etc.)  | Categórica  |
| **Raza**            | Raza del ganado                                          | Categórica  |
| **Marca**           | Marca del ganado                                         | Categórica  |
| **Peso**            | Peso del ganado en kilogramos                            | Numérica    |
| **Precio_Kilo**     | Precio del ganado por kilogramo en USD                   | Numérica    |
| **Tipo_Remate**     | Tipo de remate (Feria, Privado, etc.)                    | Categórica  |
| **Corredor_Compra** | Corredor que realizó la compra                           | Categórica  |
| **Dolar**           | Tipo de cambio del dólar en la fecha de la transacción   | Numérica    |
| **Temperatura_Minima** | Temperatura mínima registrada en la fecha de la venta  | Numérica    |
| **Precipitacion**   | Nivel de precipitación en la región (mm)                 | Numérica    |

---

## 2. Fuentes de Datos
Los datos provienen de diversas fuentes para garantizar precisión y confiabilidad:

- **Bases de datos de mercados ganaderos**: Registros históricos de transacciones ganaderas, incluyendo precios, pesos y categorías.
- **APIs climáticas**: Información meteorológica histórica, como temperatura y precipitación.
- **Datos económicos**: Tipo de cambio del dólar, obtenido de fuentes financieras confiables.
- **Datos externos**: Información adicional sobre recintos y corredores, proporcionada por entidades ganaderas.

---

## 3. Uso de los Datos en el Proyecto
Los datos se utilizan en las siguientes etapas del proyecto:

- **Entrenamiento del Modelo**: Se utilizan variables relevantes como **Peso**, **Raza**, **Dolar**, **Temperatura_Minima** y **Precipitacion** para predecir el **Precio_Kilo**.
- **Validación y Evaluación**: Se separa un conjunto de datos para medir el desempeño del modelo, utilizando métricas como RMSE y R².
- **Despliegue y Predicción en Tiempo Real**: Los datos recientes se ingresan al modelo para obtener predicciones actualizadas del precio del ganado.

---

## 4. Consideraciones de Calidad
Para garantizar la calidad de los datos, se aplicaron las siguientes técnicas:

- **Detección y eliminación de valores atípicos**: Se identificaron y trataron outliers en variables como **Precio_Kilo** y **Peso**.
- **Imputación de datos faltantes**: Se rellenaron valores nulos en variables como **Raza**, **Marca** y **Temperatura_Minima** utilizando técnicas de imputación (media, mediana, interpolación).
- **Validación cruzada**: Los datos se validaron con fuentes externas para evitar inconsistencias, especialmente en variables como **Dolar** y **Precipitacion**.
- **Escalado de variables**: Las variables numéricas se normalizaron para mejorar el rendimiento del modelo.

---