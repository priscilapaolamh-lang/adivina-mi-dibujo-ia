
## Adivina mi Dibujo — Clasificador de Dibujos en Tiempo Real

Proyecto Inteligencia Artificial. Sistema que predice, mientras el usuario dibuja sobre un lienzo digital, a cuál de 5 categorías pertenece el dibujo, mostrando las 3 predicciones más probables junto con su nivel de confianza.

## Descripción del proyecto

El sistema utiliza una Red Neuronal Convolucional (CNN) entrenada desde cero con el dataset **Quick, Draw!** de Google, capaz de reconocer 5 categorías de dibujos: **gato, manzana, árbol, estrella y casa**. La predicción se actualiza en tiempo real conforme el usuario dibuja, sin necesidad de presionar ningún botón de envío.

## Dataset

- **Fuente:** [Quick, Draw! Dataset](https://quickdraw.withgoogle.com/data) (Google, dominio público)
- **Categorías:** cat, apple, tree, star, house
- **Cantidad:** 4,000 imágenes por categoría (20,000 en total)
- **Formato:** imágenes en escala de grises de 28x28 píxeles

## Arquitectura del modelo

CNN construida con TensorFlow/Keras:

- 3 capas `Conv2D` (32, 64 y 64 filtros) con `MaxPooling2D` entre las dos primeras
- Capa `Flatten` + `Dense(128)` con activación ReLU
- `Dropout(0.3)` para reducir sobreajuste
- Capa de salida `Dense(5)` con activación `softmax`
- Optimizador: Adam · Función de pérdida: `sparse_categorical_crossentropy`

## Resultados

- **Accuracy en el conjunto de prueba:** ver `matriz_confusion.png` (meta mínima: 75%)
- Matriz de confusión disponible en el repositorio como `matriz_confusion.png`

## Cómo ejecutar el proyecto

1. Sube el notebook `adivina_mi_dibujo.ipynb` a [Google Colab](https://colab.research.google.com).
2. En el menú superior: `Entorno de ejecución > Cambiar tipo de entorno de ejecución > GPU`.
3. Ejecuta todas las celdas en orden, de arriba hacia abajo.
4. La última celda lanza la interfaz interactiva (Gradio) con un enlace público donde se puede dibujar y ver las predicciones en tiempo real.

## Estructura del repositorio

```
├── adivina_mi_dibujo.ipynb       # Notebook completo (dataset, entrenamiento, interfaz)
├── modelo_adivina_mi_dibujo.h5   # Modelo entrenado exportado
├── matriz_confusion.png          # Matriz de confusión sobre el set de prueba
├── informe_tecnico.docx          # Informe técnico del proyecto
└── README.md
```

## Tecnologías utilizadas

- Python, TensorFlow / Keras
- Gradio (interfaz interactiva)
- Google Colab (entorno de desarrollo y entrenamiento)

## Instituto Tecnológico Universitario Rumiñahui

Priscila Montenegro — Proyecto Evaluación Parcial 2,  Inteligencia Artificial 
