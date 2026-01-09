# Proyecto de Análisis de Datos -

Descripción
-----------
Repositorio proyecto de Analítica Avanzada usando los datasets de la carpeta `data/`.

Contenido del repositorio
-------------------------
- Datos en `data/`:
   - `data/train.csv`
   - `data/all_games.csv`
   - `data/sleep health.csv`
- Artefactos (salidas exportadas):
   - `profiling_report.html`
   - `fare_distribution.html`
   - `histogram_age.html`
- Documentación:
   - `NOTEBOOKS_DOC.md` - Documentación previa (legacy).

Nota: Los notebooks anteriores se eliminaron para rehacer el proyecto desde cero.

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
1. Coloca/actualiza los archivos de entrada en `data/`.
2. Crea tus nuevos notebooks o scripts (según lo que pida la materia) y usa rutas relativas como `data/train.csv`.

Evaluación rápida del estado actual
----------------------------------
- Datasets disponibles en `data/`.
- El proyecto está listo para rehacer análisis/notebooks desde cero.

Recomendaciones / siguientes pasos
---------------------------------
1. Limpiar outputs de los notebooks antes de commitear para mantener el repo ligero.
2. Mantener los datasets en `data/` y usar rutas relativas `data/...`.
3. Revisar si quieres versionar artefactos grandes (HTML) o generarlos bajo demanda.

Resumen de cambios
------------------
- Añadido `README.md` con descripción, instrucciones y recomendaciones.

Badges
------

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)
