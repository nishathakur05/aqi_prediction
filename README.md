# Short-Term Air Quality Index (AQI) Prediction System — New Delhi NCR

Developed as part of the Samsung Innovation Campus (SIC) Artificial Intelligence cohort at Amity University, Gurugram[cite: 2]. This project introduces a predictive analytics and machine learning pipeline to deliver short-term AQI forecasting for the Delhi NCR region, localized using telemetry from the Gurugram Vikas Sadan tracking station[cite: 2]. 

By establishing forecasting pipelines based on a rolling 3-day historical buffer, temporal shifts, and weather constraints, the project aims to support real-time health advisories in highly impacted urban environments[cite: 2].

---

## The Regional Core Problem
* **The Crisis:** New Delhi NCR consistently ranks among the world's most critically polluted urban hubs, with average AQI values scaling past 300, which exceeds standard World Health Organization (WHO) safety guidelines by over 6.6x[cite: 2].
* **Health Footprint:** This severe ambient pollution contributes to an estimated 70 deaths per 100,000 residents annually, imposing a baseline respiratory impact equivalent to smoking 4 cigarettes a day for every individual in the area[cite: 2].
* **The Objective:** To engineer a short-term forecasting capability that captures sudden pollution spikes and non-linear atmospheric cycles to enable proactive health warnings[cite: 2].

---

## Dataset Architecture & Tracking Matrix

The engine processes a multi-dimensional data grid containing 25 columns mapped across temporal, geographical, pollutant, and meteorological matrices:

* **Temporal Tracking:** datetime, date, year, month, day, hour, day_of_week, is_weekend, season
* **Geographical Vectors:** city, station (Target Focus: Gurugram Vikas Sadan)[cite: 2]
* **Pollutant Signatures:** PM2.5, PM10, NO2 (Nitrogen Dioxide), SO2 (Sulfur Dioxide), CO (Carbon Monoxide), O3 (Ozone)[cite: 2]
* **Meteorological Overlays:** temperature, humidity, wind_speed, visibility

---

## Analytical Explorations & Core Realities

### 1. Seasonal Distribution & Atmospheric Stagnation
* **The Winter Trap:** Winter acts as a structural choke point, registering 2,146 days classified as Severe and 742 days as Very Poor due to cold air trapping and low boundary layer heights[cite: 2].
* **The Monsoon Cleanse:** Heavy seasonal rain downpours clear suspended elements, producing 689 Good and 1,467 Satisfactory clean air days via natural precipitation washing[cite: 2].

### 2. Time-of-Day Volatility & Weekday Patterns
* **Predictability Thresholds:** Early evening hours around 18:00 (6:00 PM) showcase stable, structurally predictable trends with a low standard deviation of 162.5[cite: 2]. Conversely, early morning hours at 06:00 AM feature chaotic atmospheric shifts and peak volatility, with standard deviation scaling to 180.0[cite: 2].
* **Anthropogenic Rhythms:** Concentrated human and industrial operations yield an elevated weekday average mean AQI of 264.74, compared to a weekend baseline drop down to 249.66 due to reduced traffic[cite: 2].

### 3. Feature Correlations & Weather Buffers
* **Pollutant Loading:** Core particulates (PM2.5, PM10) alongside gaseous outputs (CO, SO2, NO2) share an intense, direct linear dependency with overall AQI scores.
* **Natural Weather Buffers:** Meteorological features act as primary dispersion catalysts. Visibility exhibits an inverse relationship with localized pollution indices (-0.85), while ambient temperature (-0.74) and surface wind speeds (-0.54) act as natural clearing components.

---

## Machine Learning Benchmarks & Evaluation

The workspace benchmarks three regression models to predict continuous next-day localized AQI tracks based on the preceding 3-day conditions[cite: 2].

### Predictive Performance Grid
* **Random Forest Regression:**
  * Root Mean Squared Error (RMSE): 34.0973[cite: 2]
  * Mean Squared Error (MSE): 1162.6282[cite: 2]
  * Mean Absolute Error (MAE): 23.5905[cite: 2]
  * R-Squared Score ($R^2$): 0.9642[cite: 2]

* **XGBoost Regressor:**
  * Root Mean Squared Error (RMSE): 34.3983[cite: 2]
  * Mean Squared Error (MSE): 1183.2444[cite: 2]
  * Mean Absolute Error (MAE): 23.5731[cite: 2]
  * R-Squared Score ($R^2$): 0.9636[cite: 2]

* **Linear Regression Baseline:**
  * Root Mean Squared Error (RMSE): 36.4843[cite: 2]
  * Mean Squared Error (MSE): 1331.1098[cite: 2]
  * Mean Absolute Error (MAE): 24.9636[cite: 2]
  * R-Squared Score ($R^2$): 0.9590[cite: 2]

### Technical Summary
1. **Random Forest Regression:** Captured non-linear micro-spikes and temporal features effectively, yielding the highest statistical variance coverage with an $R^2$ score of 96.42%[cite: 2].
2. **XGBoost Regression:** Demonstrated high gradient efficiency, minimizing absolute prediction bounds to achieve the lowest overall Mean Absolute Error of 23.57[cite: 2].
3. **Linear Regression Baseline:** Established a baseline trend tracking capability, proving that previous 3-day history maintains strong linear dependencies that account for 95.90% of variance[cite: 2].

---
