# Pandas: Lectura y manejo de datos con CSV, Excel, Google Sheets y JSON

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/LordAguaKate/Pandas/blob/main/Pandas.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/LordAguaKate/Pandas/blob/main/Tratamiento_y_Manipulacion_de_Datos.ipynb)

## Descripción
Este repositorio contiene notebooks educativos (`Pandas.ipynb` y `Tratamiento_y_Manipulacion_de_Datos.ipynb`) que muestran, de forma práctica y comentada, cómo utilizar la biblioteca `pandas` para:

- Leer y explorar archivos CSV con diferentes separadores.
- Leer, explorar y escribir archivos Excel, incluyendo selección de hojas y columnas.
- Importar datos desde Google Sheets mediante URLs en formato CSV parametrizadas.
- Leer archivos JSON planos y anidados, y normalizarlos con `pd.json_normalize`.

El objetivo es servir como guía rápida de referencia para tareas frecuentes de ingestión y exportación de datos con `pandas`.

## Contenidos del notebook
- **CSV**
  - `pd.read_csv` con parámetros clave: `sep`, `nrows`, `usecols`.
  - Exportación con `DataFrame.to_csv` y uso de `index=False` para evitar columnas de índice.
- **Excel**
  - `pd.read_excel` y `pd.ExcelFile(...).sheet_names` para listar hojas.
  - Selección de hojas con `sheet_name` y de columnas con `usecols`.
  - Exportación con `DataFrame.to_excel` y `index=False`.
- **Google Sheets**
  - Construcción de URLs con el `sheet_id` y el parámetro `tqx=out:csv`.
  - Selección de distintas hojas mediante el parámetro `sheet` en la URL.
- **JSON**
  - Lectura de JSON tabular con `pd.read_json`.
  - Normalización de estructuras anidadas con `pd.json_normalize`.

## Requisitos
- Python 3.9+ recomendado
- Paquetes Python:
  - `pandas`
  - `openpyxl` (para leer/escribir Excel .xlsx)
  - `requests` (opcional, para validar accesos a URLs si lo deseas)

### Instalación rápida (entorno local)
```bash
python -m venv .venv
.venv\Scripts\activate  # Windows
pip install --upgrade pip
pip install -r requirements.txt
```

## Uso

- **Google Colab (recomendado para prueba rápida):**
  - Haz clic en los badges “Open In Colab” de arriba para abrir cualquiera de los notebooks directamente en Colab.
  - Sube los archivos de datos requeridos o ajusta las rutas según sea necesario.

- **Local con Jupyter:**
  - Activa tu entorno y lanza Jupyter:
    ```bash
    jupyter notebook
    ```
  - Abre `Pandas.ipynb` o `Tratamiento_y_Manipulacion_de_Datos.ipynb` y ejecuta las celdas.

## Archivos de datos esperados
El notebook hace referencia a archivos de ejemplo que no necesariamente están incluidos en el repositorio. Colócalos en la raíz del proyecto (o ajusta las rutas en el notebook):

- `superstore_data.csv`
- `superstore_data_punto_coma.csv` (CSV con separador `;`)
- `emisiones_CO2.xlsx`
- `pacientes.json`
- `pacientes_2.json` (con estructuras anidadas)

Para Google Sheets, el notebook utiliza un `sheet_id` de ejemplo y construye URLs parametrizadas para distintas hojas (`emisiones_percapita`, `fuentes`, etc.). Asegúrate de que el archivo esté compartido con acceso mediante enlace.

## Estructura del repositorio
```
Pandas/
├─ Pandas.ipynb                                # Notebook con ejemplos paso a paso
├─ Tratamiento_y_Manipulacion_de_Datos.ipynb   # Notebook complementario
├─ README.md                                   # Este documento
└─ requirements.txt                            # Paquetes requeridos
```

## Notas importantes
- Si al exportar con `to_csv` aparece una columna adicional llamada `Unnamed: 0`, añade `index=False` para evitar que el índice se guarde como columna.
- Para Excel, `openpyxl` es requerido para `.xlsx`. Instálalo si encuentras errores al leer/escribir.
- En `read_csv`, ajusta `sep` si tu archivo no usa coma (por ejemplo, `sep=';'`).
- Cuando leas desde Google Sheets, verifica permisos de acceso y el nombre exacto de la hoja en el parámetro `sheet` de la URL.

## Contribuciones
Las mejoras, correcciones y ejemplos adicionales son bienvenidos. Abre un issue o envía un pull request con una descripción clara del cambio.

## Licencia
Sin licencia.