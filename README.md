# Weather and Air Quality ETL Pipeline

<p align="center">
  <img src="ETL.png" alt="Weather and Air Quality ETL Pipeline" width="920">
</p>

<p align="center">
  A clean ETL pipeline that extracts weather and air-quality data, transforms it into analysis-ready tables, and loads it into PostgreSQL.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.7%2B-3776AB?logo=python&logoColor=white" alt="Python 3.7+">
  <img src="https://img.shields.io/badge/PostgreSQL-Database-316192?logo=postgresql&logoColor=white" alt="PostgreSQL">
  <img src="https://img.shields.io/badge/ETL-Data%20Pipeline-0F766E" alt="ETL Pipeline">
</p>

## Overview

This project demonstrates an end-to-end ETL pipeline for combining weather data and air-quality measurements for a selected city and time range. The pipeline collects data from external APIs, normalizes and cleans it, and stores the results in PostgreSQL for downstream analysis.

## What It Does

- Extracts weather data from Visual Crossing.
- Extracts air-quality data from AirVisual.
- Cleans, standardizes, and merges the datasets.
- Loads the transformed data into PostgreSQL tables.
- Supports exploratory analysis in a Jupyter notebook.

## Project Highlights

- Modular Python code in `src/` for extraction, transformation, and loading.
- SQL schema ready for PostgreSQL setup.
- Notebook-based analysis workflow for quick insight generation.
- Shell script to run the pipeline end to end.

## Tech Stack

- Python
- PostgreSQL
- pandas
- SQLAlchemy
- requests
- python-dotenv

## Repository Structure

```text
.
├── src/
│   ├── extract.py
│   ├── transform.py
│   ├── load.py
│   ├── config.py
│   └── utils.py
├── sql/
│   └── schema.sql
├── notebooks/
│   └── analysis.ipynb
├── run_etl.sh
├── requirements.txt
├── README.md
└── LICENSE
```

## Getting Started

### Prerequisites

- Python 3.7 or newer
- PostgreSQL
- API keys for Visual Crossing and AirVisual

### Installation

```bash
git clone https://github.com/jasseurchibani/air_quality_etl_pipline.git
cd air_quality_etl_pipline
python -m venv venv
```

Activate the environment:

```bash
source venv/bin/activate
```

On Windows PowerShell:

```powershell
venv\Scripts\Activate.ps1
```

Install dependencies:

```bash
pip install -r requirements.txt
```

### Environment Variables

Create a `.env` file in the project root:

```env
VISUALCROSSING_API_KEY=your_visual_crossing_api_key
AIRVISUAL_API_KEY=your_airvisual_api_key
DATABASE_URL=postgresql://username:password@host:port/dbname
```

### Database Setup

Run the schema script against your PostgreSQL database:

```bash
psql -U <username> -d <dbname> -f sql/schema.sql
```

## Run the Pipeline

Run each stage manually:

```bash
python src/extract.py
python src/transform.py
python src/load.py
```

Or run the full pipeline script:

```bash
chmod +x run_etl.sh
./run_etl.sh
```

## Explore the Data

Open the analysis notebook:

```bash
jupyter notebook notebooks/analysis.ipynb
```

## Data Flow

1. Extract raw weather and air-quality data.
2. Transform and clean the data.
3. Load the final dataset into PostgreSQL.
4. Analyze the output in the notebook or with SQL queries.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
