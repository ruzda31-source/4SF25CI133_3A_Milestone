# Air Quality Index (AQI) in India, 2022-2025 - Milestone 1 CIE

## Overview
This project analyzes daily air quality data from Indian cities and states using Python and Pandas. It covers data transformation, null value handling with mean imputation, insight generation, and visualization.

## Dataset
- **File:** `aqi.csv`
- **Source:** Daily AQI by area and state across India (CPCB data)
- **Size:** 235,785 records, 292 locations across 32 states, 1 April 2022 to 30 April 2025
- **Columns:** date, state, area, number_of_monitoring_stations, prominent_pollutants, aqi_value, air_quality_status, note
- **Note:** a constant text column `unit` was removed from the file before upload to keep it under GitHub's 25 MB upload limit.

## Files
- `AQI_Analysis.ipynb` - notebook with the full analysis
- `aqi.csv` - dataset used
- `README.md` - this file

## What the notebook does
1. Reads the CSV with Pandas
2. Studies the structure (shape, info, describe, duplicates)
3. Transforms data: drops empty/constant columns, converts `date` to datetime, converts `air_quality_status` to an ordered category, adds `Year`, `Month`, `Season` and `location`
4. Identifies null values (the `note` column is empty) and finds missing area-days by reshaping to a date x location table
5. Fills missing area-days using mean imputation (each location's own mean AQI)
6. Generates insights: most polluted states and locations, monthly and seasonal trends, major city comparison, prominent pollutants, AQI category distribution
7. Visualizes the insights with bar charts, line charts and a heatmap

## Key findings
*(Write your own findings here after reading the notebook outputs.)*
-
-
-

## How to run
1. Install Python and Jupyter Notebook (or use Google Colab)
2. Keep `AQI_Analysis.ipynb` and `aqi.csv` in the same folder
3. Run all cells from top to bottom

## Libraries
pandas, numpy, matplotlib, seaborn
