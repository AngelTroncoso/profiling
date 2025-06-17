# Análisis de Datos con Python - Perfilado Html.
![](https://image.lexica.art/full_webp/3366c9c6-1f33-419e-9994-a2a321f8f7aa)

Este repositorio contiene scripts y notebooks de Python para realizar análisis exploratorio de datos (EDA) y generar informes interactivos en HTML utilizando la librería `pandas-profiling` (o `ydata-profiling`).

## 🚀 Inicio Rápido

Sigue estos pasos para poner en marcha tu análisis de datos y generar informes.

### 📋 Prerrequisitos

Asegúrate de tener Python instalado (versión 3.7 o superior recomendada).

### 🛠️ Instalación

1.  **Clona este repositorio:**

    ```bash
    git clone [https://github.com/tu_usuario/tu_repositorio_analisis_datos.git](https://github.com/tu_usuario/tu_repositorio_analisis_datos.git)
    cd tu_repositorio_analisis_datos
    ```

2.  **Crea un entorno virtual (recomendado):**

    ```bash
    python -m venv venv
    # En Windows
    .\venv\Scripts\activate
    # En macOS/Linux
    source venv/bin/activate
    ```

3.  **Instala las dependencias:**

    ```bash
    pip install pandas numpy matplotlib seaborn jupyterlab ydata-profiling
    ```
    *Nota: Si tienes problemas con `ydata-profiling`, prueba con `pip install pandas-profiling` (versiones anteriores).*

## 📂 Estructura del Repositorio

```
├── data/
│   └── raw_data.csv            # Archivos de datos brutos
├── notebooks/
│   └── 01_eda_profiling.ipynb  # Notebooks de Jupyter para análisis
├── scripts/
│   └── generate_report.py      # Script Python para generar informes
├── reports/
│   └──                   # Directorio para los informes HTML generados
├── .gitignore
├── README.md
└── requirements.txt
```
## 📈 Cómo Usar

### 1. Prepara tus Datos

Coloca tus archivos de datos (por ejemplo, `.csv`, `.xlsx`) en el directorio `data/`. Puedes renombrar `raw_data.csv` o agregar nuevos archivos.

### 2. Ejecuta el Análisis

Puedes elegir entre usar un script o un notebook de Jupyter.

#### Opción A: Usando el Script Python

El script `generate_report.py` está diseñado para automatizar la generación de informes.

1.  **Edita `scripts/generate_report.py`:**
    Asegúrate de que la ruta de tu archivo de datos esté correctamente configurada.

    ```python
    # scripts/generate_report.py
    import pandas as pd
    from ydata_profiling import ProfileReport # O from pandas_profiling import ProfileReport

    # Carga tus datos
    df = pd.read_csv('../data/your_data_file.csv') # ¡Asegúrate de cambiar esto!

    # Genera el informe
    profile = ProfileReport(df, title="Informe de Perfilado de Datos")
    profile.to_file("../reports/your_data_report.html") # El informe se guardará aquí

    print("Informe generado exitosamente en reports/your_data_report.html")
    ```

2.  **Ejecuta el script:**

    ```bash
    python scripts/generate_report.py
    ```

    Esto generará un archivo HTML interactivo en el directorio `reports/`.

#### Opción B: Usando el Notebook de Jupyter

Para un análisis más interactivo y exploratorio, usa el notebook de Jupyter.

1.  **Inicia JupyterLab:**

    ```bash
    jupyter lab
    ```

2.  **Abre `notebooks/01_eda_profiling.ipynb`:**
    Sigue las celdas para cargar tus datos, realizar análisis básicos y generar el informe de perfilado.

    ```python
    # Dentro de notebooks/01_eda_profiling.ipynb
    import pandas as pd
    from ydata_profiling import ProfileReport # O from pandas_profiling import ProfileReport

    # Carga tus datos
    df = pd.read_csv('../data/raw_data.csv') # Cambia esto a tu archivo

    # Muestra las primeras filas
    print(df.head())

    # Genera el informe de perfilado
    profile = ProfileReport(df, title="Informe de Perfilado de Datos del Notebook")
    profile.to_widgets() # Para ver el informe dentro del notebook
    # O para guardar en HTML:
    # profile.to_file("../reports/notebook_report.html")
    ```

### 3. Visualiza el Informe

Abre el archivo `.html` generado en el directorio `reports/` con tu navegador web preferido para explorar el informe interactivo. Este informe incluye:

* **Descripción general:** Estadísticas de alto nivel, tipo de variables, valores perdidos.
* **Variables:** Estadísticas detalladas para cada columna (distribución, valores únicos, etc.).
* **Interacciones:** Gráficos de dispersión y correlación entre variables.
* **Correlaciones:** Mapas de calor de diferentes tipos de correlación (Pearson, Spearman, Kendall, Phik).
* **Valores perdidos:** Matriz, recuento y dendrograma de valores perdidos.
* **Muestra:** Las primeras y últimas filas del dataset.

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Si tienes sugerencias o mejoras, no dudes en abrir un *issue* o enviar un *pull request*.

## 📄 Licencia

Este proyecto está bajo la Licencia MIT - mira el archivo [LICENSE](LICENSE) para más detalles. (Si planeas usar una licencia, crea un archivo `LICENSE` en la raíz del repositorio).

---

**¡Feliz Análisis de Datos!** 📊
