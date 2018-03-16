# dIabetes_prediction_Pima_indians
Predicción de diabetes en indios Pima

### Información del dataset

* Toda la información que necesitas saber del dataset está en este link: 
*<https://archive.ics.uci.edu/ml/datasets/pima+indians+diabetes>*

* Para saber quiénes son los indios Pima: *<https://es.wikipedia.org/wiki/Pueblo_pima>*

### Descripción del problema de negocio

* El departamento de salud de USA le ha asignado la misión de entregar una recomendación de política pública de salud con respecto a la presencia de diabetes en la población de Indios Pima. Para esto, el departamento le ha facilitado el siguiente dataset que contiene 762 observaciones correspondientes a una pre-selección realizada por los investigadores (*<https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2245318/pdf/procascamc00018-0276.pdf>*)


* El objetivo de este trabajo, es hacer una revisión de este estudio y determinar si con las nuevas técnicas y herramientas disponibles en la actualidad es posible entregar mejores recomendaciones o si se deben mantener las recomendaciones entregadas previamente


### Resultados

* Luego de testear varios métodos, se decide aplicar la tecnica de balance de clases Smote y el algoritmo de Regresión logística con optimización de parámetros utilizando el algoritmo GridSearch para identificar a los mujeres Pima que tendrán diabetes. Luego de la primera iteración, se obtienen los siguientes resultados pre-liminares al comparar con nuestro conjunto de test:

     * Accuracy: 79%
     * Roc auc score: 0.88
     * Sensitivity : 66%
     * Specificity : 89%
     * Recall de la clase positiva: 81%
     * Recall de la clase negativa: 78%


* Es decir, esperamos identificar correctamente  al 81% de la población que va a tener diabetes y al 78% de los que no, lo cual nos permitirá aplicar políticas preventivas sobre quienes tienen mayor probabilidad de padecer la enfermedad.


* Hemos identificado que el nivel de glucosa en la sangre (medido con un test), la presión sistólica, la edad y el número de embarazos aparecen como las variables más relevantes a controlar en los pacientes para que podamos generar la predicción


* El modelo es muy bueno identificando a los pacientes que no son diabéticos, pero tiene una performance menor para identificar a los que si lo son. Aún así, es el modelo con mejor balance en la precisión entre ambas clases, menor variabilidad en sus resultados y menor proproción de falsos negativos, que es el error que queremos minimizar.

### Próximos pasos

* Se pueden realizar ajustes moviendo la probabilidad de umbral, de tal forma que minimizemos los falsos negativos.

* En la optimización de parámetros, se puede cambiar la métrica que sigue el algoritmo Gridsearch de Accuracy a Recall de la clase negativa

* Aplicar optimización de parámetros al algoritmo KNN, el cual lógica distinta a los algoritmos escogidos previamente y podría ser que el identificar los subgrupos con caracteristicas similares previo a la clasificación capture patrones que el resto no

* Generar un modelo que votacion de las predicciones realizadas con Random forest, Regresión Logística y KNN.

### Lenguajes utilizado

* Python 3.6
* Jupyter notebook

### Librerias necesarias

   - [Pandas](https://pandas.pydata.org/) 
   - [Scikit Learn](http://scikit-learn.org/) 
   - [Numpy](http://www.numpy.org/) 
   - [imbalanced-learn ](https://github.com/scikit-learn-contrib/imbalanced-learn)
   - [matplotlib ](https://matplotlib.org)
   - [seaborn](https://seaborn.pydata.org)
