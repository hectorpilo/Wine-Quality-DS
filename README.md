# 🍷 Predicción de Calidad del Vino – Proyecto de Machine Learning

Este proyecto fue desarrollado usando el dataset de **Wine Quality** disponible en [Kaggle](https://www.kaggle.com/datasets/yasserh/wine-quality-dataset). Mi objetivo fue predecir la calidad del vino a partir de sus características fisicoquímicas, aplicando técnicas de análisis exploratorio de datos (EDA), limpieza, visualización y modelos de clasificación.

## 📌 ¿Qué hice?

1. **Importación y revisión inicial del dataset**  
   Comencé importando el archivo CSV y explorando su estructura general, tipos de datos y presencia de valores nulos o atípicos.

2. **Análisis exploratorio de datos (EDA)**  
   Realicé un análisis gráfico y estadístico para entender mejor las relaciones entre variables como:  
   - `citric acid`  
   - `volatile acidity`  
   - `residual sugar`  
   - `alcohol`  
   - `quality`  

3. **Tratamiento de valores cero**  
   Identifiqué 99 valores "0" en la columna `citric acid`. En vez de eliminarlos automáticamente, analicé su coherencia con otras variables (por ejemplo, rangos normales de `fixed acidity`, `volatile acidity`, etc.) para evaluar si eran plausibles.

4. **Detección de outliers**  
   Utilicé boxplots y otras herramientas visuales para encontrar valores atípicos, los cuales luego revisé para decidir si debían ser eliminados o mantenidos.

5. **Modelado predictivo**  
   Entrené tres modelos:
   - `KNeighborsClassifier` (KNN), ajustando el hiperparámetro `K` con validación cruzada.
   - `RandomForestClassifier`, aplicando búsqueda de hiperparámetros (`GridSearchCV`) para optimizar su rendimiento.
   - `LogisticRegression`, como modelo base de referencia.

   Para la regresión logística, ajusté el hiperparámetro `C` (que controla la regularización) mediante búsqueda en cuadrícula usando `GridSearchCV` y validación cruzada. El mejor rendimiento se obtuvo con:
   - `C = 1`
   - `penalty = 'l2'`
   - `solver = 'liblinear'`

   Este modelo sirvió como base para comparar los resultados con KNN y Random Forest.

6. **Evaluación de modelos**  
   Evalué el rendimiento usando métricas como `accuracy`, `precision`, `recall`, `f1-score` y matriz de confusión. Comparé los tres modelos y documenté sus fortalezas.

7. **Exportación**  
   Guardé el notebook en GitHub y creé una versión de liberación del proyecto con una descripción clara.

## 📁 Archivo principal

- `CORE_Prediccion_Calidad_VINO.ipynb`


