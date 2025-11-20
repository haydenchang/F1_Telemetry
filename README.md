# F1 Race Telemetry Intelligence

Multi-sensor EDA of F1 driver performance, racing lines, tires, and strategy.

## 📌 Overview

This project analyzes Formula 1 race telemetry using FastF1 + Ergast to understand how drivers extract performance from the car.

Instead of heavy ML, the focus is on complex data engineering, deep exploratory analysis, and clear visualizations.

## 📂 Data Sources

- FastF1 API: telemetry (speed, throttle, brake, gear, RPM, DRS), GPS x/y, laps, stints, pit stops, weather

- Ergast API: driver/team metadata, race results

- Optional track maps & tire metadata

## 🧠 Key Analysis Areas

- Driver pace & consistency

- Speed/throttle/brake overlays (corner-level comparison)

- Racing line mapping using GPS

- Tire degradation & stint evolution

- Pit strategy & undercut/overcut gains

- Dirty air vs free-air behavior during battles

## 🏗️ Project Structure
f1-telemetry-eda/
├── data/
├── notebooks/
│   ├── 01_data_ingestion.ipynb
│   ├── 03_lap_time_eda.ipynb
│   ├── 04_telemetry_signals_eda.ipynb
│   └── 05_racing_line_eda.ipynb
├── src/
└── website/

## 🔧 How It Works

1. Ingest & cache telemetry via FastF1

2. Clean & merge laps, stints, pit stops, telemetry

3. Build features:

- stint index

- speed deltas

- braking/throttle metrics

- DRS usage

4. Perform EDA:

- lap-time trends

- telemetry overlays

- racing-line heatmaps

- tire degradation curves

- pit strategy timeline

## 🚀 Run
pip install -r requirements.txt

import fastf1
fastf1.Cache.enable_cache('./data/raw')


Run notebooks in order starting with 01_data_ingestion.ipynb.
