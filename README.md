# 📊 Análisis y Segmentación de Clientes - ConnectaTel

## Objetivo del Proyecto
Analizar, limpiar y segmentar los datos de los usuarios de la compañía de telecomunicaciones **ConnectaTel** mediante técnicas de análisis de datos con Python (Pandas y Seaborn). El propósito es identificar patrones de comportamiento, evaluar el impacto de los outliers y proporcionar insights accionables para la toma de decisiones comerciales y la estrategia de planes.

---

## Datasets Utilizados
El proyecto integra las siguientes fuentes de datos principales:
* **`users` (Datos demográficos):** Información de los clientes, incluyendo ID, nombres, edad, ciudad de residencia, fecha de registro y tipo de plan contratado (*Básico* o *Premium*).
* **`usage` (Datos de comportamiento):** Registro histórico de interacciones de los usuarios, detallando el tipo de servicio (*call* o *text*), duración y longitud.
* **`plans`:** Detalle de las características de los planes comerciales ofrecidos por la compañía.

---

## Etapas del Análisis Realizadas
1. **Limpieza y Preprocesamiento:** 
   * Tratamiento de valores centinela (imputación de la mediana en la edad para valores `-999`).
   * Corrección de formato y manejo de valores nulos o fechas futuras anómalas en `reg_date`.
   * Diagnóstico de nulos estructurales de tipo **MAR** (*Missing At Random*) en las columnas `duration` y `length` según el tipo de servicio.
2. **Agregación de Métricas:** Consolidación de la información de uso por usuario (`user_id`) para calcular el total de mensajes, llamadas y minutos acumulados, combinándolos con el perfil demográfico.
3. **Análisis Exploratorio de Datos (EDA):** Visualización de distribuciones mediante histogramas y diagramas de caja (*boxplots*) para evaluar variables clave y justificar la retención de valores extremos (*outliers* legítimos de consumo).
4. **Segmentación de Clientes:**
   * **Por Uso (`grupo_uso`):** Clasificación en *Bajo uso*, *Uso medio* y *Alto uso* utilizando umbrales lógicos sobre la cantidad de llamadas y mensajes.
   * **Por Edad (`grupo_edad`):** Segmentación demográfica en *Joven* (<30 años), *Adulto* (30 a 59 años) y *Adulto Mayor* ($\ge$60 años).
5. **Conclusiones Ejecivas:** Traducción de los hallazgos técnicos en recomendaciones estratégicas para los *stakeholders*.

---

## Cómo Ejecutar el Notebook
Puedes abrir y ejecutar el proyecto de dos formas sencillas:
1. **En Google Colab:** Sube el archivo `.ipynb` a Google Colab asegurándote de cargar los archivos de datos (`users`, `usage`, etc.) en el entorno de ejecución.
2. **Localmente (Jupyter Notebook):** 
   * Asegúrate de tener Python instalado junto con las librerías requeridas (`pandas`, `numpy`, `matplotlib`, `seaborn`).
   * Coloca los datasets en la misma carpeta que el cuaderno de Jupyter.
   * Abre Jupyter Notebook y ejecuta las celdas secuencialmente de arriba hacia abajo.

---

## Guía de Reproducción Rápida
1. Clona o descarga este repositorio en tu equipo.
2. Abre el archivo de Jupyter Notebook (`.ipynb`).
3. Comprueba que las rutas de los archivos CSV coincidan con tu directorio de trabajo.
4. Ejecuta cada celda en orden para reproducir la limpieza, los gráficos estadísticos, la segmentación y los insights ejecutivos.
