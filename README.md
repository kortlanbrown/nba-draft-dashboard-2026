# 2026 NBA Draft Predictions Dashboard

An interactive, data-driven dashboard projecting rookie year, career average, and peak season stats for the top prospects in the 2026 NBA Draft.

Built using a machine learning model trained on 141 top-14 draft picks from 2004–2021, using college advanced metrics to predict five core NBA box score stats.

---

## Live Dashboard

**[View the dashboard →](https://kortlanbrown.github.io/nba-draft-dashboard-2026)**

---

## What The Model Does

The model takes in a prospect's final college season advanced stats and outputs three sets of NBA predictions:

- **Rookie year** — what to expect in their first NBA season
- **Career average** — what kind of player they become over their full career
- **Peak season** — the best single season they are projected to reach

### The 5 Predicted Stats
- Points Per Game (PPG)
- Assists Per Game (APG)
- Rebounds Per Game (RPG)
- Blocks Per Game (BPG)
- Steals Per Game (SPG)

---

## How It Was Built

### Training Data
- **141 players** — top 14 picks from NBA drafts 2004–2021
- College players only (international players excluded due to league translation complexity)
- Minimum 20 games played filter applied to both college and rookie seasons
- Sources: Kaggle NBA stats datasets, Barttorvik college advanced stats

### Model Inputs (College Advanced Stats)
| Category | Features |
|---|---|
| Scoring efficiency | TS%, eFG%, FT%, FT rate, 3P%, 2P% |
| Playmaking | AST%, AST/TO ratio, TOV% |
| Rebounding | ORB%, DRB% |
| Defense | STL%, BLK%, DBPM |
| Overall | BPM, OBPM, Usage rate, Offensive rating |
| Context | Draft pick number, games played |

### Model Type
Gradient Boosting Regressor (scikit-learn) — 5 separate models per time period = 15 models total

### Model Accuracy (Cross-Validated MAE)
| Stat | Rookie | Career | Peak |
|---|---|---|---|
| PPG | ±3.5 | ±4.4 | ±5.4 |
| APG | ±0.9 | ±1.1 | ±1.3 |
| RPG | ±1.4 | ±1.2 | ±1.5 |
| BPG | ±0.2 | ±0.2 | ±0.2 |
| SPG | ±0.3 | ±0.2 | ±0.3 |

---

## 2026 Prospects Included

| Pick | Player | School | Conference |
|---|---|---|---|
| 1 | AJ Dybantsa | BYU | Big 12 |
| 2 | Darryn Peterson | Kansas | Big 12 |
| 3 | Cameron Boozer | Duke | ACC |
| 4 | Caleb Wilson | North Carolina | ACC |
| 5 | Darius Acuff Jr | Arkansas | SEC |
| 6 | Kingston Flemings | Houston | Big 12 |
| 7 | Keaton Wagler | Illinois | Big Ten |
| 8 | Mikel Brown Jr | Louisville | ACC |
| 9 | Nate Ament | Tennessee | SEC |
| 11 | Koa Peat | Arizona | Big 12 |
| 12 | Thomas Haugh | Florida | SEC |
| 13 | Yaxel Lendenborg | Michigan | Big Ten |
| 14 | Braylon Mullins | UConn | Big East |
| 18 | Chris Cenac | Houston | Big 12 |
| 19 | Labaron Philon | Alabama | SEC |

---

## Important Disclaimers

- Predictions are probabilistic, not guarantees
- The model cannot account for injuries, coaching systems, team fit, or player development work ethic
- Generational outliers (think Luka Dončić, LeBron James) will always exceed model projections — that is a feature of statistics, not a flaw in the model
- Uncertainty flags are shown for players with limited college sample sizes or unusual statistical profiles
- Draft pick projections used are based on mock drafts as of March 2026 — actual draft order will affect predictions

---

## Tech Stack

- **Python** — data collection, cleaning, modeling
- **pandas / numpy** — data manipulation
- **scikit-learn** — Gradient Boosting models, cross-validation, imputation
- **Kaggle datasets** — NBA historical stats, draft history
- **Barttorvik** — 2026 prospect college advanced stats
- **Chart.js** — dashboard visualization
- **GitHub Pages** — hosting

---

## Follow Along

This dashboard will be updated after March Madness with final season stats for all prospects, and again after the draft lottery with official pick positions.

Follow for more data-driven NBA content.

---

*Model trained March 2026. Prospect stats current as of March 17, 2026.*
