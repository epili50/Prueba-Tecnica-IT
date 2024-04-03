# Prueba-Tecnica-IT
Prueba técnica IT para actualizar conocimiento sobre Data Science

# Algoritmos de Aprendizaje Supervisado: Clasificación <br>Predicción sobre el turno en el que se producen acidentes de transito en Barcelona

## 1. Introducción

El presente repositorio se centra en el análisis de datos de accidentes gestionados por la Guàrdia Urbana en la ciudad de Barcelona, recopilados entre los años 2021 y 2023. El objetivo principal es predecir el momento del día en el que se producirán los accidentes, utilizando técnicas de aprendizaje supervisado de clasificación. 
Si bien la base de datos pública consultada provee registros desde 2016, es recién a partir de 2021 que el campo que se utilizará como target (turno en el que se produce el accidente) tiene los datos registrados con la consistencia necesaria. 
Se ha seleccionado el siguiente conjunto de variables para este propósito: distrito, mes y día de la semana.

## 2. Depuración de datos

Para preparar los datos para el análisis, se llevaron a cabo varias técnicas de preprocesamiento. Primero, se realizó un análisis gráfico para entender su distribución y correlación, y luego los datos de los campos seleccionadas en variables numéricas para poder llevar adelante el modelo mencionado. 
Más adelante, se midió si la muestra en cada campo tenía una distribución gaussiana y, al ver que en todos los casos el resultado fue negativo, se aplicó una normalización de los datos. Naturalmente este preprocesado se realizó con los datos que se utilizaron luego como variables para predecir el objetivo, pero no con el Target, que no debe ser alterado.
Además, todas las variables se transformaron en tipo categórico, dado que no presentaban una relación ordinal.

## 3. Resultados

La muestra se dividió en conjuntos de entrenamiento y prueba, y se entrenaron cuatro modelos de clasificación: KNN, LR, SVC y RF. Aunque LR y SVC mostraron una mayor precisión (0.51), al examinar la matriz de confusión se observó que los modelos RF y KNN se acercaban más a una predicción deseada. Se ajustaron los parámetros de estos modelos, lo que resultó en una leve mejora en KNN al establecer el número de vecinos en 13. A pesar de intentar balancear la muestra del conjunto de prueba, los resultados no se vieron modificados.

Se utilizaron métricas como la precisión (acc), F1-score (F1), recall y validación cruzada (CV) para evaluar los modelos. El mejor rendimiento se logró con el modelo KNN después de ajustar sus parámetros, obteniendo una precisión del 0.47, un F1-score de 0.33, un recall de 0.35 y una validación cruzada de 0.34.

## 4. Conclusiones

Los resultados obtenidos son útiles tanto para la comunidad como para los agentes cívicos en tareas de prevención de accidentes. La capacidad de prever los momentos del día en los que son más probables los accidentes puede contribuir significativamente a la planificación de medidas preventivas. Aunque se logró una precisión modesta, los modelos desarrollados proporcionan una base sólida para futuros análisis y mejoras en la predicción de accidentes en la ciudad de Barcelona.

**Nota:** Este README proporciona una visión general del trabajo realizado y sus resultados clave. Para obtener más detalles, consulte la documentación y el código fuente en el repositorio correspondiente.
