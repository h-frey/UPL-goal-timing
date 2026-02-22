# UPL Goal Data Analysis Project

## Project Overview

This portfolio project analyzes goal-scoring patterns in the Uganda Premier League (UPL) across 6 seasons (2019/20–2024/25). The analysis reveals critical timing windows when teams are most vulnerable to conceding goals, with insights for coaches, analysts, and sports data enthusiasts.

**Pipeline:**
1. **Data Scraping** (`notebooks/01_scraping.py`): Web scraping UPL match data from official website
2. **Data Cleaning** (`notebooks/02_cleaning.ipynb`): Consolidating, standardizing, and engineering features
3. **Analysis & Visualization** (`notebooks/03_analysis.ipynb`): Key metrics, timing patterns, and insights

## Project Structure

```
upl-goal-timing/
├── README.md                      <- This file
├── LICENSE                        <- Open-source license
├── requirements.txt               <- Python dependencies
│
├── data/
│   ├── raw/                       <- Original season CSVs (gitignored)
│   │   ├── upl_goals_2019_20.csv
│   │   ├── upl_goals_2020_21.csv
│   │   └── ...
│   └── processed/                 <- Cleaned & final datasets (gitignored)
│       ├── upl_goals_2019_2025_cleaned.csv
│       └── upl_goals_2019_2025_final.csv
│
├── notebooks/
│   ├── 01_scraping.py             <- Web scraping script (standalone)
│   ├── 02_cleaning.ipynb          <- Data cleaning & feature engineering
│   └── 03_analysis.ipynb          <- Full analysis & key visualization
│
└── outputs/
    └── goal_timing_upl.png        <- Final polished visualization
```

## How to Use

### 1. Installation

```bash
# Clone the repository
git clone https://github.com/h-frey/upl-goal-timing.git
cd upl-goal-timing

# Create a Python virtual environment
python -m venv .venv
.venv\Scripts\activate  # Windows
# source .venv/bin/activate  # macOS/Linux

# Install dependencies
pip install -r requirements.txt
```

### 2. Run the Pipeline

**Option A: Run notebooks in Jupyter**
```bash
jupyter lab
```
Then execute in order:
1. `notebooks/01_scraping.py` — Fetch fresh data from UPL website
2. `notebooks/02_cleaning.ipynb` — Clean & feature-engineer the data
3. `notebooks/03_analysis.ipynb` — Generate insights & visualization

**Option B: Run scraper script only (if data already exists)**
```bash
python notebooks/01_scraping.py
```

### 3. Output

After running the pipeline:
- **Cleaned data**: `data/processed/upl_goals_2019_2025_cleaned.csv`
- **Analysis output**: `outputs/goal_timing_upl.png` (key visualization)

## Key Metrics & Features

The analysis includes calculation of:
- **GQR** (Goal Quality Ratio): % of open-play goals
- **GTSI** (Goal Timing Shift Index): Ratio of late goals (76-90') vs early (16-30')
- **DIS** (Decisive Impact Score): Goal importance based on time & match state
- **OVW** (Opponent Vulnerability Window): When teams concede most goals
- **DDI** (Discipline Degradation Index): Penalty/own-goal ratio 2nd half vs 1st half

## Main Finding

**The most dangerous 15 minutes in UPL football is 46–60 (right after halftime)**, with 517 goals (17.9% of total). This differs from European leagues, which peak at 76–90' due to late-game fatigue. The UPL's second-half kickoff restart is a critical defensive moment.

## Dependencies

Required packages (see `requirements.txt`):
- `pandas` – Data manipulation
- `matplotlib` – Visualization
- `numpy` – Numerical computing
- `seaborn` – Statistical plots
- `scipy` – Scientific computing
- `plotly` – Interactive charts
- `jupyter` – Notebook environment

## Author & Audience

- **Portfolio project** for graduate school applications
- **Target audience**: Growth-focused football data teams, FUFA stakeholders
- **Format**: Jupyter notebooks + standalone scraper for clarity & reproducibility

