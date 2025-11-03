# Analysis

This folder contains notebooks for analyzing project data after it has been processed and prepared in the presentation layer (`f1_presentation`).

## Purpose

The analysis focuses on:

- Identifying dominant drivers in specific decades.
- Identifying dominant teams throughout race history.
- Presenting results in tables and simple HTML visualizations.

---

## Files

### 1. Dominant Drivers

- SQL/Databricks notebook for analyzing top drivers.
- Calculates:
  - Total races (`total_races`) for each driver.
  - Total points (`total_points`) and average points (`avg_points`) per season.
  - Ranking (`RANK() OVER`) of drivers based on average points.
- Subqueries filter only the top 10 drivers for further analysis.
- Results can be used for seasonal points charts of top drivers.

### 2. Dominant Teams

- SQL/Databricks notebook for analyzing top teams (constructors).
- Calculates:
  - Total races (`total_races`) for each team.
  - Total and average points (`total_points`, `avg_points`).
  - Team ranking based on average points.
- Subqueries filter the top 10 teams.
- Prepares data for visualizing seasonal team results.

### 3. Visualization

- Python/Databricks notebooks for visualizing results.
- Create simple HTML reports and summary tables:
  - Top 10 drivers by decade.
  - Top 10 teams in race history.
- Provides a quick view of dominant entities in Formula 1.

---

## How to Use

1. Run all notebooks
2. Results will be available in temporary views in Databricks.
3. Visualizations can be displayed directly in the notebook using `displayHTML`.
