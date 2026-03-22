\# 🏆 Simulating FIFA World Cup 2026

\### Data Analysis Portfolio | Power BI · DAX · HTML Content



\---



\## 📋 Description



An interactive 5-page dashboard that visualizes the complete FIFA World Cup 2026 analysis

— from venue distribution to Monte Carlo simulation results —

with an advanced design layer built using \*\*HTML Content lite\*\* directly inside Power BI.



This dashboard consumes data from its sibling R project (`mundial\_2026/`)

and presents it in a dark, responsive, and visually structured environment.



\---



\## 🗂️ Project Structure





Power BI/

├── main.pbix # Main dashboard (HTML-powered)

├── main (no html).pbix # Native version without HTML

├── tema\_mundial2026.json # Power BI custom theme

├── style\_notes.md # Design decisions guide

└── README.md # This file





Datasets are consumed from `../datasets/` and processed CSVs from

`../mundial\_2026/data/` and `../mundial\_2026/output/`.



\---



\## 📄 Dashboard Pages



| # | Page | Description |

|---|------|-------------|

| 1 | \*\*Cover\*\* | 5 KPI cards — matches, venues, teams, groups and days until kickoff |

| 2 | \*\*Venues \& Schedule\*\* | Interactive map · 3-country panel · Matches per stadium · Fixtures table |

| 3 | \*\*Teams\*\* | FIFA Rankings · Top 5 scorers and goalkeepers · Historical records |

| 4 | \*\*Monte Carlo Simulation\*\* | Top 15 favorites · Probability per team · Mexico metrics |

| 5 | \*\*World Cup History\*\* | Historical championships · Finals · Curiosities 1930–2022 |



\---



\## 🎨 Design



This dashboard implements an \*\*HTML layer\*\* over native visuals using

\[HTML Content (lite)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA200001930):



Main background → #0D1117 (graphite black)

Primary accent → #C8102E (FIFA red)

Mexico accent → #006341 (flag green)

Main text → #E2E8F0 (soft white)

Secondary text → #A0AEC0 (light gray)

Golden values → #F4D03F (golden yellow)





\---



\## 📦 Connected Datasets



| Dataset | Source | Description |

|---------|--------|-------------|

| `mundial\_2026\_full.csv` | Generated in R | 104 matches with teams, venues and rankings |

| `sim\_prob\_campeon.csv` | Generated in R | Championship probability (Monte Carlo 10k) |

| `sim\_prob\_final.csv` | Generated in R | Probability of reaching the Final |

| `dim\_titulos\_historicos.csv` | Generated in R | World champions 1930–2022 |

| `dim\_rachas\_victorias.csv` | Generated in R | Historical win streaks and ratios per team |

| `dim\_curiosidades\_mundial.csv` | Generated in R | 14 historical tournament facts |

| `dim\_leyendas.csv` | Generated in R | Top 5 all-time scorers and goalkeepers |

| `fifa\_rankings\_clean.csv` | Kaggle + FIFA | FIFA Rankings January 2026 |



\---



\## 📊 Key Results (P4 — Monte Carlo)



| Team | P(Champion) | P(Finalist) |

|------|-------------|-------------|

| 🇪🇸 Spain | 6.61% | 11.10% |

| 🇦🇷 Argentina | 6.18% | 10.80% |

| 🇫🇷 France | 5.94% | 10.54% |

| 🇲🇽 \*\*Mexico\*\* | \*\*3.63%\*\* | \*\*7.39%\*\* |



> Mexico ranks 11th overall, with a +8% boost from home-ground advantage.



\---



\## 🔧 Key DAX Measures



```dax

\-- Dynamic KPI: days until tournament begins

Días al Mundial =

VAR hoy = TODAY()

VAR inicio = DATE(2026, 6, 11)

RETURN IF(hoy < inicio, inicio - hoy, 0)



\-- Mexico host flag for conditional color

Is\_Mexico\_Sede =

IF(SELECTEDVALUE(data\[country]) = "Mexico", 1, 0)



\-- Formatted champion probability

Prob\_Campeon\_Label =

FORMAT(\[prob\_title] / 100, "0.00%")


---

## ▶️ How to Reproduce


1. Clone the full repository (R + Power BI share ../datasets/)

2\. Run main.Rmd in the R project to regenerate the processed CSVs

3\. Open Power BI/main.pbix in Power BI Desktop (≥ March 2025)

4\. Install HTML Content (lite) from AppSource if you don't have it

5\. Update data source paths if your directory differs

6\. Refresh: Ctrl + Alt + F5




Versions: Power BI Desktop ≥ March 2025 · HTML Content lite ≥ 2.1


👤 Author


Joel B. Perez Giroud G · LinkedIn · GitHub
Project developed as a data analytics portfolio · March 2026

