# Trazabilidad de datos y selección de la muestra

## Propósito

Este archivo hace auditable la selección del proyecto. La unidad analizada es una **muestra analítica intencional de 16 juegos de plataformas**, no un censo de toda la serie Super Mario ni de todos los resultados que devuelve un buscador.

## Sobre la cifra de 263 resultados

La cifra de 263 fue una captura de la búsqueda amplia original en VGChartz con la consulta `super mario`. Esa interfaz es dinámica: cambia con nuevas publicaciones, aliases y filtros, y el archivo fuente de 263 filas no fue preservado por el equipo. Por rigor, la cifra **no se usa en cálculos, gráficos ni modelo** y no debe presentarse como una base cruda reproducible. En la sustentación se recomienda decir: “partimos de una búsqueda amplia; el universo final se definió con criterios explícitos y está documentado en el registro de selección”.

## Criterios de inclusión

1. Juego de plataformas asociado a Super Mario.
2. Un solo lanzamiento por obra (se excluyen ports, remakes y compilaciones para evitar doble conteo de ventas o crítica).
3. Año, plataforma y ventas reportadas disponibles en el conjunto curado.
4. Los scores anteriores a Metacritic se conservan como contexto, pero se separan mediante `Metascore_valido=False`.

## Criterios de exclusión

- Spin-offs de carreras, party, deportes, RPG u otros géneros.
- Juegos centrados en creación de niveles.
- Ports, remakes, reediciones y compilaciones de obras que ya están representadas.
- Títulos fuera del alcance histórico que decidió el equipo; estos se registran explícitamente y no se ocultan.

## Archivos de evidencia

- `registro_seleccion_y_trazabilidad.csv`: 16 inclusiones y ejemplos representativos de exclusión, con una justificación por fila.
- `super_mario_datos_limpios.csv`: datos finales usados por el análisis.
- `Super_Mario_Analisis_Final.ipynb`: validaciones y cálculos reproducibles.

## Fuentes por variable

| Variable | Fuente | Uso y limitación |
|---|---|---|
| Juego, año, plataforma y delimitación de serie | [Super Mario Wiki](https://www.mariowiki.com/Super_Mario_(series)) | Referencia de alcance; se contrasta con el criterio definido por el equipo. |
| Score crítico | [Metacritic](https://www.metacritic.com/pictures/every-nintendo-franchise-ranked-worst-to-best/44/) | El artículo identifica con asterisco los scores históricos de GameRankings; esos cuatro valores no entran a correlación ni modelo. |
| Ventas reportadas | [VGChartz](https://www.vgchartz.com/gamedb/?name=super+mario) | Fuente pública de cifras reportadas; no equivale a una fuente oficial de Nintendo y debe interpretarse con cautela. |

Fecha de consulta y consolidación: 2026-09-13.
