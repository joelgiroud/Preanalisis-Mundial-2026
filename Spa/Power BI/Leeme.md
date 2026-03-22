\# 🏆 Simulando el Mundial FIFA 2026

\### Portafolio de Análisis de Datos | Power BI · DAX · HTML Content



\---



\## 📋 Descripción



Dashboard interactivo de 5 páginas que visualiza el análisis completo del Mundial FIFA 2026

— desde la distribución de sedes hasta los resultados de la simulación Monte Carlo —

con una capa de diseño avanzado construida en \*\*HTML Content lite\*\* directamente dentro de Power BI.



El dashboard consume los datos procesados por el proyecto R hermano (`mundial\_2026/`)

y los presenta en un entorno oscuro, responsivo y con jerarquía visual clara.



\---



\## 🗂️ Estructura del proyecto



Power BI/

├── main.pbix # Dashboard principal (con HTML Content)

├── main (no html).pbix # Versión de respaldo sin HTML (nativa)

├── tema\_mundial2026.json # Tema personalizado Power BI

├── style\_notes.md # Guía de decisiones de diseño

└── README.md # Este archivo



Los datasets se consumen desde `../datasets/` y los CSVs procesados

desde `../mundial\_2026/data/` y `../mundial\_2026/output/`.



\---



\## 📄 Páginas del dashboard



| # | Página | Descripción |

|---|--------|-------------|

| 1 | \*\*Portada\*\* | 5 KPI cards — partidos, sedes, selecciones, grupos y días al inicio |

| 2 | \*\*Sedes y Calendario\*\* | Mapa interactivo · Panel 3 países · Partidos por estadio · Tabla de fixtures |

| 3 | \*\*Selecciones\*\* | Rankings FIFA · Top goleadores · Top porteros · Rachas históricas |

| 4 | \*\*Simulación Monte Carlo\*\* | Top 15 favoritos · Probabilidades por selección · Métricas México |

| 5 | \*\*Historia del Mundial\*\* | Títulos históricos · Finales · Curiosidades 1930–2022 |



\---



\## 🎨 Diseño



El dashboard implementa una \*\*capa HTML\*\* sobre los visuales nativos usando

\[HTML Content (lite)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA200001930):



Fondo principal → #0D1117 (negro grafito)

Acento primario → #C8102E (rojo FIFA)

Acento México → #006341 (verde bandera)

Texto principal → #E2E8F0 (blanco suave)

Texto secundario → #A0AEC0 (gris claro)

Valores dorados → #F4D03F (amarillo oro)





\---



\## 📦 Datasets conectados



| Dataset | Origen | Descripción |

|---------|--------|-------------|

| `mundial\_2026\_full.csv` | Generado en R | 104 partidos con equipos, sedes y rankings |

| `sim\_prob\_campeon.csv` | Generado en R | Probabilidades de título (Monte Carlo 10k) |

| `sim\_prob\_final.csv` | Generado en R | Probabilidades de llegar a la Final |

| `dim\_titulos\_historicos.csv` | Generado en R | Campeones mundiales 1930–2022 |

| `dim\_rachas\_victorias.csv` | Generado en R | Rachas y ratios históricos por selección |

| `dim\_curiosidades\_mundial.csv` | Generado en R | 14 datos históricos del torneo |

| `dim\_leyendas.csv` | Generado en R | Top 5 goleadores y porteros históricos |

| `fifa\_rankings\_clean.csv` | Kaggle + FIFA | Rankings FIFA enero 2026 |



\---



\## 📊 Resultados principales (P4 — Monte Carlo)



| Selección | P(Campeón) | P(Final) |

|-----------|-----------|---------|

| 🇪🇸 España | 6.61% | 11.10% |

| 🇦🇷 Argentina | 6.18% | 10.80% |

| 🇫🇷 Francia | 5.94% | 10.54% |

| 🇲🇽 \*\*México\*\* | \*\*3.63%\*\* | \*\*7.39%\*\* |



> México ocupa el puesto #11 global con un boost de +8% por ventaja de sede local.



\---



\## 🔧 Medidas DAX destacadas



```dax

\-- KPI dinámico: días al inicio del torneo

Días al Mundial =

VAR hoy = TODAY()

VAR inicio = DATE(2026, 6, 11)

RETURN IF(hoy < inicio, inicio - hoy, 0)



\-- Flag sede México para condicional de color

Is\_Mexico\_Sede =

IF(SELECTEDVALUE(data\[country]) = "Mexico", 1, 0)



\-- Probabilidad campeón formateada

Prob\_Campeon\_Label =

FORMAT(\[prob\_title] / 100, "0.00%")



\## ▶️ ¿Cómo abrirlo?

1\. Clona el repositorio completo (R + Power BI comparten ../datasets/)

2\. Ejecuta main.Rmd en el proyecto R para regenerar los CSVs procesados

3\. Abre Power BI/main.pbix en Power BI Desktop (≥ marzo 2025)

4\. Instala HTML Content (lite) desde AppSource si no lo tienes

5\. Actualiza las rutas de datos si tu directorio difiere

6\. Refresca: Ctrl + Alt + F5



Versiones: Power BI Desktop ≥ marzo 2025 · HTML Content lite ≥ 2.1



👤 Autor


Joel B. Perez Giroud G · LinkedIn · GitHub
Proyecto desarrollado como portafolio de análisis de datos · Marzo 2026

