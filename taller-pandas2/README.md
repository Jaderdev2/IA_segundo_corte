# 📊 Taller Práctico de Pandas y Operaciones Matemáticas

<div align="center">
  <img width="650" alt="logo_unipacifico" src="https://github.com/user-attachments/assets/b67b5a9a-0ac4-4bcf-b569-bbc486818d81" />
  <br><br>

  ![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
  ![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-green)
  ![NumPy](https://img.shields.io/badge/NumPy-1.24%2B-orange)
  ![Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?logo=googlecolab&logoColor=white)

  <br><br>

  <a href="https://colab.research.google.com/drive/1r4mgqm-Fzd4rqErn_x3R9zZstbe6fdqb?usp=sharing" target="_blank">
    <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Abrir en Colab"/>
  </a>
</div>

---

### 📋 Información Académica
|||
| :--- | :--- |
| **Institución** | Universidad del Pacífico |
| **Programa** | Ingeniería de Sistemas|
| **Asignatura** | Inteligencia Artificial |
| **Fecha de entrega** | 29 de mayo de 2026 |

### 👥 Equipo de Trabajo
* 💻 **Jhon Jader Riascos Angulo**
* 💻 **Charly Johan Murillo Hernández**
* 💻 **Gabriel Alejandro Sanchez Alarcon**

---

## 📌 Contexto del Proyecto

Este repositorio contiene el desarrollo colaborativo del segundo taller práctico de Inteligencia Artificial. A partir de un dataset de 60 productos tecnológicos, realizamos tareas de limpieza, manipulación de variables y análisis estadístico utilizando Python.

> **Objetivo Principal:** Aplicar conceptos fundamentales de análisis de datos mediante la librería **Pandas**, transformando datos crudos en métricas financieras y estadísticas para la toma de decisiones.

---

## 💻 Desarrollo y Resultados del Taller

A continuación, se detalla el flujo de trabajo realizado en nuestro notebook, acompañado de las evidencias visuales de los resultados obtenidos.

### 1️⃣ Exploración y Estructura del DataFrame
Antes de manipular los datos, analizamos su integridad. Se importó el archivo `productos.xlsx`, eliminando columnas residuales. Se verificaron los tipos de datos (`dtypes`), las dimensiones (`shape`) y se generó un resumen estadístico preliminar (`describe`).

<div align="center">
<img width="595" height="257" alt="image" src="https://github.com/user-attachments/assets/0cb43da3-04a0-442a-89f8-3af44f3e4a36" />
  <p><i>Vista inicial de las primeras filas del conjunto de datos.</i></p>
</div>

<br>

### 2️⃣ Operaciones Matemáticas y Financieras
Para entender el impacto de cada producto, creamos columnas dinámicas. 
* Calculamos el **`Total_Venta`** (Precio × Cantidad).
* Calculamos el **`Costo_Total`** sumando el envío.
* Identificamos el producto con el **mayor** y **menor** ingreso total mediante las funciones `.idxmax()` e `.idxmin()`.

<div align="center">
<img width="848" height="257" alt="image" src="https://github.com/user-attachments/assets/3c6e036d-81a8-49ef-95e0-e7efda403324" />
  <p><i>DataFrame actualizado con las nuevas variables financieras: Total_Venta y Costo_Total.</i></p>
</div>

<br>

### 3️⃣ Proyecciones Porcentuales
En el contexto de análisis de negocios, los porcentajes son vitales. Se estimaron variables clave sobre el Total de Ventas:
* **IVA:** 19%
* **Ganancia Estimada:** 25%
* **Pérdida Estimada:** 0.05%
* **Participación:** Qué porcentaje del 100% de los ingresos representa cada ítem, filtrando aquellos que superan el **15%** de participación (Productos Estrella).

<div align="center">
  <img width="1485" height="264" alt="image" src="https://github.com/user-attachments/assets/d25de7c9-81cc-44c5-bce8-56d1a5b3c966" />
  <p><i>Generación de métricas porcentuales y participación en ventas.</i></p>
</div>

<br>

### 4️⃣ Estadística Descriptiva
Para comprender la dispersión y la tendencia central de nuestro inventario, aplicamos funciones estadísticas puras:
* **Media, Mediana y Moda** aplicadas al `Precio`, permitiendo entender el costo promedio frente a los precios más comunes.
* **Desviación Estándar** aplicada a la `Cantidad`, indicando qué tan variable es el volumen de stock entre los distintos productos.

<div align="center">
  <img width="479" height="249" alt="image" src="https://github.com/user-attachments/assets/95e76eb6-3041-4c66-89fd-3f5ba0f4e996" />
  <p><i>Resumen de las medidas estadísticas calculadas.</i></p>
</div>

<br>

### 5️⃣ Filtrado y Ordenamiento Estratégico
El análisis de datos requiere aislar información. Aplicamos indexación booleana para mostrar **exclusivamente la categoría "Tecnología"**, y posteriormente ordenamos el DataFrame de mayor a menor según los ingresos generados (`sort_values`).

<div align="center">
  <img width="1648" height="646" alt="image" src="https://github.com/user-attachments/assets/3ab6a3c5-6510-4bc2-b8cd-9d7c96c5eb96" />
  <p><i>Top de productos de tecnología ordenados por Total de Venta.</i></p>
</div>

<br>

### 🏆 Punto Adicional: Exportación a Excel
Como cierre del flujo de procesamiento, el DataFrame transformado con todas las nuevas columnas numéricas fue exportado exitosamente a un nuevo archivo llamado `resultado_final.xlsx` utilizando el método `to_excel()`.

---

## 🧾 Conclusiones del Análisis

| Concepto | Interpretación y Aprendizaje |
| :--- | :--- |
| **Rendimiento** | Pandas permite crear nuevas variables financieras en una sola línea de código gracias a la **vectorización**, evitando el uso ineficiente de bucles convencionales. |
| **Estadística en IA** | El cálculo de medias y desviaciones estándar no es trivi****al; es el paso previo obligatorio para normalizar datos antes de entrenar modelos de Machine Learning. |
| **Toma de Decisiones** | Funciones como el cálculo de porcentajes de participación permiten a las empresas identificar rápidamente sus "productos estrella" frente a aquellos que generan pérdidas. |
| **Flujo Completo** | Logramos ejecutar un pipeline de datos completo: **Extracción** (Lectura de Excel), **Transformación** (Limpieza y matemáticas) y **Carga** (Exportación a nuevo Excel). |

---

## 🚀 Instrucciones de Ejecución

Si deseas probar nuestro código de manera local o en la nube:

1. Clona este repositorio en tu máquina:
   ```bash
   git clone https://github.com/Jaderdev2/taller-pandas2.git
   ```
2. Si utilizas **Google Colab**, sube el archivo `productos.xlsx` al entorno virtual antes de iniciar.
3. Abre el archivo `Taller_Libreria_Pandas.ipynb` y ejecuta las celdas en orden secuencial.
4. Al finalizar, el entorno generará y descargará automáticamente el archivo `resultado_final.xlsx`.

---

## 📁 Estructura del Directorio

```text
📦 taller-pandas2
 ┣ 📄 README.md                                  # Documentación actual
 ┣ 📓 Taller_Libreria_Pandas.ipynb               # Código fuente y análisis
 ┣ 📊 productos.xlsx                             # Dataset original de entrada
 ┗ 📈 resultado_final.xlsx                       # Dataset procesado (Salida del punto extra)
```


```
