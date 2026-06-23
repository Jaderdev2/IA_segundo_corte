# 📊 Taller Práctico de NumPy, Matplotlib y Seaborn - Caso 5: Mantenimiento Predictivo

<div align="center">
  <img width="650" height="157" alt="logo_unipacifico" src="https://github.com/user-attachments/assets/8427b307-d631-426b-ba2c-cdef5d505086" />
  <br><br>

  ![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
  ![NumPy](https://img.shields.io/badge/NumPy-1.24%2B-orange)
  ![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-green)
  ![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7%2B-red)
  ![Seaborn](https://img.shields.io/badge/Seaborn-0.12%2B-skyblue)
  ![Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?logo=googlecolab&logoColor=white)

  <br><br>

  <a href="https://colab.research.google.com/drive/10aj9kXoJtTKo4z4wKlb4zm5AWfAL92n6?usp=sharing" target="_blank">
    <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Abrir en Colab"/>
  </a>
</div>

---

### 📋 Información Académica
|||
| :--- | :--- |
| **Institución** | Universidad del Pacífico |
| **Programa** | Ingeniería de Sistemas |
| **Asignatura** | Inteligencia Artificial |
| **Docente** | Wilman Andrés Quiñónez V. |
| **Semestre** | Octavo |
| **Fecha de entrega** | 22 de junio de 2026 |

### 👥 Equipo de Trabajo
* 💻 **Jhon Jader Riascos Angulo**
* 💻 **Charly Jhoan Murillo Hernández**
* 💻 **Gabriel Alejandro Sanchez Alarcon**
* 💻 **Brayan David Riascos Murillo**

---

## 📌 Contexto del Proyecto

Este repositorio contiene el desarrollo del cuarto taller práctico de Inteligencia Artificial. Nos enfocamos en el **Caso de Estudio 5: Mantenimiento Predictivo en una Fábrica Inteligente**, una estrategia crucial de la Industria 4.0 que utiliza el análisis de datos continuos para predecir fallas en motores industriales antes de que estas interrumpan las operaciones de manufactura.

> **Objetivo Principal:** Desarrollar un pipeline completo de Análisis Exploratorio de Datos (EDA) empleando **NumPy** para el procesamiento matemático, **Pandas** para la manipulación estructurada, y **Matplotlib** junto a **Seaborn** para la visualización estadística avanzada de variables físicas de un entorno industrial.

---

## 💻 Desarrollo y Resultados del Taller

A continuación, se detalla el flujo de trabajo realizado en nuestro notebook y las evidencias visuales de cada uno de los puntos requeridos.

### 1️⃣ Generación de Datos Sintéticos (Caso 5)
Para simular el entorno de una fábrica real de manera profesional, generamos **500 observaciones** correlacionadas lógicamente con NumPy:
* Las máquinas con mayor tiempo de uso tienen mayor desgaste, lo que se traduce en mayor temperatura y vibración mecánica.
* Definimos un sistema lógico donde si una máquina supera simultáneamente los $85^\circ\text{C}$ de temperatura y los $5.5\text{ mm/s}$ de vibración, se cataloga automáticamente en estado de **Falla**.

```python
# Creación estructurada del DataFrame en Pandas
datos = pd.DataFrame({
    "Temperatura del Motor": temperatura,
    "Vibración": vibracion,
    "Horas de Uso": horas_uso,
    "Consumo Eléctrico": consumo_electrico,
    "Falla": falla
})
```

---

### 2️⃣ Análisis Estadístico (NumPy)
Utilizando exclusivamente funciones vectorizadas de **NumPy**, procesamos el dataset para extraer las métricas de tendencia central, dispersión y percentiles de las variables operativas de la planta.

| Variable | Media (Promedio) | Mediana | Desviación Estándar | Rango Intercuartil (P25 - P75) |
| :--- | :---: | :---: | :---: | :---: |
| **Temperatura del Motor (°C)** | 74.52 | 74.34 | 10.02 | 67.80 - 81.33 |
| **Vibración (mm/s)** | 3.96 | 3.97 | 1.15 | 3.19 - 4.74 |
| **Horas de Uso (Horas)** | 2761.50 | 2772.10 | 1290.41 | 1634.20 - 3881.90 |
| **Consumo Eléctrico (kWh)** | 119.55 | 119.12 | 19.46 | 106.33 - 132.31 |

*   **Interpretación:** La variable con mayor estabilidad relativa es la vibración, mientras que las horas de uso y el consumo eléctrico presentan una alta desviación estándar, lo cual confirma la diversidad del estado de desgaste de la maquinaria en la planta. El 50% de las máquinas operan entre 1,634 y 3,881 horas de servicio.

---

## 📈 Análisis Visual Individual (Matplotlib)

Realizamos análisis descriptivos y de dispersión individuales utilizando exclusivamente **Matplotlib**.

### 📊 Histograma de Temperatura del Motor
Muestra la distribución térmica de los motores en la planta. La mayor parte opera en torno a los $75^\circ\text{C}$.

<div align="center">

  <img width="541" height="402" alt="image" src="https://github.com/user-attachments/assets/5664825f-acf5-4920-add4-1793ce61984e" />
  <p><i>Distribución de frecuencia térmica en los motores industriales.</i></p>
</div>

*   **Interpretación:** Las temperaturas superiores a los $85^\circ\text{C}$ o $90^\circ\text{C}$ corresponden a un porcentaje menor de máquinas, pero representan la zona de riesgo térmico extremo donde las fallas comienzan a manifestarse de forma crítica.

### 📊 Histograma de Vibración Mecánica
Permite rastrear las frecuencias del movimiento u oscilación de los componentes mecánicos del motor.

<div align="center">
<img width="541" height="402" alt="image" src="https://github.com/user-attachments/assets/ee4706e4-3781-4fc9-ad7f-802b0ec9c51e" />

  <p><i>Espectro de vibración en milímetros por segundo (mm/s).</i></p>
</div>

*   **Interpretación:** La zona de operación segura se sitúa alrededor de los $4.0\text{ mm/s}$. Desviaciones mayores a los $5.5\text{ mm/s}$ actúan como alarmas físicas de desajustes mecánicos graves o rodamientos desgastados.

### 📉 Dispersión: Temperatura vs. Vibración
Analizamos visualmente cómo interactúan el calor por fricción y el movimiento mecánico desalineado.

<div align="center">
  <img width="531" height="402" alt="image" src="https://github.com/user-attachments/assets/86b12a2b-fa96-467e-8cd1-26ec0c32dc9c" />

  <p><i>Relación térmica-mecánica y su impacto en el estado operativo de las máquinas.</i></p>
</div>

*   **Interpretación:** Se observa una correlación positiva indirecta. El incremento de temperatura coexiste con mayores niveles de vibración, empujando los datos a la zona crítica donde el sobreesfuerzo térmico y el desajuste mecánico provocan la falla inminente.

### 📉 Dispersión: Horas de Uso vs. Consumo Eléctrico
Evaluamos el impacto del envejecimiento físico sobre la eficiencia energética del activo.

<div align="center">
  <img width="550" height="402" alt="image" src="https://github.com/user-attachments/assets/a382e308-dc16-4072-a435-1f0c6a487397" />
  <p><i>Desgaste operativo e ineficiencia energética en las máquinas industriales.</i></p>
</div>

*   **Interpretación:** A medida que aumentan las horas de uso acumuladas de la maquinaria, el consumo eléctrico se eleva. Esto confirma que las piezas mecánicas desgastadas generan más resistencia y demandan mayor corriente eléctrica para operar.

---

## 🧬 Análisis Estadístico Avanzado (Seaborn)

Para un entendimiento multivariado profundo, implementamos gráficos estadísticos complejos apoyados en **Seaborn**.

### 🌡️ Mapa de Calor (Heatmap) de Correlación
Calculamos la relación lineal matemática exacta de Pearson entre las variables continuas y el estado binario de la Falla.

<div align="center">
  <!-- Mapa de Calor (Heatmap) -->
  <img width="795" height="707" alt="image" src="https://github.com/user-attachments/assets/39549c93-eeb6-430a-a485-051cf945aa72" />
  <p><i>Matriz de correlación lineal de las variables del proceso.</i></p>
</div>

*   **Interpretación:** Confirmamos que la **Temperatura del Motor** y la **Vibración** tienen coeficientes de correlación muy elevados con el fallo, ratificándolas como los indicadores predictivos más robustos del sistema industrial.

### 📦 Gráfico Boxplot (Diagramas de Cajas)
Evaluamos y comparamos la variabilidad de las variables según el estado operativo de la máquina.

<div align="center">
  <!-- Boxplots de Seaborn (Temperatura y Vibración) -->
<img width="1384" height="484" alt="image" src="https://github.com/user-attachments/assets/f4756636-4f0c-4943-8b3a-172f698b1709" />


  <p><i>Comparación de cuartiles y rangos operativos para máquinas sanas (No) y fallidas (Sí).</i></p>
</div>

*   **Interpretación:** Las cajas de las máquinas con falla se sitúan notablemente por encima en los ejes térmico y mecánico. El 50% de las máquinas con falla operan arriba de los $85^\circ\text{C}$ y de los $5.0\text{ mm/s}$ de vibración.

### 🔗 Gráfico de Pares (Pairplot)
Visualizamos la matriz completa de correlaciones e histogramas cruzados para todos los pares de variables.

<div align="center">
  <!-- Pairplot de 16 gráficos (4x4) -->
<img width="1069" height="1021" alt="image" src="https://github.com/user-attachments/assets/96258842-9c5c-4be5-bc68-8b2e53492ff2" />

  <p><i>Matriz completa de 16 gráficos cruzados comparando las variables del dataset.</i></p>
</div>

*   **Interpretación:** La distribución muestra una separación por conglomerados de color rojo (Fallas) y azul (Sanas) altamente definida en múltiples planos, demostrando la alta idoneidad de este dataset para el entrenamiento de algoritmos supervisados de clasificación.

---

##  Análisis Exploratorio de Datos (EDA)

Siguiendo estrictamente los requisitos metodológicos del taller, resumimos los hallazgos exploratorios en tres pilares:

| Pilar Analítico | Detalle y Hallazgo Clave |
| :--- | :--- |
| **1. Hallazgos Encontrados** | Las fallas no son aleatorias; se concentran en máquinas que superan las **3,500 horas de uso** y presentan ineficiencias concurrentes de temperatura y consumo de energía. |
| **2. Relaciones entre Variables** | La Temperatura y la Vibración interactúan directamente (correlación positiva). Además, las horas acumuladas elevan el gasto en kWh, lo que representa una ineficiencia invisible pero costosa para la planta. |
| **3. Variables más Relevantes** | Para cualquier modelo predictivo, las variables con mayor peso estadístico son la **Temperatura del Motor** (térmica), la **Vibración** (física) y las **Horas de Uso** (acumulativa). |

---

##  Preguntas de Análisis del Caso 5
Para dar cumplimiento al punto 3.4 del taller práctico, se da respuesta a las preguntas clave del caso de estudio:

1. **¿Qué indicadores anticipan una falla?**
   Los indicadores principales son la **Temperatura del Motor** y la **Vibración**. Un incremento continuo por encima del promedio en estas dos variables es la señal directa de desgaste que antecede al daño físico del equipo.
2. **¿Qué comportamiento tienen las máquinas defectuosas?**
   Operan de manera ineficiente: registran temperaturas elevadas ($>85^\circ\text{C}$), alta fricción y desalineamiento mecánico (vibración $>5.5\text{ mm/s}$), alto consumo de energía ($>140\text{ kWh}$) y suelen acumular una cantidad crítica de horas de servicio ($>3,500\text{ horas}$).
3. **¿Qué beneficios tendría un sistema de mantenimiento predictivo basado en IA?**
   Permite automatizar la detección de fallas antes de que ocurran, evitando costos por paradas no programadas en la planta, reduciendo el gasto de repuestos inútiles y garantizando la seguridad industrial de los operarios de la fábrica.

---

## 🧾 Conclusiones del Análisis

| Concepto | Interpretación y Aprendizaje |
| :--- | :--- |
| **Fricción y Movimiento** | Las fallas son causadas por una sinergia física desfavorable: el aumento de temperatura debilita los componentes mecánicos, provocando mayores holguras y vibraciones extremas. |
| **Desgaste Exponencial** | Superar las 3,500 horas de operación continua coloca a las máquinas en una zona de riesgo mecánico alto, requiriendo revisiones mandatorias independientemente de su estado aparente. |
| **Pérdida de Eficiencia** | Las máquinas al borde del colapso presentan un desperdicio energético promedio del 20%, lo que significa que el monitoreo de kWh sirve como un excelente indicador preventivo secundario. |
| **Poder de Visualización** | La transición de Matplotlib a Seaborn permite realizar visualizaciones estadísticas complejas en pocas líneas de código, acelerando el proceso de exploración científica de datos. |
| **Idoneidad para ML** | La clara segmentación visual de conglomerados (Sanas vs. Fallidas) valida que el dataset es óptimo para algoritmos de clasificación supervisados (SVM, Random Forest o Redes Neuronales). |

---

## Recomendaciones Empresariales

1.  **Instalación de Sensores IoT Activos:** Monitorear en tiempo real los motores en la planta. Activar pre-alertas automáticas en el software SCADA en cuanto un equipo supere los $80^\circ\text{C}$ o los $4.5\text{ mm/s}$ de vibración.
2.  **Mantenimiento Preventivo Ciclo-Horas:** Reestructurar los planes de mantenimiento para que ningún activo supere las 3,500 horas de servicio continuo sin pasar por un cambio preventivo de rodamientos y lubricación de componentes.
3.  **Auditoría de kWh:** Retirar de forma programada cualquier equipo que demuestre consumos mayores a 140 kWh en periodos de carga estándar, ya que es síntoma de un sobreesfuerzo de motor inminente a fallar.

---

## Reflexión de Inteligencia Artificial

Para automatizar la toma de decisiones críticas en esta planta inteligente, se propone estructurar un **Pipeline de Machine Learning en tiempo real**. Los datos de vibración y temperatura de los sensores alimentarán continuamente un modelo de clasificación supervisada (como *XGBoost*).

*   **Toma de Decisiones Autónoma:** Al predecir una probabilidad de fallo superior al 75%, el modelo de IA interactuará mediante APIs directamente con el software de gestión de activos de la empresa para **generar automáticamente una orden de trabajo de mantenimiento**, apartando los repuestos en el inventario de la planta.
*   **Mitigación en Tiempo Real:** En escenarios de alto riesgo inminente ($P_{\text{falla}} > 90\%$), la IA enviará una señal directa a los PLCs de las máquinas para **reducir de forma automática la velocidad operativa de los motores** o forzar una parada controlada de emergencia, protegiendo la vida de los técnicos y evitando la destrucción catastrófica de los activos físicos de la fábrica.

---

```
