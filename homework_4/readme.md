## Overview
The goal of this homework is to collect weather data, generaate daily dashboards visualizing key metrics, and train a linear regression model using a complete Apache Airflor pipeline.

## Files Included
- info.txt: contains names of teammates and name of MWAA environment and S3 bucket
- de300_homework_4_part_2.py: DAG to collect weather data
- de300_hw4_part3.py: DAG to create weather dashboards
- train_temperature_model_20hr.py: DAG to train regression after 20 hours
- train_temperature_model_40hr.py: DAG to train regression after 40 hours
  
## Weather Stations Used:
- KORD (Chicago O'Hare)
- KENW (Kenosha, WI)
- KMDW (Chicago Midway)
- KPNT (Pontiac, IL)

## Folder Structure in S3:
- weather_data/: Stores CSV files of raw weather observations every 2 hours.
- output_graphs/: Stores daily PNG plots for temperature, visibility, and relative humidity.
- predictions/: Stores temperature predictions for each station at 20 and 40 hours.

## DAG Descriptions and Output:
- weather_daily_dashboard: Collects weather data every 2 hours from 4 stations and uploads to S3
  - Output: weather_YYYYMMDD_HHMMSS.csv
- daily_dashboard: Combines daily data and creates plots for 3 features
  - Output: temperature_YYYY-MM-DD.png, etc.
- train_temperature_model_20h: Trains regression model after 20 hours
  - Output: predicted_temps_20h_*.csv
- train_temperature_model_40h: Trains regression model after 40 hours
  - Output: predicted_temps_40h_*.csv
DAGs are set to run for 48 hours total.

## How to Deploy:
1. Place all DAG .py files in your Airflow dags/ folder.
2. Unpause all DAGs (especially the scheduled ones).
3. Let the DAGs run on schedule.
4. Check logs and S3 bucket for output.

## Generative AI Disclosure
ChatGPT was used to help fix the errors and set up parts of the DAGs. The following prompts were used:
- "Can you help fix this error: *paste in error*"
- "How can I set up the DAG to run for only 48 hours"
- "How can I save my output as a csv in a folder in my S3"
- "How can I pull data from a folder in my S3 to use within my DAG"
