<a id="readme-top"></a>

<!-- SHIELDS -->
[![Python][python-shield]][python-url]
[![Pandas][pandas-shield]][pandas-url]
[![Plotly][plotly-shield]][plotly-url]
[![Jupyter][jupyter-shield]][jupyter-url]

<!-- HEADER -->
<br />
<div align="center">
  <h1>TelecomX LATAM — Churn Analysis</h1>
  <p>
    Análisis exploratorio de datos para identificar los factores clave asociados al abandono de clientes en una empresa de telecomunicaciones.
  </p>
  <p>
    <a href="#sobre-el-proyecto">Ver Proyecto</a>
    ·
    <a href="#hallazgos-principales">Hallazgos</a>
    ·
    <a href="#estructura-del-proyecto">Estructura</a>
  </p>
</div>

---

<!-- TABLA DE CONTENIDOS -->
<details>
  <summary>Tabla de Contenidos</summary>
  <ol>
    <li><a href="#sobre-el-proyecto">Sobre el Proyecto</a></li>
    <li><a href="#construido-con">Construido Con</a></li>
    <li><a href="#estructura-del-proyecto">Estructura del Proyecto</a></li>
    <li><a href="#cómo-empezar">Cómo Empezar</a></li>
    <li><a href="#pipeline-del-análisis">Pipeline del Análisis</a></li>
    <li><a href="#hallazgos-principales">Hallazgos Principales</a></li>
    <li><a href="#recomendaciones">Recomendaciones</a></li>
    <li><a href="#licencia">Licencia</a></li>
    <li><a href="#contacto">Contacto</a></li>
    <li><a href="#agradecimientos">Agradecimientos</a></li>
  </ol>
</details>

---

## Sobre el Proyecto

Este proyecto analiza un dataset de clientes de telecomunicaciones de TelecomX LATAM con el objetivo de entender qué características demográficas, contractuales y de uso están asociadas al **churn** (abandono de clientes).

El análisis sigue un pipeline ETL completo:
- **Extracción** de datos desde una API JSON pública.
- **Transformación** con limpieza, corrección de tipos y feature engineering.
- **Análisis exploratorio** con visualizaciones interactivas.
- **Exportación** de datos limpios para modelado posterior.

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

---

## Construido Con

| Herramienta | Uso |
|-------------|-----|
| **Python 3.x** | Lenguaje principal |
| **Pandas** | Manipulación y limpieza de datos |
| **NumPy** | Operaciones numéricas |
| **Plotly** | Visualizaciones interactivas |
| **Jupyter Notebook** | Entorno de desarrollo |

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

---

## Estructura del Proyecto

```
TelecomX_LATAM/
│
├── TelecomX_LATAM.ipynb      # Notebook principal con el análisis completo
├── telecomx_clean.csv         # Dataset limpio exportado
└── README.md                  # Este archivo
```

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

---

## Cómo Empezar

### Prerrequisitos

- Python 3.8+
- pip

### Instalación

1. Clonar el repositorio:
   ```sh
   git clone https://github.com/tu_usuario/TelecomX_LATAM.git
   cd TelecomX_LATAM
   ```

2. Instalar dependencias:
   ```sh
   pip install pandas numpy plotly jupyter
   ```

3. Ejecutar el notebook:
   ```sh
   jupyter notebook TelecomX_LATAM.ipynb
   ```

> **Nota:** Los datos se descargan automáticamente desde la API pública al ejecutar la primera celda del notebook.

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

---

## Pipeline del Análisis

### 📥 1. Extracción
Datos consumidos desde una API JSON pública. Las estructuras anidadas se normalizan con `pd.json_normalize`.

### 🔧 2. Transformación
- Corrección de tipos (`Charges_Total` a numérico).
- Limpieza de espacios en columnas de texto.
- Creación de `Daily_Charges` (cargos mensuales / 30).
- Codificación de `Churn` a binario (0/1).
- Eliminación de nulos y duplicados.

### 📊 3. Análisis Exploratorio

| Análisis | Variables | Visualización |
|----------|-----------|---------------|
| Distribución de churn | `Churn` | Dona + Treemap |
| Categóricas vs churn | `Contract`, `PaymentMethod`, `InternetService`, `gender`, `PaperlessBilling`, `SeniorCitizen` | Barras agrupadas |
| Numéricas vs churn | `tenure`, `Charges_Monthly`, `Charges_Total`, `Daily_Charges` | Box plots |

### 💾 4. Exportación
Dataset limpio exportado a `telecomx_clean.csv` para modelado predictivo.

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

---

## Hallazgos Principales

| Factor | Observación |
|--------|-------------|
| **Tipo de contrato** | Mes a mes tiene la mayor tasa de abandono |
| **Método de pago** | Cheque electrónico se asocia con más churn |
| **Internet** | Fibra óptica presenta mayor abandono |
| **Antigüedad** | Menor antigüedad = mayor riesgo |
| **Cargos mensuales** | Cargos más altos se asocian con churn |
| **Género** | Sin impacto significativo |
| **Facturación sin papel** | Abandono ligeramente mayor |
| **Tercera edad** | Tendencia moderada al abandono |

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

---

## Recomendaciones

1. **Incentivar contratos a largo plazo** — Descuentos o beneficios para migrar clientes de mes a mes.
2. **Revisar precios de fibra óptica** — Evaluar si el abandono responde a precio, calidad o competencia.
3. **Retención temprana** — Programas de bienvenida y seguimiento en los primeros meses.
4. **Atención a usuarios de cheque electrónico** — Campañas de retención dirigidas.
5. **Revisar cuentas con cargos altos** — Contacto proactivo para asegurar percepción de valor.

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

---

## Licencia

Distribuido bajo la licencia MIT. Consultar `LICENSE` para más información.

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

---

## Contacto

Andrés Muñoz — [tecnologiainovamm@gmail.cm](mailto:tecnologiainovamm@gmail.com)

Link del Proyecto: [https://github.com/psychedelic-art/telecom-x](https://github.com/psychedelic-art/telecom-x/blob/main/TelecomX_LATAM.ipynb)

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

---

## Agradecimientos

- [Alura LATAM](https://www.aluracursos.com/) — Challenge de Data Science
- [Best-README-Template](https://github.com/othneildrew/Best-README-Template) — Estructura del README
- [Plotly](https://plotly.com/python/) — Visualizaciones interactivas

<p align="right">(<a href="#readme-top">volver arriba</a>)</p>

---

<!-- LINKS & SHIELDS -->
[python-shield]: https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white
[python-url]: https://python.org
[pandas-shield]: https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white
[pandas-url]: https://pandas.pydata.org
[plotly-shield]: https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white
[plotly-url]: https://plotly.com
[jupyter-shield]: https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white
[jupyter-url]: https://jupyter.org
