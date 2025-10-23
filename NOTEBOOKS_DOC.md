# Documentación de notebooks (explicaciones en español)

Este archivo contiene explicaciones línea por línea de los bloques de código más relevantes en los notebooks del proyecto. Está pensado para incluir en el README antes de subir al repositorio.

## Prac1.ipynb

1. import pandas as pd, numpy, matplotlib, seaborn, SimpleImputer
   - Importa las librerías necesarias para manipulación de datos, visualización y operaciones de imputación.

2. data = pd.read_csv('data/train.csv')
   - Carga el dataset `train.csv` desde la carpeta `data`.

3. data.head()
   - Muestra las primeras filas del DataFrame para inspección rápida.

4. data.info()
   - Muestra el esquema del DataFrame, tipos de columnas y nulos.

5. data.describe()
   - Estadísticas descriptivas para columnas numéricas.

6. data.describe(include='object')
   - Estadísticas para variables categóricas.

7. data.shape
   - Tamaño del dataset (filas, columnas).

8. Conversión de `Pclass` a str y luego a int
   - Ejemplifica cómo cambiar tipos de columnas según necesidad.

9. Detección de outliers con boxplot
   - Usa seaborn para visualizar posibles valores atípicos por columna numérica.

10. Histograma de `Fare` y de `Age`
   - Visualizaciones de la distribución de variables importantes.

11. data.isnull().sum() y porcentajes
   - Conteo y porcentaje de valores nulos por columna para priorizar limpieza.

12. Eliminación de columna `Cabin`
   - Se elimina `Cabin` por tener demasiados nulos.

13. Relleno de `Age` con la mediana
   - Imputa valores faltantes de `Age` con su mediana.

14. Imputación de `Embarked` usando SimpleImputer con constante 'S'
   - Ejemplo de cómo rellenar valores categóricos con un valor por defecto.


## Prac2_Sleep.ipynb

1. Importar librerías (pandas, numpy, matplotlib, seaborn)
   - Configuración de librerías para análisis y visualización.

2. data = pd.read_csv('data/sleep health.csv', index_col='Person ID')
   - Carga el dataset de salud del sueño usando `Person ID` como índice.

3. data.info(), data.describe()
   - Inspección inicial de tipos y estadísticas.

4. Selección de columnas numéricas y análisis (media, mediana, std)
   - Análisis descriptivo para columnas numéricas.

5. Creación de `Age_Group` basada en condiciones
   - Genera categorías de edad para comparar grupos.

6. Agrupaciones por `Gender` y `Occupation` y visualizaciones (barras, heatmap, radar)
   - Cálculo de métricas agregadas y gráficos interactivos con Plotly.

7. Cálculo de correlaciones y mapas de calor
   - Estudia relaciones entre métricas promedio por ocupación.


## Limpieza2.ipynb

1. Carga de `data/all_games.csv`
   - Inspección y limpieza básica de un dataset de juegos.

2. Detección y eliminación de duplicados
   - `data.drop_duplicates(inplace=True)`.

3. Manejo de nulos y reemplazo por texto 'summary not available'
   - `data.fillna('summary not available', inplace=True)`.

4. Conversión de valores no numéricos en `user_review` a numéricos
   - `pd.to_numeric(..., errors='coerce')` para forzar NaN donde no sea convertible.


## Preba1.ipynb

1. Importación de librerías y carga de `data/train.csv`
   - Preparación y vista rápida del dataset.

2. Visualizaciones y conteos para columnas categóricas
   - Uso de seaborn para countplot y matplotlib para histogramas.

3. Selección de columnas numéricas y cálculo de matriz de correlación
   - Generación de heatmap con `sns.heatmap`.

4. Detección de outliers con IQR por columna
   - Cuenta de outliers usando límites IQR.


## Profiling.ipynb

1. import pandas, numpy y print(pd.__version__)
   - Importa librerías y muestra la versión de pandas (útil para compatibilidad).

2. Intento de importar `ydata_profiling` en bloque try/except
   - Si está disponible, se usa `ProfileReport`; si no, el notebook imprime instrucción de instalación.

3. df = pd.read_csv('data/train.csv')
   - Carga el dataset principal para profiling.

4. display(df.head()) y df.info()
   - Vista rápida y esquema del DataFrame.

5. Si `ydata_profiling` está disponible, crear `ProfileReport(df, minimal=True)` y guardar `profiling_report.html`
   - Genera un informe EDA automatizado con características exploratorias avanzadas.


---

Si quieres que genere también un archivo con comentarios insertados directamente dentro de los notebooks (como celdas markdown explicativas añadidas), puedo hacerlo, pero por ahora dejé la documentación externa en `NOTEBOOKS_DOC.md`.
