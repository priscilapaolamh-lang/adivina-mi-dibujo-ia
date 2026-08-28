**Priscila Montenegro** 
Instituto Tecnológico Universitario Rumiñahui 
Inteligencia Artificial  
 Proyecto Evaluación Parcial 2


#  Adivina mi Dibujo — Clasificador en Tiempo Real

Sistema de Inteligencia Artificial que predice, mientras el usuario dibuja sobre un lienzo digital, a cuál de 5 categorías pertenece el dibujo, mostrando las 3 predicciones más probables con su nivel de confianza.

---

## 📋 Descripción del Proyecto

El sistema utiliza una **Red Neuronal Convolucional (CNN)** entrenada desde cero con el dataset **Quick, Draw!** de Google, capaz de reconocer 5 categorías de dibujos:

-  Gato (cat)
-  Manzana (apple)
-  Árbol (tree)
-  Estrella (star)
-  Casa (house)

La predicción se actualiza **en tiempo real** mientras el usuario dibuja, sin necesidad de presionar ningún botón de envío.

---

##  Dataset

| Propiedad | Detalle |
|-----------|---------|
| **Fuente** | Quick, Draw! Dataset (Google, dominio público) |
| **Categorías** | cat, apple, tree, star, house |
| **Imágenes por categoría** | 4,000 (20,000 en total) |
| **Formato** | Escala de grises, 28×28 píxeles |

---

## Arquitectura del Modelo

CNN construida con TensorFlow/Keras:

- 3 capas Conv2D (32, 64 y 64 filtros) con MaxPooling2D
- Capa Flatten + Dense(128) con activación ReLU
- Dropout(0.3) para reducir sobreajuste
- Capa de salida Dense(5) con activación softmax
- Optimizador: Adam
- Función de pérdida: sparse_categorical_crossentropy

---

## Resultados

- **Accuracy en prueba:** 97.07% (meta mínima: 75%)
- **Matriz de confusión:** disponible en el repositorio como `matriz_confusion.png`

---

##  Requisitos Previos

- Cuenta de Google (para usar Colab)
- Navegador web (Chrome, Firefox, Edge, etc.)
- Conexión a Internet

---

## Cómo Ejecutar el Proyecto (PASO A PASO)

### Paso 1: Abrir el Notebook en Google Colab

Haz clic en el siguiente enlace para abrir el notebook directamente en Google Colab:

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/tu-usuario/adivina-mi-dibujo/blob/main/adivina_mi_dibujo.ipynb)

> **Nota:** Reemplaza `tu-usuario` con tu nombre de usuario de GitHub.

---

### Paso 2: Configurar el Entorno de Ejecución

1. En la parte superior del notebook, ve al menú **"Entorno de ejecución"**.
2. Selecciona **"Cambiar tipo de entorno de ejecución"**.
3. En la ventana emergente, elige **"GPU"** como acelerador de hardware.
4. Haz clic en **"Guardar"**.

---

### Paso 3: Ejecutar las Celdas del Notebook

Ejecuta las celdas en orden, de arriba hacia abajo. Puedes hacerlo de dos formas:

- **Opción A:** Presiona `Ctrl + F9` para ejecutar todas las celdas.
- **Opción B:** Haz clic en el botón ▶️ de la izquierda de cada celda, una por una.

#### ¿Qué hace cada celda?

| Celda | Función |
|-------|---------|
| **Celda 1** | Instala Gradio |
| **Celda 2** | Importa las librerías necesarias |
| **Celda 3** | Descarga el dataset Quick, Draw! (5 categorías, 4,000 imágenes cada una) |
| **Celda 4** | Carga y preprocesa las imágenes (normalización y reshape) |
| **Celda 5** | Muestra ejemplos de imágenes del dataset |
| **Celda 6** | Construye y compila la CNN |
| **Celda 7** | Entrena el modelo durante 12 épocas |
| **Celda 8** | Muestra las curvas de accuracy y pérdida |
| **Celda 9** | Evalúa el modelo y genera la matriz de confusión |
| **Celda 10** | Guarda el modelo entrenado como `modelo_adivina_mi_dibujo.h5` |
| **Celda 11** | Lanza la interfaz interactiva con Gradio |

---

### Paso 4: Interactuar con el Sistema

1. Una vez ejecutada la **Celda 11**, verás un enlace público como este:
Running on public URL: (https://bb252104976e8a99fd.gradio.live)


2. **Haz clic en ese enlace** para abrir la interfaz.

3. **Dibuja** con el mouse sobre el lienzo blanco.

4. **Observa** cómo la predicción se actualiza automáticamente mientras dibujas.

5. **Revisa** el Top 3 de predicciones con sus porcentajes de confianza.

---

### Paso 5: Detener la Ejecución

- Para detener la interfaz de Gradio, presiona `Ctrl + C` en la terminal de Colab.
- Para cerrar el notebook, simplemente cierra la pestaña del navegador.


---

##  Tecnologías Utilizadas

- **Python 3.10+**
- **TensorFlow / Keras** — Construcción y entrenamiento del modelo
- **Gradio** — Interfaz web interactiva
- **NumPy** — Manejo de arrays y datos numéricos
- **Matplotlib** — Visualización de resultados
- **scikit-learn** — Métricas de evaluación (matriz de confusión)
- **Google Colab** — Entorno de desarrollo y entrenamiento

---



