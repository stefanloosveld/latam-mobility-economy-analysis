# Movilidad urbana y productividad económica en ciudades de Latinoamérica
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/stefanloosveld/latam-mobility-economy-analysis/blob/main/latam_mobility_economy_analysis.ipynb)

Análisis de cómo se relaciona la congestión vehicular con la productividad económica en 15 ciudades latinoamericanas, para identificar dónde conviene invertir en infraestructura de transporte.

## Objetivo

Evaluar si las ciudades con mayor PIB per cápita presentan más o menos congestión, y priorizar ciudades para inversión en transporte combinando indicadores de tráfico y economía.

## Datos

- **TomTom Traffic Index:** más de 1 millón de registros de tráfico (retraso por congestión, índice de tráfico, tiempos de viaje por cada 10 km).
- **OECD Cities:** PIB per cápita, desempleo, calidad del aire (PM2.5) y población por ciudad.
- **Cobertura:** año 2024, 15 ciudades de 7 países (México, Brasil, Colombia, Perú, Chile, Argentina y Uruguay).

> Los datasets originales no se incluyen en el repositorio.

## Herramientas

Python · pandas · NumPy · Matplotlib · Seaborn · Jupyter Notebook

## Proceso

1. **Exploración:** revisión de estructura, tipos de datos y valores ausentes.
2. **Limpieza:** nombres de columnas en `snake_case`, conversión de fechas a `datetime` y limpieza de formatos numéricos (separadores de miles, comas decimales y símbolo `%`).
3. **Preparación:** filtrado del año 2024 y cálculo de promedios de tráfico por ciudad.
4. **Integración:** unión de tráfico y economía con un `inner join` por ciudad y año.
5. **Visualización:** boxplot de congestión, histograma de PIB per cápita y gráfico de barras comparativo.

## Hallazgos principales

- **No hay una relación clara entre congestión y PIB per cápita** (correlación de 0.28).
- **La congestión está muy concentrada:** el retraso promedio (629.52) es mucho mayor que la mediana (263), y Ciudad de México (2,833) es un valor atípico.
- **El tamaño de la ciudad influye:** el retraso por congestión es un total acumulado, por lo que favorece a las ciudades grandes. Montevideo tiene el PIB per cápita más alto y casi no presenta congestión.
- **Calidad de datos:** el PIB per cápita de Santiago (2,277) está muy por debajo del resto y conviene validarlo con la fuente.

## Recomendación

**Bogotá es la ciudad prioritaria** para invertir en infraestructura de transporte: es la tercera más congestionada, tiene un PIB per cápita por debajo del promedio (11,442 frente a 13,254) y el desempleo más alto (10%) entre las cuatro ciudades más congestionadas.

*Con 15 ciudades y un año de datos, los resultados son orientativos y no prueban causalidad.*

## Archivos

## Cómo abrirlo en Colab

Haz clic en el botón **Open in Colab** al inicio de este README. El notebook se abrirá en Google Colab, donde puedes ver el código, las tablas y los gráficos.

## Estructura del repositorio

```
latam-mobility-economy-analysis/
├── README.md                                ← descripción del proyecto
└── latam_mobility_economy_analysis.ipynb    ← notebook con el análisis completo
```
---

Proyecto realizado como parte del bootcamp de Análisis de Datos de TripleTen.
