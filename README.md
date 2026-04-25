# ENTREGA FINAL GARCÍA BOSSIO 
# Clasificación de Sentimientos con PyTorch y NLP
Este proyecto realiza un análisis de sentimientos sobre reseñas de películas de IMDB utilizando técnicas avanzadas de procesamiento de lenguaje natural.

Aborda el desarrollo de un sistema de clasificación de texto diseñado para determinar la polaridad (positiva o negativa) de reseñas cinematográficas. Utilizando el dataset IMDB, se construyó un flujo de trabajo que integra técnicas avanzadas de procesamiento de lenguaje natural (NLP) y una arquitectura de red neuronal profunda implementada en PyTorch.

## 🚀 Características
* **Limpieza:** Regex y Lematización inteligente con **spaCy**.
* **Vectorización:** TF-IDF para resaltar palabras clave.
* **Modelo:** Red Neuronal Profunda con **PyTorch**, Batch Normalization y Dropout.
* **Optimización:** Implementación de **Early Stopping** para evitar el sobreajuste.

El análisis exploratorio reveló un conjunto de datos perfectamente balanceado, lo cual es una ventaja crítica para evitar sesgos en el entrenamiento. En el estado inicial de los datos, las palabras más frecuentes resultaron ser términos funcionales (stop-words) y restos de código HTML, lo que motivó una estrategia de limpieza rigurosa mediante expresiones regulares y lematización inteligente.
<img width="702" height="486" alt="image" src="https://github.com/user-attachments/assets/f49fb4c5-22ef-45db-aac2-b8833bb74842" />
<img width="1132" height="547" alt="image" src="https://github.com/user-attachments/assets/e387c5c6-155c-4a94-b954-8edd92b0423d" />

Para la transformación de los datos, se optó por la representación numérica TF-IDF. Esta técnica permite resaltar términos con alta carga emocional, como "excelente" o "decepcionante", dándoles mayor peso que a palabras comunes que no aportan valor predictivo. La arquitectura del clasificador se basó en una red neuronal con capas densas, incorporando mecanismos de Batch Normalización y un Dropout de 0.5. Estos componentes son fundamentales para garantizar la estabilidad del aprendizaje y evitar que el modelo se sobreajuste a los datos de entrenamiento.


## 📊 Resultados
El modelo alcanzó una precisión (accuracy) del 83%, demostrando una alta capacidad de generalización. Un hallazgo clave durante el entrenamiento fue la efectividad del Early Stopping: el sistema identificó que el punto óptimo de aprendizaje se alcanzó en la primera época, deteniendo el proceso antes de que la pérdida de validación comenzara a subir. La matriz de confusión confirma este rendimiento, mostrando que el modelo es robusto tanto para predecir sentimientos positivos como negativos, con una leve tendencia a ser más preciso en la detección de críticas positivas.

<img width="596" height="648" alt="image" src="https://github.com/user-attachments/assets/5c544190-40e4-457c-86a1-c29056a8912d" />

## 💡 Conclusiones

El éxito de este clasificador no dependió solo de la red neuronal, sino de la calidad y estructura de la base de datos de origen:

**Dataset Balanceado como Pilar de Entrenamiento:** Al trabajar con el corpus de IMDB, contamos con una distribución equitativa (50/50) de reseñas positivas y negativas. Esto evitó que el modelo desarrollara sesgos (por ejemplo, que tendiera a predecir todo como positivo por simple probabilidad), permitiendo que el 83% de accuracy sea una métrica real y honesta del desempeño.

**Ruido en Datos No Estructurados:** El análisis inicial de la base de datos reveló una gran cantidad de "basura" digital (etiquetas HTML, caracteres especiales y números). Esto demostró que, en bases de datos de texto real (como reviews de usuarios), la etapa de limpieza y normalización es la que realmente define el techo de precisión que puede alcanzar un algoritmo.

**Representatividad y Volumen:** Aunque el dataset original cuenta con 50.000 registros, el uso de una muestra de 5.000 fue suficiente para capturar patrones semánticos clave. Esto confirma que una base de datos bien curada permite prototipar modelos complejos de Deep Learning de manera eficiente sin necesidad de procesamientos masivos de entrada.

## 📈 Propuestas de Mejora
Para llevar el proyecto al siguiente nivel, las mejoras desde la perspectiva de la base de datos serían:

**Enriquecimiento del Corpus:** Utilizar el total de los 50.000 registros para exponer al modelo a una mayor diversidad de modismos, sarcasmo y vocabulario técnico del cine que no aparece en muestras reducidas.

**Balanceo de Longitud de Secuencias:** Implementar un filtrado en la base de datos para equilibrar reseñas muy cortas con reseñas muy largas, reduciendo así la varianza en los vectores TF-IDF.

**Data Augmentation:** Generar nuevas muestras sintéticas (por ejemplo, mediante traducción inversa) para fortalecer la base de datos en aquellos casos donde el modelo mostró dudas (los "falsos positivos" de la matriz de confusión).
