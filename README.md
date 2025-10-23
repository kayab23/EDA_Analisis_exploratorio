Documentación técnica detallada
------------------------------
He añadido `NOTEBOOKS_DOC.md` con descripciones línea por línea de los bloques de código más relevantes en los notebooks principales. Esto sirve como documentación previa al commit.
Lista de comandos sugeridos para subir (no ejecutados)
---------------------------------------------------
Ejemplo de comandos para versionar y subir al repositorio remoto (ejecuta desde PowerShell o tu terminal Git):

```powershell
git add .
git commit -m "Limpieza: actualizar notebooks, añadir documentación y arreglar profiling"
git push origin main
```

Nota: asegúrate de revisar `.gitignore` y decidir si quieres incluir la carpeta `data/` (contiene los CSV). Si prefieres no subir los CSV, añade `data/` a `.gitignore`.
# Proyecto de Análisis de Datos - practica TuTekGuy

Descripción
-----------
Colección de notebooks y conjuntos de datos para análisis exploratorio y preprocesamiento. Los notebooks contienen tareas de limpieza, visualización y preparación de datos (por ejemplo, imputación de valores faltantes, detección de outliers y gráficos básicos).

Contenido del repositorio
-------------------------
- `Prac1.ipynb` - Notebook principal (EDA y preprocesamiento) que carga `train.csv`, analiza columnas, rellena `Age` por la mediana, elimina `Cabin`, imputa `Embarked` y realiza visualizaciones.
- `Prac2_Sleep.ipynb`, `Profiling.ipynb`, `Limpieza2.ipynb`, `Preba1.ipynb` - Otros notebooks de trabajo (exploración y experimentos con distintos datasets).
- `all_games.csv`, `sleep health.csv`, `train.csv` - Conjuntos de datos usados por los notebooks.
- `fare_distribution.html`, `histogram_age.html` - Salidas estáticas (gráficos) generadas desde notebooks.

Requisitos
----------
Se provee un `requirements.txt` con las dependencias más usadas en los notebooks. Se recomienda crear un entorno virtual antes de instalar.

Instalación (Windows - PowerShell)
---------------------------------
1. Crear y activar un entorno virtual (opcional pero recomendado):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

2. Instalar dependencias:

```powershell
pip install -r requirements.txt
```

Cómo usar
---------
1. Abrir los notebooks con Jupyter o Visual Studio Code (extensión Jupyter).
   - Desde PowerShell puedes lanzar Jupyter Lab o Notebook:

```powershell
jupyter lab
# o
jupyter notebook
```

2. Ejecutar las celdas en orden. Algunos notebooks asumen que los CSV están en la raíz del proyecto (p. ej. `train.csv`). Si mueves los datos, actualiza las rutas en las celdas.

Evaluación rápida del estado actual
----------------------------------
- El notebook `Prac1.ipynb` realiza un EDA básico y algunas imputaciones (Age, Embarked) y eliminación de columnas con muchos nulos (Cabin). Hay visualizaciones guardadas en HTML.
- Los notebooks contienen celdas con código de análisis y visualización; conviene limpiar salidas (outputs) antes de commitear para mantener el repo ligero.

Recomendaciones / siguientes pasos
---------------------------------
1. Añadir `.gitignore` que incluya:
   - `.venv/` o la carpeta del entorno virtual
   - `.ipynb_checkpoints/`
   - `__pycache__/`
   - `*.pyc`
   - `data/` si vas a mover los CSV a una carpeta privada
2. Crear una carpeta `data/` y mover los datasets allí. Actualizar notebooks con rutas relativas `data/train.csv`.
3. Limpiar outputs de los notebooks antes de subirlos (en Jupyter: File > Clear All Outputs).
4. Convertir análisis reproducibles en scripts (por ejemplo `notebooks/` vs `src/`) y añadir un pequeño pipeline o Makefile para ejecutar pasos reproducibles.
5. Añadir un `requirements-dev.txt` si necesitas herramientas adicionales (black, isort, pytest) y tests básicos.
6. Considerar añadir un `LICENSE` y un `CONTRIBUTING.md` si el repositorio será público.

Contacto
--------
Si necesitas que adapte este README (ej. en inglés, con versiones de paquetes, o con instrucciones para Docker), dime qué prefieres y lo actualizo.

Badges
------

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)

Desarrollo
----------

Para contribuir y ejecutar las herramientas de desarrollo:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements-dev.txt
pre-commit install
```

El script `scripts/run_notebooks.py` permite ejecutar todos los notebooks o una lista concreta:

```powershell
# Ejecutar todos los notebooks y guardar copias ejecutadas
python .\scripts\run_notebooks.py -l "*"

# Ejecutar varios notebooks concretos
python .\scripts\run_notebooks.py -l "Prac1.ipynb,Preba1.ipynb"

# Ejecutar y sobrescribir los notebooks originales
python .\scripts\run_notebooks.py -l "Prac1.ipynb" -o
```

Resumen de cambios
------------------
- Añadido `README.md` con descripción, instrucciones y recomendaciones.
