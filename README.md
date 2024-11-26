# Monitoring Energy Consumption Trends for Homeowners

## Project Summary
This project aims to assist homeowners in monitoring their energy consumption trends over time and accurately predicting future energy usage. Through **exploratory data analysis (EDA)**, **energy consumption trend analysis**, and **regression modeling**, the project provides insights that allow homeowners to optimize their energy usage, save money, and reduce their environmental impact.

## Problem Definition
Providing real-time feedback on household energy consumption has been shown to influence consumer habits, leading to a 5-15% reduction in usage [[2]](#references). Tracking energy consumption over time offers even greater benefits, such as identifying shifts in usage due to new appliances or seasonal changes, setting and tracking energy reduction goals, and benchmarking against similar households. Monitoring trends allows homeowners to forecast future costs, budget accordingly, and assess the effectiveness of energy-saving strategies.

## Project Objectives
The main objectives of this project are:
- **Monitoring Energy Consumption Trends**: Enable homeowners to visualize consumption patterns and identify any anomalies or seasonal changes.
- **Predicting Future Energy Usage**: Use regression models to provide accurate energy consumption forecasts.
- **Providing Insights for Optimization**: Identify factors influencing energy use to help homeowners make informed decisions to reduce consumption.

## Methodology

### 1. Exploratory Data Analysis (EDA)
- **Dataset**: The data used for this project was obtained from a published paper [[1]](#references).
- **Analyses**: Both univariate and bivariate analyses were conducted to understand feature distributions and relationships.
  - **Univariate Analysis**: Focused on features including `Appliances`, `lights`, `T1`, `RH_1`, `Press_mm_hg`, and `date`.
  - **Bivariate Analysis**: Explored correlations between `Appliances` (main energy indicator) and environmental variables like room temperature (`T1`) and humidity (`RH_1`).

### 2. Energy Consumption Trend Analysis
A new data frame containing the `date` and `Appliances` features was created to analyze trends. From the timestamp, additional columns for `hour`, `day`, `week`, and `month` were derived to enable granular trend analysis. Various plots were used to visualize patterns, such as:
- **Hourly, Daily, Weekly, and Monthly Consumption**: Peak usage was observed in the evenings and mid-month.
- **Interactive Time Series Plot**: Allows users to highlight specific time frames, aiding in the detection of trends and anomalies.

### 3. Regression Model Selection
- **Data Preprocessing**: MinMaxScaler was used to normalize the data for feature selection and model training.
- **Modeling**: Three linear regression models were constructed:
  - **Model 1**: Utilized all features except `Appliances`, `lights`, and `date`.
  - **Model 2**: Used features derived from Principal Component Analysis (PCA) retaining components that explained 95% of variance.
  - **Model 3**: Selected features using the `SelectKBest` algorithm.
- **Model Comparison**: Models were compared based on RMSE and R² scores, with the first model demonstrating superior performance.

## Results

### Exploratory Data Analysis
The `Appliances` feature had the highest correlation with `lights`. However, weak correlations were observed with environmental variables such as `T1` and `RH_1`. The highest correlations aside from `lights` were observed between `Appliances` and temperature-related features (`T2` and `T6`).

### Regression Model Selection
The **fundamental linear regression model** (Model 1) performed best, achieving an RMSE of 93.64 and an R² score of 0.1489. **SelectKBest** identified temperature features as influential, indicating temperature can effectively predict energy consumption.

### Energy Consumption Trend Analysis
- **Evening Peaks**: Energy consumption was highest in the evenings.
- **Mid-Month Increases**: Energy use tended to rise mid-month.
- **Monthly Decline**: Energy use decreased over months, with May showing the lowest values.

## Discussion and Reflection
Monitoring energy trends over time provides homeowners with actionable insights to reduce energy use and costs. By leveraging EDA, trend analysis, and regression modeling, this project empowers homeowners with tools to monitor patterns, predict usage, and make data-driven adjustments. Ultimately, this can motivate homeowners to adopt sustainable energy habits, contributing to cost savings and environmental sustainability.

## References
1. Luis C, Véronique F, Dominique D, “Data-driven prediction models of energy use of appliances in a low-energy house,” *Elsevier*, 2017.
2. João J, João P, Mário N, “Home Electric Energy Monitoring System: Design and Prototyping,” *Research Gate*, 2011.
