

# Big Data Capstone Project: Smart Agriculture Analytics using Databricks & PySpark

## Overview

This project demonstrates how **Big Data Analytics**, **Machine Learning**, and **Cloud Platforms** like **Databricks** can transform traditional agriculture into a **data-driven and intelligent system**.
By analyzing climate, soil, and crop datasets, the project builds a complete **data pipeline** and delivers actionable insights for optimizing agricultural productivity and sustainability.

The project implements **five analytical use cases** that together form an end-to-end smart agriculture solution — from **data ingestion to visualization**.

---

## Project Objectives

* To develop a **Big Data Pipeline** using **Databricks (PySpark)** for agricultural data processing.
* To design **predictive and analytical models** for multiple agricultural use cases.
* To visualize insights through an **interactive Databricks dashboard**.
* To support data-driven decision-making for **farmers, researchers, and policymakers**.

---

##  Key Features

* Multi-layered data architecture: **Bronze → Silver → Gold (Feature → Model → Visualization)**
* Predictive and classification models using **Spark MLlib**.
* Integration of multiple datasets (Climate, Soil, Crop Yield, Rainfall).
* Fully automated **Databricks pipeline orchestration**.
* Real-time insights and visual dashboards.

---

## Project Architecture

```
                ┌───────────────────────────────┐
                │        Data Sources            │
                │ (FAO, ICAR, Rainfall, Soil)   │
                └──────────────┬────────────────┘
                               │
                         (Data Ingestion)
                               │
                ┌──────────────▼──────────────┐
                │        Bronze Layer         │
                │ Raw data loaded in Delta    │
                └──────────────┬──────────────┘
                               │
                         (Data Cleaning)
                               │
                ┌──────────────▼──────────────┐
                │         Silver Layer        │
                │ Transformed and validated   │
                └──────────────┬──────────────┘
                               │
                        (Feature Engineering)
                               │
                ┌──────────────▼──────────────┐
                │           Models            │
                │ ML-based Predictions (Yield,│
                │ Climate Match, Soil, GDD)   │
                └──────────────┬──────────────┘
                               │
                         (Visualization)
                               │
                ┌──────────────▼──────────────┐
                │        Dashboard Layer      │
                │ Interactive Graphs & KPIs   │
                └──────────────────────────────┘
```

---

## Use Cases Implemented

### 1️**Crop Yield Prediction**

Predicts yield for major crops using rainfall, temperature, and humidity data.

* Algorithm: Linear Regression (Spark MLlib)
* Output: Predicted vs Actual Yield Chart
* Insight: Optimal rainfall levels significantly influence yield performance.

---

### 2️ **Rainfall Impact Analysis**

Analyzes the influence of rainfall fluctuations on yield performance.

* Method: Correlation and Trend Analysis
* Output: Rainfall–Yield correlation visualization
* Insight: Strong dependency between rainfall variability and yield outcome.

---

### 3️**Climate–Crop Matching**

Identifies the best climatic conditions for specific crops using environmental parameters.

* Method: Clustering and Filtering
* Output: Crop–Region suitability chart
* Insight: Enables better regional planning and crop selection.

---

### 4️**Growing Degree Days (GDD) Analysis**

Calculates accumulated temperature for optimal crop development.

* Formula: GDD = ((Tmax + Tmin) / 2) – Tbase
* Output: Cumulative GDD growth curve
* Insight: Assists in scheduling sowing and harvesting periods.

---

### 5️ **Soil–Crop Recommendation**

Recommends suitable crops based on soil composition (NPK, pH, Organic Carbon).

* Algorithm: Random Forest Classifier
* Output: Crop recommendation per soil type + Feature Importance Chart
* Insight: Improves sustainability through soil-based crop selection.

---

##  Tech Stack

| Category                 | Technology                                |
| ------------------------ | ----------------------------------------- |
| **Platform**             | Databricks                                |
| **Big Data Framework**   | Apache Spark (PySpark)                    |
| **Storage Format**       | Delta Lake                                |
| **Programming Language** | Python                                    |
| **ML Library**           | Spark MLlib                               |
| **Visualization**        | Matplotlib, Databricks Dashboard          |
| **Data Source**          | FAOSTAT, Climate, Soil, Rainfall datasets |

---

##  Folder Structure

```
Big Data Project Pipeline/
│
├── 01_ingest_bronze/              # Raw data ingestion
├── 02_clean_silver/               # Data transformation and cleaning
├── 03_feature_engineering/        # Feature extraction and preprocessing
├── 04_models_and_usecases/        # ML models for 5 use cases
├── 05_visualizations/             # Dashboard visuals
└── 00_master_pipeline_runner/     # Master orchestration notebook
```

---

## Datasets Used

| Dataset               | Description                                 | Source                                 |
| --------------------- | ------------------------------------------- | -------------------------------------- |
| **FAOSTAT Crop Data** | Annual crop yield and area harvested        | [FAO](https://www.fao.org/faostat/en/) |
| **Rainfall Dataset**  | Historical rainfall records                 | IMD / Climate Data Portal              |
| **Climate Dataset**   | Temperature, humidity, wind speed, pressure | Kaggle / OpenWeather                   |
| **Soil Dataset**      | NPK, pH, organic carbon values              | ICAR / Regional Databases              |

---

##  Pipeline Execution Flow

1. **Bronze Layer:** Ingest all datasets into Databricks tables (Delta format).
2. **Silver Layer:** Clean and transform the datasets (remove nulls, rename columns).
3. **Feature Engineering:** Combine datasets and prepare features for ML models.
4. **Model Layer:** Train ML models for each use case (Regression, Classification).
5. **Visualization Layer:** Generate dashboards summarizing all insights.
6. **Master Pipeline Runner:** Execute all stages sequentially.

---

##  Dashboard Insights (Sample Visuals)

| Use Case            | Visualization                                                                                                      |
| ------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Yield Prediction    | ![Yield Prediction](https://raw.githubusercontent.com/yourusername/project/main/images/yield_prediction.png)       |
| Rainfall Impact     | ![Rainfall Impact](https://raw.githubusercontent.com/yourusername/project/main/images/rainfall_impact.png)         |
| Climate Matching    | ![Climate Matching](https://raw.githubusercontent.com/yourusername/project/main/images/climate_match.png)          |
| GDD Timing          | ![GDD Timing](https://raw.githubusercontent.com/yourusername/project/main/images/gdd_curve.png)                    |
| Soil Recommendation | ![Soil Recommendation](https://raw.githubusercontent.com/yourusername/project/main/images/soil_recommendation.png) |

---

##  Results Summary

| Use Case            | Model Used         | Accuracy / R² | Key Insight                                   |
| ------------------- | ------------------ | ------------- | --------------------------------------------- |
| Yield Prediction    | Linear Regression  | 0.89          | Yield rises with rainfall up to optimal level |
| Rainfall Impact     | Correlation        | 0.83          | Yield fluctuates with rainfall intensity      |
| Climate Matching    | Clustering         | -             | Matched crops to optimal climatic zones       |
| GDD Analysis        | Custom Calculation | -             | Identified critical growth temperature range  |
| Soil Recommendation | Random Forest      | 93%           | Soil type strongly influences crop selection  |

---

##  Challenges & Solutions

* **Challenge:** Data inconsistencies and missing values
   *Solution:* Implemented Spark-based data cleaning and imputations
* **Challenge:** Large data volumes
  *Solution:* Used Databricks Delta tables for optimized storage
* **Challenge:** Multiple data sources integration
   *Solution:* Unified schema and feature alignment in Silver layer

---

##  Future Enhancements

* Integrate real-time **IoT sensor data** for soil and weather monitoring
* Use **Deep Learning models** (LSTM, ARIMA) for time-series yield forecasting
* Deploy as a **cloud-based analytics dashboard** for farmers and policymakers
* Add **geospatial and satellite imagery data** for remote sensing insights

---

##  Author

**Kyatham Srilaya**
 [kyathamsrilaya@gmail.com](mailto:kyathamsrilaya@gmail.com)
 Databricks Capstone Project – 2025

---

## Conclusion

This project demonstrates how **Big Data Analytics** and **Machine Learning** can revolutionize agriculture by leveraging data pipelines, predictive analytics, and visual dashboards.
The integrated Databricks workflow offers a scalable, automated, and intelligent system that supports **smart and sustainable farming practices**.

---


