# Weather Data Visualizer 🌦️

## Project Overview
This project analyzes a real-world weather dataset spanning from 2006 to 2016. The goal is to perform data cleaning, statistical analysis, and visualization to uncover meteorological trends and relationships, such as the correlation between temperature and humidity or the accuracy of "apparent temperature" versus actual recorded temperature.

## Dataset Description
The analysis is based on the **Weather History** dataset (`weatherHistory.csv`), which contains hourly weather observations.

**Key Columns:**
* **Formatted Date:** Timestamp of the observation.
* **Summary:** Brief text description of the weather (e.g., "Partly Cloudy").
* **Precip Type:** Type of precipitation (Rain/Snow).
* **Temperature (C):** Actual measured temperature in Celsius.
* **Apparent Temperature (C):** The "feels like" temperature in Celsius.
* **Humidity:** Relative humidity (0.0 to 1.0).
* **Wind Speed (km/h):** Speed of the wind.
* **Pressure (millibars):** Atmospheric pressure.

## Tools Used 🛠️
The project is implemented in **Python** using the following libraries:
* **Pandas:** For data manipulation, cleaning, and time-series resampling.
* **NumPy:** For numerical operations.
* **Matplotlib:** For generating static visualizations (line charts, histograms, scatter plots).

## Methodology
1.  **Data Loading:** The raw CSV file is loaded into a Pandas DataFrame.
2.  **Data Cleaning:**
    * Converted `Formatted Date` to UTC datetime objects.
    * Removed rows with missing `Precip Type`.
    * Dropped irrelevant columns (e.g., `Loud Cover`).
    * Filtered out anomalies (e.g., rows where Pressure was 0 millibars).
3.  **Statistical Analysis:**
    * Resampled data to calculate **Daily** and **Monthly** averages.
    * Computed a correlation matrix to quantify relationships between variables.
4.  **Visualization:**
    * Generated charts to visualize trends, distributions, and correlations.

## Results & Insights 📊
The analysis produced the following key insights:

### 1. Temperature vs. Humidity Relationship
* **Finding:** There is a distinct **negative correlation (-0.63)** between temperature and humidity.
* **Interpretation:** As expected, warmer weather tends to be associated with lower relative humidity, while colder months are more humid.
* **Visual:** `temp_vs_humidity.png`

### 2. Seasonal Trends
* **Finding:** The 10-year monthly average trend shows a consistent, sinusoidal seasonal pattern.
* **Interpretation:** Weather patterns in this region are stable with predictable seasonal transitions. No drastic long-term warming or cooling trend was observed in this specific 10-year window.
* **Visual:** `monthly_temp_trend.png`

### 3. Apparent vs. Actual Temperature
* **Finding:** These two variables have a near-perfect positive correlation (**0.99**).
* **Interpretation:** The "feels like" temperature tracks the actual temperature very closely on a monthly average basis, with only minor deviations likely caused by wind chill or humidity factors.
* **Visual:** `actual_vs_apparent.png`

## Files in Repository
* `weather_analysis.py`: Main Python script containing all cleaning and plotting code.
* `weatherHistory.csv`: The original raw dataset.
* `cleaned_weather_data.csv`: The processed dataset used for analysis.
* `README.md`: Project documentation.
* `images/`: Folder containing the generated plots (`monthly_temp_trend.png`, etc.).

## How to Run
1.  Ensure you have Python installed.
2.  Install dependencies:
    ```bash
    pip install pandas matplotlib numpy
    ```
3.  Run the analysis script:
    ```bash
    python weather_analysis.py
    ```
4.  Check the generated PNG files for visualizations and the console output for statistical summaries.
