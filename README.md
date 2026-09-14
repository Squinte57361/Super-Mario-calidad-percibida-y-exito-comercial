# Super Mario: calidad percibida y éxito comercial

Proyecto final de Ciencia de Datos para DataXperience. Analiza una **muestra analítica intencional de 16 juegos de plataformas de Super Mario (1985–2023)** para explorar la relación entre la valoración crítica y las ventas reportadas.

## Pregunta de investigación

¿Cómo se relacionan la calidad percibida —crítica y usuarios— y el éxito comercial de los juegos seleccionados de Super Mario?

## Hallazgo principal

La relación lineal entre Metascore válido y ventas es prácticamente nula (`r = -0.008`). Se compararon Regresión Lineal y Ridge con validación Leave-One-Out; ninguno superó la referencia que predice la media de ventas. El resultado es descriptivo, exploratorio y **no causal**.

## Estructura del repositorio

| Archivo | Contenido |
|---|---|
| `Informe_Final_Super_Mario.docx` | Informe técnico: problema, datos, limpieza, EDA, estadística, modelos, evaluación, conclusiones y código explicado. |
| `Presentación Final Super Mario DataXperience.pdf` | Versión lista para visualizar o proyectar. |
| `Super_Mario_Analisis_Final.ipynb` | Cuaderno reproducible para Google Colab/Jupyter con código completo. |
| `super_mario_datos_limpios.csv` | Datos analíticos usados por el cuaderno. |
| `registro_seleccion_y_trazabilidad.csv` | Registro de decisiones de inclusión y exclusión. |
| `TRAZABILIDAD_DATOS.md` | Fuentes, criterios de selección y límites metodológicos. |

## Cómo visualizar los archivos

- GitHub muestra directamente `README.md`, `TRAZABILIDAD_DATOS.md` y los archivos CSV.
- El PDF de la presentación se puede abrir o descargar desde GitHub.
- Para el informe Word y la presentación editable, use **Download raw file** o descárguelos con el botón de descarga del repositorio.
- El cuaderno `.ipynb` puede abrirse en GitHub para lectura o cargarse en Google Colab para ejecutarlo.

## Cómo ejecutar el cuaderno en Google Colab

1. Descargue desde este repositorio estos tres archivos: `Super_Mario_Analisis_Final.ipynb`, `super_mario_datos_limpios.csv` y `registro_seleccion_y_trazabilidad.csv`.
2. Abra el archivo `.ipynb` en [Google Colab](https://colab.research.google.com/) mediante **Archivo → Subir cuaderno**.
3. En el panel de archivos de Colab, cargue **los dos CSV**: `super_mario_datos_limpios.csv` y `registro_seleccion_y_trazabilidad.csv`.
4. Seleccione **Entorno de ejecución → Ejecutar todo**.
5. Las celdas producirán las validaciones, tablas, gráficos, comparación de modelos y conclusiones.

Para ejecución local:

```bash
pip install pandas numpy matplotlib scikit-learn jupyter
jupyter notebook Super_Mario_Analisis_Final.ipynb
```

## Modelos comparados

Se comparan Regresión Lineal (OLS) y Ridge con el mismo esquema de validación Leave-One-Out. Ridge aplica regularización L2; OLS se conserva como modelo principal por ser más interpretable y porque Ridge no obtiene una mejora práctica. La referencia de media confirma que el Metascore, por sí solo, no aporta capacidad útil de predicción de ventas en esta muestra.

## Fuentes y limitaciones

Los scores críticos proceden de Metacritic, las ventas reportadas de VGChartz y el alcance de la serie se apoyó en Super Mario Wiki. Los títulos antiguos con score de GameRankings se conservan como contexto, pero se excluyen de los cálculos que requieren Metascore directamente comparable.

La muestra no es un censo completo de toda la franquicia. Consulte `TRAZABILIDAD_DATOS.md` y `registro_seleccion_y_trazabilidad.csv` para revisar las decisiones de selección y sus límites.

**Integrantes:** Santiago Bautista · Samuel Quintero · Heidy Maldonado · Kevin Perdomo
