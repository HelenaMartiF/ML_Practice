# **Predicción de Precios de Airbnbs - Proyecto de Machine Learning**

## **Objetivo**

El objetivo de este proyecto es desarrollar un modelo de machine learning capaz de predecir el precio de los anuncios de Airbnb basándose en un conjunto de datos proporcionado. La variable objetivo es `Price`, y se trata de un problema de **regresión**.

## **Pipeline del Proyecto**

### **1. Carga de Datos y Preprocesamiento Inicial**

El primer paso fue cargar el dataset y realizar un preprocesamiento inicial. Se verificaron las columnas del conjunto de datos y se eliminaron aquellas que contenían información irrelevante como URLs, identificadores de host y IDs que no aportaban valor predictivo.

### **2. Manejo de Valores Nulos**

- **Eliminación de columnas con más del 50% de valores nulos**: Se eliminaron aquellas columnas que contenían un alto porcentaje de valores faltantes, ya que no aportaban suficiente información para la predicción.
  
- **Imputación de datos faltantes**: Para las columnas restantes con valores nulos, se utilizó la **media** para imputar las variables **numéricas** y la **moda** para las **categóricas**.

### **3. Imputación de Datos**

Se realizaron las imputaciones necesarias utilizando estrategias de **media** para las variables numéricas y de **moda** para las categóricas, con el fin de mantener la integridad del conjunto de datos.

### **4. Separación de Datos**

El siguiente paso fue dividir el conjunto de datos en **conjunto de entrenamiento** y **conjunto de prueba** para evitar el sobreajuste (overfitting) y poder evaluar la precisión de los modelos.

### **5. Codificación de Variables Categóricas**

Las variables categóricas fueron convertidas a formato numérico mediante técnicas de **Codificación One-Hot** o **Label Encoding**, dependiendo de la naturaleza de las variables. Este paso es esencial para que los algoritmos de machine learning puedan procesarlas correctamente.

### **6. Análisis de Varianza (ANOVA)**

Se realizó un análisis de varianza utilizando el **ANOVA** para identificar las variables más relevantes que afectan la predicción del precio. Este análisis permitió seleccionar las características que aportaban la mayor varianza explicativa en relación con el precio.

### **7. Importancia de las Características con Random Forest**

Se utilizó un modelo de **Random Forest** para calcular la **importancia de las características**. Este modelo proporcionó una evaluación de qué variables eran más influyentes a la hora de predecir el precio de los anuncios de Airbnb.

### **8. Correlación entre Variables**

Se analizó la correlación entre las variables numéricas utilizando un **heatmap** para visualizar las relaciones entre las características y la variable objetivo `Price`. Este análisis ayudó a identificar posibles redundancias o variables altamente correlacionadas.

### **9. Visualización de los Datos**

Se generaron gráficos para explorar la distribución de variables clave, como el `Price`, y para detectar posibles **outliers** que pudieran influir negativamente en los resultados del modelo.

### **10. Regularización de Outliers**

Los **outliers** fueron identificados y tratados manualmente utilizando un enfoque basado en el análisis visual y en la regla del **1.5 * IQR**. Se aplicaron los siguientes filtros para eliminar los valores atípicos en varias variables.
Después de aplicar estos filtros, se realizó una visualización mediante gráficos de dispersión (scatter plots) para cada variable, con el objetivo de identificar cualquier posible patrón y correlación con la variable objetivo `Price`. Los gráficos fueron generados en un **subplot** de 9 filas y 2 columnas, lo que permitió inspeccionar rápidamente las relaciones entre las características y el precio.

### **11. Modelado**

Se probaron distintos modelos para predecir los precios de los Airbnbs. Los modelos evaluados fueron:

- **Lasso Regression**  
- **Regresión Lineal**  
- **Random Forest**  
- **Gradient Boosting**  

A continuación, se muestran los resultados de cada modelo en términos de **Mean Squared Error (MSE)**:

1. **Lasso Regression**: MSE de 1670. Este modelo no fue capaz de predecir bien los precios, ya que el valor es más alto en comparación con otros modelos.
  
2. **Regresión Lineal**: MSE de 1269. Aunque ligeramente mejor que Lasso, sigue siendo peor que los modelos de árboles.

3. **Random Forest**: MSE de 1123. Este modelo superó a Lasso y Regresión Lineal, demostrando su capacidad para capturar relaciones más complejas entre las variables.

4. **Gradient Boosting**: MSE de 1096. Este fue el modelo que tuvo el mejor rendimiento, alcanzando el MSE más bajo y demostrando ser el más preciso en la predicción de los precios de Airbnb.

### **12. Análisis Final**

El modelo de **Gradient Boosting** resultó ser el más adecuado para predecir los precios de los Airbnbs en este conjunto de datos. A pesar de que otros modelos, como **Random Forest**, también mostraron buenos resultados, **Gradient Boosting** demostró ser el más preciso, lo que lo convierte en la mejor opción para este problema de predicción.

---

### **Tecnologías Utilizadas**

- **Python**  
- **Pandas**  
- **Scikit-Learn**  
- **Matplotlib** (para visualización de resultados)  
- **Seaborn** (para visualización de datos)
- **Scikit-Learn**
- **SciPy**
- **NumPy**

---
