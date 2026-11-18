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
- Delhi is the most polluted state with an average AQI of 206, followed by Jharkhand (165), Himachal Pradesh (160) and Bihar (157). Mizoram is the cleanest at 47.
- Byrnihat (Assam) has the highest average AQI among locations (240). Most other top locations are in the Delhi-NCR region, such as Greater Noida, Gurugram, Ghaziabad and Faridabad.
- Winter has the worst air quality (average AQI 139), followed by Post-Monsoon (132) and Summer (112). Monsoon is the cleanest season (81).
- November 2023 was the most polluted month (165) and August 2024 the cleanest (63).
- Delhi's average AQI (206) is about double that of Mumbai (106) and Kolkata (102), and nearly three times that of Chennai (74) and Bengaluru (75).
- PM10 is the most frequent prominent pollutant (135,806 records), followed by PM2.5 (78,030).
- About 55% of records fall in the Good or Satisfactory categories, 33% are Moderate, and about 12% are Poor, Very Poor or Severe.
- About 19.9% of area-days were missing and were filled using mean imputation (each location's own mean AQI).

## How to run
1. Install Python and Jupyter Notebook (or use Google Colab)
2. Keep `AQI_Analysis.ipynb` and `aqi.csv` in the same folder
3. Run all cells from top to bottom

## Libraries
pandas, numpy, matplotlib, seaborn
