# 🌍 Air Quality Index (AQI) Analysis – Delhi, January 2023  

## 📌 Project Overview  
This project analyzes the **Air Quality Index (AQI)** in **Delhi (January 2023)** using time-series analysis, pollutant correlation, and AQI computation.  
The objective is to uncover **pollution patterns, weekly/daily trends, and health risks** associated with poor air quality.  

---

## 📊 Dataset  
The dataset contains hourly air quality measurements with the following features:  

- **date** – Date and time of measurement  
- **co** – Carbon Monoxide (µg/m³)  
- **no** – Nitric Oxide (µg/m³)  
- **no2** – Nitrogen Dioxide (µg/m³)  
- **o3** – Ozone (µg/m³)  
- **so2** – Sulfur Dioxide (µg/m³)  
- **pm2_5** – Particulate Matter (PM2.5) (µg/m³)  
- **pm10** – Particulate Matter (PM10) (µg/m³)  
- **nh3** – Ammonia (µg/m³)  

---

## 🔎 Analysis Performed  

- ✅ **AQI Calculation** – Computed AQI from pollutant concentrations  
- ✅ **AQI Distribution** – Categorized air quality (Good, Moderate, Unhealthy, etc.)  
- ✅ **Time-Series Analysis** – Hourly, daily, and weekly AQI patterns  
- ✅ **Hourly Trends** – Identified **peak pollution hours**  
- ✅ **Weekly AQI** – Compared average AQI by day of week  
- ✅ **Correlation Study** – Explored relationships between pollutants  

---

## 📈 Visualizations  

### 1️⃣ AQI Distribution in January  
AQI values were classified into standard categories (Good, Moderate, Unhealthy, etc.)  

![AQI Distribution](https://github.com/Jericho0015/Air-Quality-Index-AQI-Analysis/blob/main/Visualizations%20Graphs/AQI_category_distribution_Over_Time.PNG)  

---

### 2️⃣ Hourly Average AQI Trends  
Average AQI was calculated for each hour of the day to detect **peak pollution hours**.  

![Hourly AQI](https://github.com/Jericho0015/Air-Quality-Index-AQI-Analysis/blob/main/Visualizations%20Graphs/Hourly_Avg_AQI_Trends_in_Delhi.PNG)  

---

### 3️⃣ Average AQI by Day of Week  
The analysis revealed that **Wednesdays and Thursdays had the worst air quality**.  

![Weekly AQI](https://github.com/Jericho0015/Air-Quality-Index-AQI-Analysis/blob/main/Visualizations%20Graphs/Avg_AQI_in_Week.PNG)  

---

### 4️⃣ Correlation Heatmap of Pollutants  
A heatmap showed strong correlation between **PM2.5 and PM10**, highlighting their dominant role in AQI.  
![Correlation Heatmap](https://github.com/Jericho0015/Air-Quality-Index-AQI-Analysis/blob/main/Visualizations%20Graphs/Correlations_between_pollution.PNG)  

---

## 🔑 Key Findings  

- 🚨 **Air quality is worse on Wednesdays and Thursdays**  
- 🌆 **Peak pollution hours**: early morning & evening  
- 💨 **PM2.5 & PM10 strongly correlated**, driving AQI values  
- 📉 Most days in January fell into **“Unhealthy” AQI categories**  

---

## 🛠️ Tools & Libraries  

- **Python** – Pandas, NumPy  
- **Visualization** – Matplotlib, Seaborn  
- **Analysis** – Time-Series, Correlation, AQI Computation  

---

## 🧩 Example Code Snippet  

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load dataset
df = pd.read_csv("delhi_air_quality.csv", parse_dates=["date"])

# Calculate daily AQI average
daily_aqi = df.groupby(df["date"].dt.date)["pm2_5"].mean()

# Plot daily AQI
plt.figure(figsize=(10,5))
plt.plot(daily_aqi.index, daily_aqi.values, marker='o')
plt.title("Daily Average AQI - Delhi (Jan 2023)")
plt.xlabel("Date")
plt.ylabel("AQI (PM2.5 concentration)")
plt.xticks(rotation=45)
plt.savefig("plots/daily_aqi.png")
plt.show()
