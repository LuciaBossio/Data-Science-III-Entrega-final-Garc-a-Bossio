
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



## 📊 Resultados
El modelo alcanzó un **83% de precisión**. A continuación, los hallazgos principales:
* El modelo es robusto tanto para críticas positivas como negativas.
* El Early Stopping evitó el overfitting rescatando el mejor modelo en la época 1.
