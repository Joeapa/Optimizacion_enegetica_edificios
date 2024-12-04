# Optimización del diseño energético en edificios

## Descripción del proyecto
Este proyecto tiene como objetivo optimizar el diseño energético en edificios mediante el uso de modelos de Machine Learning. Utilizando datos relacionados con las características físicas de los edificios, se predicen las cargas de refrigeración (o calefacción), permitiendo tomar decisiones más informadas en el diseño arquitectónico y energético.

---

## Estructura del proyecto

### 1. Carga de datos
Se ha trabajado con un dataset que contiene características de edificios como:
- **Compactación relativa**
- **Área de superficie**
- **Área de paredes**
- **Área de techo**
- **Altura total**
- **Orientación**
- **Área de acristalamiento**
- **Distribución del área de acristalamiento**
- Cargas de calefacción y refrigeración como variables objetivo (en el modelo se ha utilizado la carga de refrigeración).

El dataset ha sido cargado y explorado con herramientas como **Pandas** y **Seaborn**.

---

### 2. Análisis exploratorio de datos (EDA)
Se ha realizado un análisis exhaustivo de los datos, destacando:
- **Distribuciones de las variables objetivo**: 
  - Se ha identificado una **bimodalidad** en las distribuciones de `Heating Load` y `Cooling Load`.
- **Mapa de calor de correlaciones**:
  - Variables como `relative_compactness`, `surface_area`, `roof_area` y `overall_height` han mostrado alta correlación con las variables objetivo.
- **Detección de outliers**:
  - Se han analizado mediante boxplots para descartar valores atípicos significativos en las variables predictoras.

---

### 3. Preprocesamiento de los datos
El dataset ha sido dividido en **conjuntos de entrenamiento y prueba**.

---

### 4. Modelos de Machine Learning
Se han entranado y evaluado dos modelos:

#### **Linear Regression**
- **R²**: 0.89
- **MAE**: 2.20
- **RMSE**: 3.15

#### **XGBoost Regressor**
- **R²**: 0.99
- **MAE**: 0.46
- **RMSE**: 0.83

**Conclusión**: El modelo **XGBoost** ha superado significativamente al modelo de regresión lineal en términos de precisión y error, mostrando un ajuste casi perfecto para los datos.

---

### 5. Uso práctico del modelo
Se ha demostrado un caso de uso práctico del modelo entrenado:
- **Predicción de cargas de refrigeración para un nuevo diseño**:
  - Se han introducido características de un diseño hipotético y se ha predicho la carga de refrigeración utilizando el modelo XGBoost.
