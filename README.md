# 🌦️ Global Weather Trend Forecasting & Climate Analysis

### Advanced Time-Series Forecasting, Spatial Analysis & Environmental Impact Assessment using the Global Weather Repository

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-yellowgreen?logo=scikit-learn)
![Prophet](https://img.shields.io/badge/Prophet-Forecasting-blue)
![Folium](https://img.shields.io/badge/Folium-Interactive%20Maps-green)
![Domain](https://img.shields.io/badge/Domain-Climate%20%7C%20Data%20Science-teal)

---

## 📌 Overview

Climate variability and extreme weather events are among the most consequential challenges of our time — affecting agriculture, infrastructure, energy systems, and public health at a global scale. Understanding and forecasting weather trends requires not just historical analysis but sophisticated time-series modeling and spatial reasoning across geographically diverse datasets.

This project delivers a **full-stack weather analytics pipeline** built on the **Global Weather Repository** dataset, combining:

- **Time-series forecasting** with ARIMA, Facebook Prophet, and ensemble methods
- **Climate trend analysis** across long-term seasonal and regional patterns
- **Environmental impact assessment** — correlating weather variables with air quality metrics
- **Interactive geospatial visualization** via a Folium-powered HTML map
- **Feature importance evaluation** using Random Forest to identify the strongest predictors of temperature

> 📄 A full detailed project report (`Detailed_project_report.pdf`) is included in this repository.
> 🗺️ An interactive weather map (`weather_map.html`) is also included — open it in any browser.

---

## 🎯 Project Objectives

- Clean and preprocess a large, real-world global weather dataset with missing values and irregular formats
- Perform EDA to uncover temperature and precipitation trends across regions and seasons
- Build, compare, and ensemble **ARIMA** and **Prophet** forecasting models for weather prediction
- Conduct advanced climate, environmental, and spatial analyses to extract actionable insights
- Visualize global weather patterns interactively on a geographic map

---

## 🗂️ Repository Structure

```
PM_ACCELERATOR/
│
├── Advanced_Assessment.ipynb       # Full analysis: EDA, forecasting, all advanced analyses
├── GlobalWeatherRepository.csv     # Global weather dataset (source: Kaggle)
├── weather_map.html                # Interactive Folium map — open in browser
├── Detailed_project_report.pdf     # Complete project report and findings
└── README.md
```

---

## 📊 Dataset — Global Weather Repository

| Property | Details |
|---|---|
| **Source** | [Global Weather Repository — Kaggle](https://www.kaggle.com/datasets/nelgiriyewithana/global-weather-repository) |
| **Coverage** | Global — multiple countries and continents |
| **Key Variables** | Temperature (max/min/avg), precipitation, humidity, wind speed, air pressure, UV index, air quality metrics (PM2.5, CO, ozone) |
| **Temporal Coverage** | Multi-year daily records |
| **Format** | CSV — tabular time-series |

---

## 🏗️ Pipeline Architecture

```
Raw Global Weather Data (CSV)
           │
           ▼
  ┌─────────────────────────────────┐
  │     Data Cleaning &             │
  │     Preprocessing               │
  │  • Missing value imputation     │
  │  • Date parsing & indexing      │
  │  • Outlier detection            │
  │  • Feature normalization        │
  └─────────────────────────────────┘
           │
           ▼
  Exploratory Data Analysis (EDA)
  (temperature trends, precipitation patterns,
   seasonal decomposition, correlation heatmaps)
           │
     ┌─────┴──────┐
     ▼            ▼
  ARIMA        Prophet
  Model        Model
     │            │
     └─────┬──────┘
           ▼
    Ensemble Forecast
    (weighted combination for improved accuracy)
           │
           ▼
  ┌──────────────────────────────────────────┐
  │         Advanced Analyses                │
  │  • Climate Trend Analysis                │
  │  • Environmental Impact Assessment       │
  │  • Feature Importance (Random Forest)    │
  │  • Spatial Analysis (Folium Maps)        │
  │  • Geographical Pattern Comparison       │
  └──────────────────────────────────────────┘
```

---

## 🔬 Methodology

### 1. Data Cleaning & Preprocessing
- Identified and imputed missing values using forward-fill and median strategies
- Parsed datetime columns and set proper time-series indices for forecasting
- Removed duplicate records and handled outliers via IQR-based filtering
- Normalized continuous features for use in ML models

### 2. Exploratory Data Analysis
- Daily and monthly temperature trend visualization across regions
- Precipitation frequency and intensity distribution
- Seasonal decomposition to separate trend, seasonality, and residuals
- Correlation heatmap across all weather and air quality variables

### 3. Forecasting Models

#### ARIMA (AutoRegressive Integrated Moving Average)
- Classical statistical time-series model suited for univariate, stationary sequences
- ACF/PACF plots used to determine optimal (p, d, q) hyperparameters
- Evaluated on RMSE and MAE against held-out test periods

#### Facebook Prophet
- Additive forecasting model designed for business/environmental time series with strong seasonality
- Handles missing data and holiday/event effects gracefully
- Automatically decomposes into trend + weekly + yearly seasonal components
- Produces uncertainty intervals for forecast confidence bands

#### Ensemble Forecast
- Weighted average of ARIMA and Prophet predictions
- Ensemble consistently outperformed individual models by smoothing their respective failure modes
- Evaluated across multiple forecast horizons (7-day, 30-day, 90-day)

### 4. Advanced Analyses

**Climate Trend Analysis**
- Long-term temperature trend identification across decades
- Regional comparison of warming/cooling patterns
- Seasonal variation analysis (amplitude and timing shifts)

**Environmental Impact Assessment**
- Correlation analysis between weather parameters (temperature, humidity, wind) and air quality indices (PM2.5, CO, ozone levels)
- Identification of weather conditions associated with elevated pollution events
- Heatwave and pollution co-occurrence mapping

**Feature Importance Evaluation**
- Random Forest regressor trained to predict temperature
- Feature importance scores extracted using mean decrease in impurity (MDI)
- Identifies which variables (humidity, pressure, wind speed, UV index, etc.) are the strongest predictors — actionable for feature selection in downstream models

**Spatial Analysis**
- Interactive **Folium** map (`weather_map.html`) visualizing weather conditions geographically
- Choropleth and marker-based layers for temperature, precipitation, and air quality
- Enables visual identification of regional clusters and geographic outliers

**Geographical Pattern Analysis**
- Country and continent-level aggregation and comparison
- Identifies climatically similar and distinct regions
- Boxplots and violin plots comparing distributions across geographic groups

---

## 📈 Key Findings

- The **ensemble forecast** outperformed both standalone ARIMA and Prophet across all test horizons, with the greatest improvement at longer ranges (30–90 day forecasts)
- **Humidity and atmospheric pressure** emerged as the top predictors of temperature variation in the Random Forest feature importance analysis
- Strong positive correlations were found between **high-temperature days and elevated PM2.5 levels**, consistent with known climate-air quality linkages
- Tropical regions showed the least seasonal temperature variance while continental climates exhibited the highest amplitude seasonal cycles
- Interactive spatial mapping revealed clear **longitudinal banding patterns** in average temperature — confirming expected latitudinal climate zones and flagging regional anomalies

> *Add your specific RMSE/MAE numbers from the notebook for maximum impact.*

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels prophet folium jupyter
```

### Running the Notebook

```bash
git clone https://github.com/avanthikarajesh30/PM_ACCELERATOR.git
cd PM_ACCELERATOR
jupyter notebook Advanced_Assessment.ipynb
```

Or open directly in **Google Colab**:

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/avanthikarajesh30/PM_ACCELERATOR/blob/main/Advanced_Assessment.ipynb)

### Viewing the Interactive Map

Simply open `weather_map.html` in any web browser — no server required:

```bash
open weather_map.html        # macOS
start weather_map.html       # Windows
xdg-open weather_map.html    # Linux
```

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.8+ | Core language |
| Jupyter Notebook | Analysis and visualization |
| pandas / NumPy | Data manipulation and preprocessing |
| Matplotlib / Seaborn | Static visualizations and EDA plots |
| statsmodels | ARIMA time-series modeling |
| Prophet (Meta) | Additive seasonal forecasting |
| scikit-learn | Random Forest feature importance, preprocessing |
| Folium | Interactive geospatial map generation |
| HTML | Standalone interactive map output |

---

## 🌍 Real-World Applications

- **Climate monitoring agencies** — automated regional trend alerts and forecast dashboards
- **Agricultural planning** — long-range temperature and precipitation forecasts for crop management
- **Energy sector** — demand forecasting based on weather-driven heating/cooling loads
- **Public health** — early warning systems for heatwaves and high-pollution events
- **Urban planning** — data-driven decision-making for climate-resilient infrastructure
- **Insurance & risk modeling** — quantifying weather-related financial exposure

---

## 🔮 Future Work

- Integrate **deep learning forecasting** — N-BEATS, Temporal Fusion Transformer (TFT), or PatchTST for improved long-range accuracy
- Add **real-time data ingestion** via OpenWeatherMap or NOAA APIs for live forecasting
- Build a **Streamlit or Dash dashboard** wrapping all analyses into an interactive web app
- Extend environmental analysis to include **carbon emission correlations**
- Incorporate **satellite imagery data** (NDVI, land surface temperature) for richer spatial features
- Apply **clustering algorithms** (K-Means, DBSCAN) to identify climatically homogeneous regions automatically

---

## 👩‍💻 Author

**Avanthika Rajesh**
MS Computer Engineering — Virginia Tech
[GitHub](https://github.com/avanthikarajesh30) • [LinkedIn](https://linkedin.com/in/YOUR_LINKEDIN_HERE)

---

## 📄 License

This project is licensed under the MIT License.

Dataset sourced from Kaggle under its respective terms of use.

---

## 🙏 Acknowledgements

- **Global Weather Repository** dataset — Nelgiriye Withana, available on [Kaggle](https://www.kaggle.com/datasets/nelgiriyewithana/global-weather-repository)
- **Meta (Facebook) Research** for the open-source Prophet forecasting library
- **PM Accelerator** program for the project framework and assessment structure
