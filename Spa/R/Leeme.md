# 🏆 Simulando el Mundial FIFA 2026
### Portafolio de Análisis de Datos | R · ggplot2 · Monte Carlo

---

## 📋 Descripción

Proyecto de análisis de datos que responde 3 preguntas sobre el Mundial FIFA 2026
mediante exploración descriptiva, modelado predictivo y visualización:

1. ¿Cómo se distribuyen los 104 partidos entre las 16 sedes?
2. ¿Qué selección tiene mayor probabilidad de ser campeona?
3. ¿Cuánto impacta la sede local en las probabilidades de México?

---

## 🗂️ Estructura del proyecto

```
mundial_2026/
├── data/               # Datos procesados (generados por el script)
├── output/             # Gráficas y reportes exportados
├── main.Rmd            # Script principal (reproducible)
└── README.md           # Este archivo
```

Los datasets **raw** se almacenan en `../datasets/` (no incluidos dentro del repositorio R).

---

## 📦 Datasets utilizados

| Dataset | Fuente | Link |
|---------|--------|------|
| FIFA WC 2026 Match Data | Kaggle | [Ver dataset](https://www.kaggle.com/datasets/areezvisram12/fifa-world-cup-2026-match-data-unofficial) |
| FIFA Rankings (ene 2026) | FIFA oficial | [Ver ranking](https://inside.fifa.com/fifa-world-ranking/men) |
| FIFA WC All Dataset | Gigasheet | [Ver dataset](https://www.gigasheet.com/sample-data/fifa-world-cup-all-dataset) |

---

## 🔬 Metodología

- **Validación de datos:** `pointblank` (completitud, validez, unicidad)
- **Modelo predictivo:** Función logística sobre diferencia de puntos FIFA
- **Simulación:** Monte Carlo · 10,000 torneos · `set.seed(2026)`
- **Distribución de goles:** Poisson con media proporcional a fuerza del equipo

---

## 📊 Resultados principales

| Selección | P(Campeón) | P(Final) |
|-----------|-----------|---------|
| 🇪🇸 España | 6.61% | 11.10% |
| 🇦🇷 Argentina | 6.18% | 10.80% |
| 🇫🇷 Francia | 5.94% | 10.54% |
| 🇲🇽 **México** | **3.63%** | **7.39%** |

---

## ▶️ ¿Cómo reproducirlo?

```r
# 1. Clona el repositorio
# 2. Descarga los datasets en ../datasets/
# 3. Abre mundial_2026/R.Rproj en RStudio
# 4. Abre main.Rmd y ejecuta: rmarkdown::render("main.Rmd")
```

**Versiones:** R ≥ 4.3 · tidyverse 2.0 · pointblank 0.12 · ggplot2 3.5

---

## 👤 Autor

** Joel B. Perez Giroud G** · [LinkedIn](in/joel-pgiroud/) · [GitHub](/joelgiroud)

*Proyecto desarrollado como portafolio de análisis de datos · Marzo 2026*
