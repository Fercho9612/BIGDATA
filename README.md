# 🎵 Proyecto: Procesamiento de Canciones de Spotify en Databricks (Cloud)

Este proyecto automatiza la ingesta, limpieza y análisis de las 50 canciones más escuchadas de Spotify en 2019 utilizando **Apache Spark (PySpark)** y **Spark SQL**.

---

## 🛠️ ¿Cómo hacer funcionar este repositorio?

El código está diseñado para ejecutarse en **Databricks**. Para que corra correctamente sin modificar el script, sigue estos dos sencillos pasos antes de presionar *Run All*:

### 1. Preparar los Datos (Infraestructura)
* Ve a la sección **Catalog** en tu entorno de Databricks.
* Sube el archivo `top50.csv` (que está dentro de la carpeta `data` de este repositorio).
* **Importante:** Nombra la tabla exactamente como **`top_50`** dentro del catálogo `workspace` y esquema `default`. 
*(La ruta debe quedar: `workspace.default.top_50`)*.

### 2. Ejecutar el Código
* Importa el archivo `.ipynb` de este repositorio a tu espacio de trabajo de Databricks.
* Conéctalo a un clúster activo y ejecútalo. El script buscará la tabla que creaste en el paso anterior y hará todo el proceso automáticamente.

---

## 📁 Contenido del Repositorio

* 📁 ** Contiene el archivo original `top50.csv` extraído de Kaggle.
* 📄 **`GRUPO12_Actividad_2...ipynb`**: Notebook con todo el código de ingeniería de datos.

---

## ⚙️ ¿Qué hace el código automáticamente?

1. **Aplica un esquema estricto (`StructType`):** Fuerza a que cada columna tenga el tipo de dato correcto (Textos o Números Enteros) para evitar errores.
2. **Limpia los encabezados:** Elimina puntos y caracteres extraños de las columnas originales (ej. convierte `Track.Name` a `Track_Name`).
3. **Guarda los resultados:** Crea una nueva tabla optimizada en la nube llamada `top_50_limpio`.
4. **Analiza los datos:** Realiza consultas para conocer los géneros musicales más populares y estadísticas clave del dataset.
