# Análisis Detallado de la Base de Datos de Habilidades

Este repositorio contiene el proceso de análisis realizado sobre el archivo de base de datos `consolidado_final_habilidades_mapha_061224.xlsx` mediante el código presente en `analisis_detallado_archivo_091224.ipynb`. A continuación, se describe el flujo de trabajo, las herramientas utilizadas y los resultados obtenidos.

## Contenido del Repositorio

- **`consolidado_final_habilidades_mapha_061224.xlsx`**: Archivo Excel que contiene la base de datos inicial a ser analizada.
- **`analisis_detallado_archivo_091224.ipynb`**: Notebook en Python que documenta y ejecuta el análisis detallado del archivo.
- **Imágenes Generadas**: Gráficas y visualizaciones que resumen los hallazgos.

## Objetivo del Análisis

El propósito principal del análisis es depurar y explorar los datos de habilidades para identificar patrones, inconsistencias y realizar una representación visual significativa que permita comprender mejor las tendencias en la base de datos.

## Requisitos Previos

Para ejecutar el código contenido en el notebook, necesitas:

1. Python 3.8 o superior.
2. Las siguientes bibliotecas instaladas:
   ```bash
   pip install pandas numpy matplotlib seaborn openpyxl
   ```

## Proceso de Análisis

### 1. **Carga de Datos**

El archivo Excel fue cargado y explorado para comprender la estructura de los datos:
```python
import pandas as pd

# Cargar el archivo Excel
archivo = "consolidado_final_habilidades_mapha_061224.xlsx"
datos = pd.read_excel(archivo)

# Vista preliminar de los datos
datos.head()
```

### 2. **Exploración de los Datos**

Se analizaron las columnas, tipos de datos y valores nulos:
```python
# Información general sobre los datos
datos.info()

# Estadísticas descriptivas
datos.describe()
```
Se identificaron columnas clave y potenciales inconsistencias.

### 3. **Limpieza de Datos**

Se manejaron valores nulos, duplicados y errores tipográficos:
```python
# Eliminación de duplicados
datos = datos.drop_duplicates()

# Rellenar valores nulos con un valor por defecto
datos = datos.fillna("Sin Especificar")
```

### 4. **Análisis Exploratorio (EDA)**

Se crearon visualizaciones para identificar patrones:
```python
import matplotlib.pyplot as plt
import seaborn as sns

# Ejemplo: Distribución de una columna clave
sns.histplot(datos["Habilidad"], kde=True)
plt.title("Distribución de Habilidades")
plt.show()
```

### 5. **Resultados Clave**

1. **Distribución de Habilidades**: Las habilidades se concentran en ciertos dominios clave, destacándose un conjunto reducido de competencias altamente demandadas.
2. **Datos Faltantes**: Menos del 5% de los registros contenían valores nulos tras la limpieza.
3. **Tendencias Identificadas**: Algunos patrones interesantes incluyen un incremento en la frecuencia de ciertas habilidades específicas.

### 6. **Exportación de Resultados**

Los datos procesados fueron guardados en un nuevo archivo Excel:
```python
# Exportar los datos procesados
datos.to_excel("datos_procesados.xlsx", index=False)
```

Adicionalmente, las gráficas generadas se guardaron en formato PNG para documentar los hallazgos.

## Visualizaciones Incluidas

El notebook contiene varias gráficas:

1. **Distribución de Habilidades**: Representación de la frecuencia de habilidades.
2. **Comparativas por Categorías**: Visualizaciones que destacan las diferencias entre grupos de datos.

Ejemplo de código para guardar una gráfica:
```python
plt.savefig("distribucion_habilidades.png")
```

## Instrucciones para Usar el Notebook

1. Descarga el repositorio.
2. Asegúrate de instalar los requisitos listados.
3. Abre el archivo `analisis_detallado_archivo_091224.ipynb` con Jupyter Notebook.
4. Ejecuta las celdas secuencialmente para replicar el análisis.

## Contribuciones

Las contribuciones al proyecto son bienvenidas. Por favor, sigue los pasos a continuación:

1. Haz un fork del repositorio.
2. Crea una rama para tu función o corrección:
   ```bash
   git checkout -b nombre-de-tu-rama
   ```
3. Realiza un pull request describiendo los cambios.

## Contacto

Si tienes preguntas o sugerencias, no dudes en abrir un Issue o contactarnos directamente.

---

**Autor:** Renzo Valencia Oyace - Proyecto MAPHA


