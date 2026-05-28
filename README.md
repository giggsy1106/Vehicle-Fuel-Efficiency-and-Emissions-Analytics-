# 🚗 Vehicle Fuel Efficiency & Emissions Analytics

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=flat&logo=python&logoColor=white)
![PySpark](https://img.shields.io/badge/PySpark-3.x-E25A1C?style=flat&logo=apachespark&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-Dashboard-E97627?style=flat&logo=tableau&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat)

> An end-to-end big data analytics pipeline that uncovers fuel efficiency trends and CO₂ emissions patterns across vehicle classes, fuel types, and manufacturers using EPA datasets — processed with PySpark and visualized through interactive Tableau dashboards.

---

## 📌 Table of Contents

- [Overview](#overview)
- [Key Findings](#key-findings)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Dataset](#dataset)
- [Pipeline Architecture](#pipeline-architecture)
- [Getting Started](#getting-started)
- [Results & Visualizations](#results--visualizations)
- [Future Work](#future-work)
- [Author](#author)

---

## Overview

This project analyzes multi-year EPA vehicle data to answer questions like:

- Which vehicle classes and manufacturers have the best/worst fuel economy?
- How have CO₂ emissions trended over model years?
- What is the relationship between engine displacement, cylinders, and MPG?
- How do fuel types (gasoline, diesel, electric, hybrid) compare on efficiency and emissions?

The pipeline ingests raw EPA CSVs, performs distributed cleaning and aggregation with PySpark, and surfaces insights through a multi-page Tableau dashboard.

---

## Key Findings

| Insight | Detail |
|---|---|
| 🌿 Best MPG class | Compact & subcompact cars average 30+ MPG combined |
| 🏭 Highest emitters | Large SUVs and pickup trucks average 400–550 g CO₂/mile |
| 📉 Emissions trend | Average CO₂ per vehicle dropped ~18% from 2010–2023 |
| ⚡ EV advantage | Electric vehicles produce 0 tailpipe CO₂ vs 350+ g for ICE average |
| 🔧 Displacement impact | Every +1L of displacement correlates with ~4 MPG decrease |

---

## Tech Stack

| Layer | Tools |
|---|---|
| Data Processing | Python 3.9+, PySpark 3.x, Pandas, NumPy |
| Storage | CSV / Parquet (local or S3-compatible) |
| SQL Queries | Spark SQL, HiveQL |
| Visualization | Tableau Desktop / Public |
| Environment | Jupyter Notebook, VS Code |

---

## Project Structure

```
vehicle-emissions-analytics/
│
├── data/
│   ├── raw/                  # Raw EPA CSVs
│   └── processed/            # Cleaned Parquet files
│
├── notebooks/
│   ├── 01_eda.ipynb          # Exploratory data analysis
│   ├── 02_spark_pipeline.ipynb  # PySpark ETL pipeline
│   └── 03_analysis.ipynb     # Aggregations & insights
│
├── src/
│   ├── ingest.py             # Data ingestion & schema validation
│   ├── clean.py              # Null handling, type casting, deduplication
│   ├── transform.py          # Feature engineering & aggregations
│   └── export.py             # Export to Parquet / CSV for Tableau
│
├── dashboards/
│   └── vehicle_emissions.twbx   # Tableau workbook
│
├── requirements.txt
└── README.md
```

---

## Dataset

**Source:** [EPA Fuel Economy Data](https://www.fueleconomy.gov/feg/download.shtml)

| Field | Description |
|---|---|
| `make` / `model` | Manufacturer and model name |
| `year` | Model year (1984–2024) |
| `VClass` | Vehicle class (SUV, Sedan, Pickup, etc.) |
| `fuelType` | Gasoline, Diesel, Electric, Hybrid |
| `city08` / `hwy08` | City / highway MPG |
| `comb08` | Combined MPG |
| `co2` | Tailpipe CO₂ emissions (g/mile) |
| `displ` | Engine displacement (liters) |
| `cylinders` | Number of cylinders |

---

## Pipeline Architecture

```
Raw EPA CSVs
     │
     ▼
 [ingest.py]  ──── Schema validation, type inference
     │
     ▼
 [clean.py]   ──── Null imputation, outlier removal, deduplication
     │
     ▼
[transform.py] ─── Feature engineering (combined MPG, emission bins),
                   Spark SQL aggregations by make/class/year/fuel
     │
     ▼
 [export.py]  ──── Parquet (for Spark) + CSV (for Tableau)
     │
     ▼
  Tableau Dashboard
```

---

## Getting Started

### Prerequisites

```bash
Python 3.9+
Java 8+ (required for PySpark)
Apache Spark 3.x
Tableau Desktop or Tableau Public (free)
```

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/RahulReddyKota/Vehicle-Fuel-Efficiency-and-Emissions-Analytics-.git
cd Vehicle-Fuel-Efficiency-and-Emissions-Analytics-

# 2. Create a virtual environment
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Download EPA data
# Visit https://www.fueleconomy.gov/feg/download.shtml
# Place CSV files in data/raw/
```

### Run the Pipeline

```bash
# Option A — Run notebooks in order
jupyter notebook notebooks/

# Option B — Run scripts directly
python src/ingest.py
python src/clean.py
python src/transform.py
python src/export.py
```

### View Dashboard

Open `dashboards/vehicle_emissions.twbx` in Tableau Desktop or upload to Tableau Public.

---

## Results & Visualizations

The Tableau dashboard includes four views:

1. **MPG by Vehicle Class** — Bar chart comparing combined fuel economy across all vehicle categories
2. **CO₂ Emissions Trend** — Line chart of average emissions per model year (2000–2023)
3. **Fuel Type Comparison** — Side-by-side efficiency and emissions breakdown (Gas vs Diesel vs EV vs Hybrid)
4. **Manufacturer Leaderboard** — Ranked heatmap of top/bottom brands by fleet-average MPG

---

## Future Work

- [ ] Integrate real-time EPA API for live data updates
- [ ] Deploy Spark pipeline on AWS EMR for full-scale processing
- [ ] Add ML regression model to predict MPG from vehicle specs
- [ ] Build an interactive web app with Streamlit or Dash

---

## Author

**Rahul Reddy Kota**
MS Data Science · University of Maryland, Baltimore County (UMBC) · GPA 4.0

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin)](https://www.linkedin.com/in/rahul-reddy-kota-b55a3a251/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=flat&logo=github)](https://github.com/RahulReddyKota)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=flat&logo=gmail)](mailto:kotarahulreddy@gmail.com)

---

*Feel free to ⭐ star this repo if you found it useful!*
