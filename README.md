# Air Quality Index (AQI) Analysis – Delhi, January 2023  

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
import plotly.express as px
import plotly.io as pio
import plotly.graph_objects as go
pio.templates.default = "plotly_white"

data = pd.read_csv('delhiaqi.csv')
print(data)

# Time Series Plot for each Air Pollutant
fig = go.Figure()

for pollutant in ['co','no', 'no2','o3','so2','pm2_5','pm10','nh3']:
    fig.add_trace(go.Scatter(x=data['date'], y=data[pollutant], mode='lines', name=pollutant))

fig.update_layout(title='Time Series Analysis for Air Pollution in Delhi', xaxis_title='Date', yaxis_title='Concentration (µg/m³)')
fig.show()
