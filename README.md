# Citi-Bike-
DIS Stockholm Spring 2026 Machine Learning Project 

## Overview

This project is a regression problem. We predict the duration of a Citi Bike trip
in minutes using features available at the time a ride starts: time of day, day of
week, rider type, bike type, start/end coordinates, and straight-line route distance.

**Target variable:** `trip_duration_minutes` — derived from `ended_at - started_at`

## Dataset

We use the official Citi Bike trip history data for May 2025, publicly available at:
https://citibikenyc.com/system-data

The combined dataset contains approximately 4.3 million trip records across 12 columns.

> **Note:** The raw CSV files are not included in this repository due to file size.
> Download the May 2025 trip history files from the link above and place the combined
> CSV at the project root as `202505-citibike-tripdata.csv` before running the notebook.

## Repository Structure
├── notebook.ipynb               # Main Jupyter notebook
├── requirements.txt             # Python dependencies
├── README.md
└── .gitignore

## Setup

1. Clone the repository
```bash
   git clone https://github.com/Wiz1702/Citi-Bike-.git
   cd Citi-Bike-
```

2. Create and activate a virtual environment
```bash
   python -m venv venv
   source venv/bin/activate        # Mac/Linux
   venv\Scripts\activate           # Windows
```

3. Install dependencies
```bash
   pip install -r requirements.txt
```

4. Download the dataset from https://citibikenyc.com/system-data and place it at
   the project root as `202505-citibike-tripdata.csv`

5. Launch Jupyter and open `notebook.ipynb`
```bash
   jupyter notebook
```

## Approach

- **Baseline:** Mean/median duration predictor
- **Linear model:** Ridge regression with temporal and spatial features
- **Tree-based model:** Random Forest and/or XGBoost with full feature set

Features include cyclical time encoding (sine/cosine for hour and day of week),
haversine straight-line distance between start and end coordinates, rider type,
and bike type.

## Evaluation Metrics

| Metric | Description |
|--------|-------------|
| MAE    | Mean absolute error in minutes |
| RMSE   | Root mean squared error in minutes |
| R²     | Proportion of variance explained |

## Team

Wisdom Akanwe - Kenyon College
Danna Duarte - Princeton University


## License

MIT
