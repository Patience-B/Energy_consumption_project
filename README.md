# ⚡ Monitoring Energy Consumption Trends for Homeowners

## 📌 Project Overview
This project helps homeowners **monitor energy consumption trends** and **predict future usage** using data-driven techniques. By combining:

- 🔍 Exploratory Data Analysis (EDA)  
- 📈 Trend Analysis  
- 🤖 Regression Modeling  

it delivers actionable insights to help reduce energy costs and environmental impact.

---

## ❗ Problem Statement
Providing real-time feedback on household energy use can reduce consumption by **5–15%** [2]. However, **tracking trends over time** unlocks even greater value:

- Detecting behavioral and seasonal changes  
- Identifying the impact of new appliances  
- Forecasting future energy costs  
- Setting and tracking energy-saving goals  

---

## 🎯 Objectives
- 📊 **Monitor Energy Trends**  
  Visualize consumption patterns and detect anomalies  

- 🔮 **Predict Future Usage**  
  Build regression models for energy forecasting  

- 💡 **Enable Optimization**  
  Identify key drivers of energy consumption  

---
- ## 📊 The Dataset

- **Dataset Source**: Published research paper [1]
- The dataset contains **time-series measurements** of energy consumption and environmental conditions collected from a low-energy smart home.

---

### 🧾 Feature Description

The dataset includes the following key variables:

- **`date`** → Timestamp of the observation  
- **`Appliances`** → Energy consumption of appliances (Wh) ⚡ *(target variable)*  
- **`lights`** → Energy consumption from lighting (Wh) 💡  

---

### 🌡️ Temperature & Humidity Sensors

Temperature (`T`) and Relative Humidity (`RH`) readings were collected from different locations within the house:

| Feature | Description |
|--------|-------------|
| `T1`, `RH_1` | Temperature & humidity in **Room 1** |
| `T2`, `RH_2` | Temperature & humidity in **Room 2** |
| `T3`, `RH_3` | Temperature & humidity in **Room 3** |
| `T4`, `RH_4` | Temperature & humidity in **Room 4** |
| `T5`, `RH_5` | Temperature & humidity in **Room 5** |
| `T6`, `RH_6` | Temperature & humidity in **Room 6** |
| `T7`, `RH_7` | Temperature & humidity in **Room 7** |
| `T8`, `RH_8` | Temperature & humidity in **Room 8** |
| `T9`, `RH_9` | Temperature & humidity in **Room 9** |


---

### 🌍 Outdoor & Environmental Features

| Feature | Description |
|--------|-------------|
| `T_out` | Outdoor temperature (°C) |
| `RH_out` | Outdoor humidity (%) |
| `Press_mm_hg` | Atmospheric pressure (mm Hg) |
| `Windspeed` | Wind speed (m/s) |
| `Visibility` | Visibility (km) |
| `Tdewpoint` | Dew point temperature (°C) |

---

### 🔁 Random Variables

| Feature | Description |
|--------|-------------|
| `rv1`, `rv2` | Random variables (included for benchmarking and testing model robustness) |

---

### 🏠 Sensor Placement

Below is the layout of sensors on **Floor 1** (adapted from the original paper):

![Location of Sensors Floor 1](floor1_layout.png)

Below is the layout of sensors on **Floor 2** (adapted from the original paper):

![Location of Sensors Floor 2](floor2_layout.png)


---

### 💡 Key Notes

- The dataset is **multivariate and time-dependent**, making it suitable for:
  - Time-series analysis  
  - Regression modeling  
  - Feature importance studies  

- Indoor environmental conditions (temperature & humidity) are expected to influence **energy consumption patterns**, particularly heating, cooling, and appliance usage.

---
- Here are the the images from where the different sensors were located. These images were picked from the published papers.
- ![Location of Sensors Floor 1](floor1_layout.png)

--- 
## 🛠️ Methodology

### 🔍 1. Exploratory Data Analysis (EDA)

- **Analysis Types**:
  - **Univariate**:  
    `Appliances`, `lights`, `T1`, `RH_1`, `Press_mm_hg`, `date`
  - **Bivariate**:  
    Relationship between `Appliances` and environmental variables like:
    - 🌡️ Temperature (`T1`)  
    - 💧 Humidity (`RH_1`)  

---

### 📈 2. Energy Consumption Trend Analysis
- Created a time-based dataset using:
  - `hour`, `day`, `week`, `month`

#### Key Visualizations:
- ⏰ Hourly Trends  
- 📅 Daily & Weekly Patterns  
- 🗓️ Monthly Consumption  
- 📊 Interactive Time Series (for anomaly detection)

---

### 🤖 3. Regression Modeling

#### 🔧 Data Preprocessing
- Normalization using **MinMaxScaler**

#### 🧠 Models Built
1. **Model 1 (Baseline)**  
   - All features except `Appliances`, `lights`, `date`

2. **Model 2 (PCA-Based)**  
   - Components explaining **95% variance**

3. **Model 3 (Feature Selection)**  
   - `SelectKBest` algorithm

#### 📏 Evaluation Metrics
- RMSE (Root Mean Squared Error)  
- R² Score  

---

## 📊 Results

### 🔍 EDA Insights
- Strongest correlation: `Appliances` ↔ `lights`  
- Weak correlations with:
  - Temperature (`T1`)  
  - Humidity (`RH_1`)  
- Notable relationships with:
  - `T2` and `T6` (temperature features)

---

### 🤖 Model Performance
| Model | Description | Performance |
|------|------------|------------|
| Model 1 | Baseline Linear Regression | ✅ Best |
| Model 2 | PCA-Based | Moderate |
| Model 3 | SelectKBest | Moderate |

- **Best Model**: Model 1  
  - RMSE: `93.64`  
  - R²: `0.1489`  

- **Key Insight**:  
  Temperature features significantly influence energy consumption.

---

### 📈 Trend Insights
- 🌙 **Evening Peaks** → Highest energy usage  
- 📆 **Mid-Month Increase** → Noticeable spikes  
- 📉 **Monthly Decline** → Lowest consumption in May  

---

## 💭 Discussion & Reflection
Tracking energy consumption trends enables homeowners to:

- Make **data-driven decisions**  
- Reduce **energy costs**  
- Adopt **sustainable habits**  

This project demonstrates how combining **EDA**, **trend analysis**, and **machine learning** can transform raw data into meaningful, actionable insights.

---

## 📚 References
1. Luis C, Véronique F, Dominique D,  
   *Data-driven prediction models of energy use of appliances in a low-energy house*, Elsevier, 2017.  

2. João J, João P, Mário N,  
   *Home Electric Energy Monitoring System: Design and Prototyping*, ResearchGate, 2011.  

---

## 🚀 Future Improvements
- Integrate real-time IoT energy data  
- Deploy as a web dashboard  
- Explore advanced models (e.g., Random Forest, XGBoost)  
- Add personalized energy-saving recommendations  

---

## 👩‍💻 Author
Developed as part of a data-driven exploration into **energy efficiency and sustainability**.
