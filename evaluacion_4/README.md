# 📊 Evento Evaluativo 4 – Machine Learning
**Asignatura:** Análisis de Datos  
**Carrera:** Ingeniería en Ciencia de Datos  
**Grupo:** 190304018-1 | **Periodo:** 2025-2  
**Docente:** Daniel Alexis Nieto Mora  
**Equipo:** 6

---

## 📁 Estructura del Repositorio

```
evaluacion_4/
│
├── Ejercicio3_Sentimientos_Amazon.ipynb   # Análisis de sentimientos en reseñas
├── Ejercicio4_Clustering_Clientes.ipynb   # Agrupamiento de clientes (Mall)
└── README.md
```

---

## 🧪 Ejercicio 3: Análisis de Sentimientos en Reseñas de Amazon

### Descripción
Modelo de aprendizaje supervisado para clasificar reseñas de productos de Amazon como **positivas** o **negativas** mediante técnicas de Procesamiento de Lenguaje Natural (NLP).

### Dataset
[Amazon Reviews Dataset – Kaggle](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews)

### Pipeline
1. **EDA:** distribución de clases, longitud de textos, WordCloud por sentimiento
2. **Preprocesamiento:** limpieza de texto, tokenización, eliminación de stopwords, stemming, vectorización TF-IDF (5000 features, unigramas + bigramas)
3. **Modelos aplicados:**

| Modelo | Justificación |
|--------|--------------|
| Naive Bayes (MultinomialNB) | Clásico en NLP; rápido, eficiente con TF-IDF |
| Regresión Logística | Modelo lineal interpretable; ideal para clasificación binaria con texto |
| SVM Lineal (LinearSVC) | Robusto en alta dimensión; excelente con representaciones dispersas |

4. **Métricas:** Accuracy, F1-Score, Precision, Recall, Matriz de Confusión
5. **Reducción de dimensionalidad:** SVD + t-SNE para visualizar separabilidad de clases
6. **Interpretabilidad:** palabras más influyentes por clase (coeficientes de Regresión Logística)

### Resultados Destacados
- SVM Lineal y Regresión Logística superan a Naive Bayes en F1-Score
- t-SNE muestra agrupaciones identificables entre clases positivas y negativas
- Las palabras con mayor peso positivo y negativo son coherentes con el lenguaje real de las reseñas

---

## 🛍️ Ejercicio 4: Agrupamiento de Clientes – Mall Customers

### Descripción
Segmentación de clientes de un centro comercial usando **aprendizaje no supervisado** para identificar perfiles de comportamiento de compra y proponer estrategias de marketing diferenciadas.

### Dataset
[Mall Customers Dataset – Kaggle](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python)

### Variables utilizadas
- `Age` – Edad del cliente
- `Annual Income (k$)` – Ingreso anual
- `Spending Score (1-100)` – Puntuación de gasto asignada por el mall

### Pipeline
1. **EDA:** distribuciones, scatter plots, mapa de correlación, análisis por género
2. **Preprocesamiento:** estandarización con StandardScaler
3. **Selección de k:** Método del Codo + Silhouette Score
4. **Modelos aplicados:**

| Modelo | Justificación |
|--------|--------------|
| K-Means | Eficiente y ampliamente usado en segmentación; requiere k definido |
| DBSCAN | No requiere k; detecta outliers y clusters de forma arbitraria |
| Agglomerative Clustering (Ward) | Jerárquico; permite explorar estructura de grupos mediante dendrograma |

5. **Evaluación:** Silhouette Score, Davies-Bouldin Score
6. **Visualización:** PCA 2D comparando los 3 métodos, dendrograma, perfiles por cluster

### Segmentos Identificados (K-Means, k=5)

| Cluster | Perfil | Estrategia Sugerida |
|---------|--------|---------------------|
| 0 | Alto ingreso, bajo gasto | Programas de fidelización premium |
| 1 | Jóvenes, bajo ingreso, alto gasto | Promociones frecuentes y descuentos |
| 2 | Perfil estándar | Campañas masivas |
| 3 | Adultos, gasto conservador | Productos de valor y durabilidad |
| 4 | Alto ingreso + alto gasto (VIP) | Experiencias exclusivas y membresías |

---

## ⚙️ Requisitos e Instalación

### Ejecutar en Google Colab (recomendado)
1. Abrir el notebook en [Google Colab](https://colab.research.google.com/)
2. Subir el archivo `kaggle.json` si se desea usar los datasets reales
3. Ejecutar todas las celdas en orden (`Runtime > Run all`)

### Dependencias principales
```
pandas · numpy · scikit-learn · matplotlib · seaborn
nltk · scipy · wordcloud
```
Todas se instalan automáticamente en la primera celda de cada notebook.

---

## 📏 Métricas Utilizadas

| Tarea | Métricas |
|-------|----------|
| Clasificación (Ej. 3) | Accuracy, F1-Score, Precision, Recall, Matriz de Confusión |
| Clustering (Ej. 4) | Silhouette Score, Davies-Bouldin Score |

---

## 🤝 Integrantes del Equipo 6

| Nombre | Rol |
|--------|-----|
DAVID RAMIREZ VELEZ
JESSICA JOHANNA OBANDO GARCIA
LUKAS JIMENEZ BUENO
MATEO GONZALEZ ESCUDERO

---

## 📌 Notas
- Cada notebook incluye una **Opción B** con dataset simulado en caso de no contar con acceso a Kaggle.
- Las conclusiones, implicaciones éticas e interpretaciones de negocio se documentan al final de cada notebook.
- El video de sustentación (máx. 12 min) cubre los puntos clave del proceso y las decisiones técnicas tomadas.
