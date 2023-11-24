# Actividad: Análisis y Reporte sobre el desempeño del modelo.

En esta actividad, se analiza el desempeño del modelo creado en una de las actividades previas, se identifica sesgo, varianza y el ajuste del modelo.
Esta carpeta contiene los archivos solicitados para completar la actividad, está compuesta por:
* **Actividad_Desempeño.ipynb**: Notebook donde se encuentra el código realizado y la implementación del modelo, además de las explicaciones pertinentes.
* **iris.csv**: Archivo donde se encuentran los datos del set de datos utilizado en la actividad en formato csv.

## Set de Datos 

El set de datos utilizado se llama "iris.csv", y este incluye 150 muestras de flores, las cuales están clasificadas en 3 clases distintas. Cada muestra tiene las siguientes características:

* sepal_length
* sepal_width
* petal_length
* petal_width
* species

En donde, buscamos predecir la especie a la que pertenece cada muestra en base a las otras características que tenemos como "datos de entrada".

El set de datos se puede encontrar en: https://github.com/adrian-faz/EntregasIndividuales_AdrianFaz/tree/main/retro/M2_ML/Act2/iris.csv

## Problema

El problema presentado en este caso es de **clasificación**, pues se busca generar un modelo que sea capaz de clasificar en una de las 3 especies existentes en los datos, basandose en los otros datos, como lo son las longitudes y anchuras del sépalo y del pétalo. 

El modelo a utilizar fue el **Decision Tree Classifier**, el cual es un algoritmo de aprendizaje supervisado que descompone un problema complejo en subproblemas más simples, tomando decisiones basadas en las características de los datos. Este árbol se compone de nodos que representan condiciones, y ramas, que serían las posibles respuestas. Lo que se busca  es llegar a una "hoja" que contiene la clase a la que pertenece.

## Archivos a revisar para evaluar subcompetencias

1. **SMA0104A**
   * Indicadores:
      * Evalúa el modelo con un conjunto de prueba y un conjunto de validación
      * Detecta correctamente el grado de bias o sesgo: bajo medio alto
      * Detecta correctamente el grado de varianza: bajo medio alto
      * Explica el nivel de ajuste del modelo: underfitt fitt overfitt
      * Utiliza técnicas de regularización para mejorar el desempeño del modelo
       
   * Archivo donde se evalúa:
      * Actividad_Desempeño.ipynb


## Cambios implementados

A continuación se enlistan los puntos que no recibieron marcas en la rúbrica de retroalimentación y lo que se hizo para resolverlo:

1. "**El conjunto de validación se utiliza para escoger el modelo final (refinamiento de hiper-parámetros)**":
    * Antes de seleccionar el modelo definitivo a analizar, realicé 3 pruebas distintas con valores de hiperparámetros distintos. Varié parámetros como "criterion", "max_depth", "splitter", y otros y se obtuvo el valor de accuracy de cada uno en entrenamiento y validación. Utilicé el desempeño del árbol en el conjunto de validación para seleccionar el que mejor resultados tuvo. En la entrega pasada en realidad no varié parámetros más que hasta el final, en esta, desde el inicio realicé pruebas con diferentes parámetros y así seleccioné el modelo final. (Con la mejor combinación de las que tenía).
    
2. **Se detecta correctamente el nivel de ajuste del modelo: underfit, fit, overfit**
    * En la entrega pasada tenía una apreciación mal del modelo y mencionaba que para que el modelo fuera adecuado, debíamos de tener exactamente el mismo porcentaje de validación y de entrenamiento, pero no es así. Antes había catalogado mi modelo como overfit cuando en realidad era un buen fit, pues aunque no fueran exactamente los mismos valores de accuracy para entrenamiento y validación, eran muy cercanos y tenían porcentaje alto, por lo que en realidad era un buen fit. En esta entrega se explica correctamente que mi modelo tiene un buen ajuste por los diferentes factores involucrados, se elimina esa apreciación inicial que tenía de que ambos valores de accuracy debían ser forzosamente iguales y se interpreta de la manera adecuada en esta entrega.
      
3. **Se utilizan técnicas de regularización para mejorar el desempeño del modelo**
    * Se agregó una sección llamada "Técnica de regularización", en donde se utiliza la técnica de poda para limitar la complejidad del Árbol de Decisión. Utilizando el parámetro "ccp_alpha", se introduce una penalización que guía esta poda, donde un valor más alto nos da un árbol más simplificado. En la sección, se presentan diferentes valores de "ccp_alpha" y se analizan sus impactos, mostrando cómo esta técnica de regularización puede ser efectiva para obtener un mejor modelo.
