## Análisis de Fraude con Transacciones de Tarjetas de Crédito

Este repositorio contiene un análisis de detección de fraude en transacciones con tarjetas de crédito. Se utiliza un conjunto de datos que contiene transacciones realizadas con tarjetas de crédito en septiembre de 2013 por titulares de tarjetas europeos. El conjunto de datos contiene 284,807 transacciones, de las cuales 492 son fraudulentas.

### Información del Conjunto de Datos

* **Fuente:** Conjunto de datos de transacciones con tarjetas de crédito de titulares de tarjetas europeos en septiembre de 2013.
* **Tamaño:** 284,807 transacciones
* **Desequilibrio de clases:** La clase positiva (fraudes) representa el 0,172% de todas las transacciones.
* **Variables:** 
    * **V1 - V28:** Componentes principales obtenidos con PCA (Análisis de Componentes Principales).
    * **Tiempo:** Segundos transcurridos entre cada transacción y la primera transacción del conjunto de datos.
    * **Monto:** Monto de la transacción.
    * **Clase:** Variable de respuesta (0: no fraudulento, 1: fraudulento).

**Nota:** Debido a cuestiones de confidencialidad, no se proporcionan las características originales ni más información general sobre los datos.

### Metodología

Para abordar el desafío de detección de fraude, se implementaron y compararon varios modelos de aprendizaje automático:

* **Modelos tradicionales:**
    * `svc_rbf`: Máquina de Vectores de Soporte con kernel RBF.
    * `lr`: Regresión Logística.
    * `dt`: Árbol de Decisión.
    * `rfc`: Bosque Aleatorio.
    * `abc`: AdaBoost.
    * `gbc`: Gradient Boosting.
    * `xgbc`: XGBoost.
    * `gssnb`: Naive Bayes Gaussiano.
    * `knc`: K-Vecinos Más Cercanos.
    * `mlpc`: Perceptrón Multicapa.
    * `sgdc`: Clasificador de Descenso de Gradiente Estocástico.

* **Red Neuronal:**
    * `model_nn`: Red neuronal secuencial con 3 capas densas y función de activación ReLU. La última capa tiene una función de activación Sigmoid para la clasificación binaria.

### Resultados

Se lograron resultados excelentes tanto para el `MLPClassifier` como para la red neuronal secuencial. Las métricas de precisión fueron aproximadamente 0.999 para ambos modelos, con solo tres falsos positivos en la matriz de confusión. 

El modelo fue entrenado utilizando validación cruzada con 10 modelos distintos y se seleccionó el mejor modelo al calcular las medias de cada métrica con `n_splits=5`. Se optó por la métrica `roc_auc` para evaluar el rendimiento, ya que representa mejor la capacidad del modelo para distinguir entre las dos clases.

Se realizó un ajuste de hiperparámetros (tuning) para la red neuronal con el fin de buscar los mejores parámetros, reduciendo así la pérdida y maximizando la precisión.

**Importantes Consideraciones:**

* Los datos fueron procesados mediante PCA para reducir la dimensionalidad. 
* Los datos no representan las transacciones reales debido a la seguridad e integridad de los datos.
* Los datos no reflejan los datos obtenidos en el momento debido al uso de PCA.

* Exploración de técnicas de muestreo de datos para abordar el desequilibrio de clases.
* Aplicación de técnicas de aprendizaje profundo más avanzadas para mejorar la precisión.
* Validación del modelo con datos reales de transacciones con tarjetas de crédito.

### Conclusión

El modelo desarrollado se comporta de manera óptima, mostrando un excelente rendimiento en la detección de fraude. El análisis de este conjunto de datos proporciona una comprensión valiosa sobre los patrones de fraude y cómo identificarlos utilizando modelos de aprendizaje automático.

### Contacto

Para cualquier consulta o sugerencia, por favor contacta con: [angelalvaradonasa@gmail.com]

@ Angel Alaguera. Ing Informático | Esp. Machine Learning
