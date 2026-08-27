# Fitbit User Activity & Wellness Analysis
### Google Data Analytics Specialization — Capstone Project

![SQL](https://img.shields.io/badge/Tool-MySQL-orange?logo=mysql)
![Excel](https://img.shields.io/badge/Tool-Excel-green?logo=microsoft-excel)
![R](https://img.shields.io/badge/Tool-R-blue?logo=r)

---

## Table of Contents

- [Overview](#overview)
- [Business Task](#business-task)
- [Objectives](#objectives)
- [Dataset](#dataset)
- [Tools & Technologies](#tools--technologies)
- [Methodology](#methodology)
- [SQL Analysis Results](#sql-analysis-results)
- [R Analysis & Visualizations](#r-analysis--visualizations)
- [Key Performance Indicators](#key-performance-indicators)
- [Key Findings](#key-findings)
- [Business Recommendations](#business-recommendations)
- [Repository Contents](#repository-contents)
- [Acknowledgments](#acknowledgments)

---

## Overview

This capstone project analyzes Fitbit smart-device usage data to understand user behavior around activity, sleep, calories, intensity, and heart rate. The analysis follows the Google Data Analytics case study framework (Ask → Prepare → Process → Analyze → Share → Act) and was built for **Bellabeat**, a wellness technology company, to inform product and marketing strategy using real usage patterns.

---

## Business Task

Bellabeat wants insight into how users interact with wearable devices to improve product engagement and marketing effectiveness. This project answers three questions:

1. What are the main behavioral trends in activity, sleep, and heart rate?
2. How do these trends reflect user habits across the day and week?
3. What insights can guide Bellabeat's marketing and product decisions?

---

## Objectives

- Clean and structure 7 raw Fitbit datasets into an analysis-ready format
- Build a relational MySQL schema to validate and aggregate sensor data
- Identify activity, sleep, and heart-rate patterns across users, days, and hours
- Visualize behavioral trends in R to support clear, evidence-based recommendations
- Translate findings into concrete marketing and product recommendations for Bellabeat

---

## Dataset

| Attribute | Detail |
|---|---|
| Source | Fitbit Fitness Tracker Data (Public Domain — Möbius / Kaggle) |
| Raw Files | 7 CSV files (activity, sleep, heart rate, intensity, calories, steps) |
| Users | 30+ unique Fitbit users |
| Granularity | Daily and hourly logs |
| Final Output | `Transformed_Fitbit_Dataset.xlsx` — cleaned, merged dataset |

---

## Tools & Technologies

| Category | Tools |
|---|---|
| Data Cleaning | MS Excel |
| Database & Query | MySQL Workbench |
| Analysis & Visualization | RStudio |
| R Libraries | tidyverse, dplyr, lubridate, readxl, janitor, ggplot2 |

---

## Methodology

**1. Ask — Define the Problem**
Identified Bellabeat as the stakeholder and framed the core business questions around activity, sleep, and heart-rate behavior.

**2. Prepare — Data Collection & Initial Review**
Loaded 7 raw Fitbit CSV files in Excel. Identified key data issues: inconsistent datetime formats, heart rate outliers, missing sleep values, and high-frequency log volume.

**3. Process — Cleaning & Structuring**
Fixed formatting inconsistencies, engineered new fields (`day_of_week`, `week_number`, `sleep_hours`), rounded numerical data, and verified dataset integrity before loading into MySQL.

**4. Analyze — SQL & R**
Built a relational MySQL schema, validated row counts and date ranges, and constructed a `daily_master` aggregation table combining steps, sleep, heart rate, intensity, and calories per user per day. Mirrored and extended this analysis in R for statistical summarization and visualization.

**5. Share — Visualization**
Produced R visualizations (ggplot2) to communicate activity, sleep, and heart-rate trends clearly for a non-technical stakeholder audience.

**6. Act — Recommendations**
Converted findings into specific marketing, product, and engagement recommendations for Bellabeat.

---

## SQL Analysis Results

All queries in [`fitbit_analysis.sql`](./fitbit_analysis.sql); all screenshots in [`Fitbit_analysis_results`](./Fitbit_analysis_results).

| # | Result | Screenshot |
|---|--------|------------|
| 1 | Row counts per table — validates row load per dataset | ![Row Counts](./Fitbit_analysis_results/row_counts_per_table_sql.png) |
| 2 | Distinct users — confirms total unique Fitbit users | ![Distinct Users](./Fitbit_analysis_results/daily_activity_distinct_users_sql.png) |
| 3 | Date range validation — confirms consistent date coverage across tables | ![Date Range](./Fitbit_analysis_results/date_range_checks_sql.png) |
| 4 | Invalid heart rate records — confirms filtering of unrealistic HR values | ![Invalid HR](./Fitbit_analysis_results/invalid_heartrate_records_sql.png) |
| 5 | Daily sleep summary — aggregated sleep minutes per user per day | ![Daily Sleep](./Fitbit_analysis_results/daily_sleep_sum_sql.png) |
| 6 | Daily steps summary — daily totals from hourly logs | ![Daily Steps](./Fitbit_analysis_results/daily_steps_sql.png) |
| 7 | Daily calories summary — total calories burned per user per day | ![Calories](./Fitbit_analysis_results/daily_calories_sql.png) |
| 8 | Daily intensity summary — daily totals and averages of intensity metrics | ![Intensity](./Fitbit_analysis_results/daily_intensity_summary_sql.png) |
| 9 | Daily heart rate summary — mean, min, max HR per day | ![HR Summary](./Fitbit_analysis_results/daily_heartrate_summary_sql.png) |
| 10 | Daily master table validation — combined steps, sleep, HR, intensity, calories | ![Daily Master](./Fitbit_analysis_results/daily_master_table_validation_sql.png) |
| 11 | Total users check — confirms user presence across aggregated datasets | ![Total Users](./Fitbit_analysis_results/total_users_sql.png) |
| 12 | Summary metrics overview — key averages: steps, sleep, HR, calories | ![Summary Metrics](./Fitbit_analysis_results/overall_summary_metrics_sql.png) |
| 13 | Average steps by day of week — reveals highest-activity weekdays | ![Avg Steps Week](./Fitbit_analysis_results/avg_steps_by_day_of_week_sql.png) |
| 14 | Sleep vs. steps relationship — tests link between sleep duration and activity | ![Sleep vs Steps](./Fitbit_analysis_results/sleep_vs_steps_avg_sql.png) |
| 15 | Sedentary minutes vs. calories burned — higher sedentary time, fewer calories | ![Sed vs Cal](./Fitbit_analysis_results/sedentary_vs_calories_avg_sql.png) |
| 16 | Daily average heart rate trend — day-to-day HR fluctuation | ![HR Trend](./Fitbit_analysis_results/daily_heartrate_trend_sql.png) |
| 17 | Top 10 most active users — ranked by average daily steps | ![Top Users](./Fitbit_analysis_results/top_10_users_by_avg_steps_sql.png) |
| 18 | Sorted weekday step counts — full weekday activity ranking | ![Weekday Sorted](./Fitbit_analysis_results/avgg_steps_by_day_of_week_sql.png) |
| 19 | Average steps by hour — highlights peak activity window (7–10 AM) | ![Hourly Steps](./Fitbit_analysis_results/avg_steps_by_hour_sql.png) |

---

## R Analysis & Visualizations

Full RStudio project in [`fitbit_analysis_R`](./fitbit_analysis_R). Workflow: imported all 7 sheets, cleaned date/time fields, summarized daily HR/sleep/steps/calories/intensity, merged datasets, generated final visuals below.

| # | Visualization | Chart |
|---|----------------|-------|
| 1 | Average daily steps by day of week — Wednesday peaks | ![Avg Steps Week](./Fitbit_analysis_results/avg_daily_steps_by_of_week_R.png) |
| 2 | Sleep hours vs. daily steps — correlation check | ![Sleep vs Steps](./Fitbit_analysis_results/relationship_btw_sleep_hrs_&_daily_steps_R.png) |
| 3 | Calories burned vs. active minutes — burn rises with active time | ![Calories vs Active Minutes](./Fitbit_analysis_results/calories_burned_vs_active_mints_R.png) |
| 4 | Average daily heart rate trend — long-term HR fluctuation | ![HR Trend](./Fitbit_analysis_results/daily_Avg_heartrate_trend_R.png) |
| 5 | Average steps by hour of day — confirms 7–10 AM peak activity window | ![Steps by Hour](./Fitbit_analysis_results/avg_steps_by_hour_of_day_R.png) |

---

## Key Performance Indicators

| KPI | Result |
|---|---|
| Users Analyzed | 30+ |
| Peak Activity Window | 7 AM – 10 AM |
| Highest-Activity Weekday | Wednesday |
| Average Sleep Duration | 5–7.5 hours |
| Active Minutes ↔ Calories | Strong positive relationship |
| Sedentary Minutes ↔ Calories | Negative relationship |

---

## Key Findings

- Activity consistently peaks between **7 AM and 10 AM**, indicating a strong morning-exercise pattern among users.
- **Wednesday** shows the highest average step count of any weekday — a mid-week engagement spike.
- Users sleep **5–7.5 hours** on average, below the commonly recommended 7–9 hour range.
- **Very active minutes** show a clear positive relationship with **calories burned**.
- **Sedentary minutes** are negatively associated with calorie burn, confirming the cost of prolonged inactivity.
- Heart rate shows recurring **afternoon peaks** across the user base.

---

## Business Recommendations

**Marketing Strategy**
- Send morning "Get Moving" push notifications timed to the 7–10 AM activity window
- Run mid-week engagement campaigns to reinforce the natural Wednesday activity spike
- Trigger sedentary alerts during extended periods of inactivity

**Product Enhancements**
- Improve sleep-tracking accuracy given the below-recommended average sleep duration observed
- Add stress scoring derived from heart-rate pattern analysis
- Introduce personalized, intensity-based workout suggestions

**User Engagement**
- Deliver weekly progress summaries to reinforce habit formation
- Introduce gamified step challenges around peak activity days
- Suggest sleep-activity balance tips based on individual user trends

---

## Repository Contents

| Folder / File | Description |
|---|---|
| `Fitbit_analysis_results/` | SQL query screenshots + R visualizations |
| `fitbit_analysis_R/` | RStudio project files |
| `Transformed_Fitbit_Dataset.xlsx` | Final cleaned, merged dataset |
| `fitbit_analysis.sql` | MySQL analysis script |

---

## Acknowledgments

Dataset: Fitbit Fitness Tracker Data (Public Domain — Möbius / Kaggle). Completed as part of the Google Data Analytics Professional Certificate.

---
