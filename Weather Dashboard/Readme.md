# 🌦 Weather Dashboard – Power BI

A visually appealing weather analytics dashboard built using Power BI.  
It provides current weather conditions and forecast insights such as temperature trends, rain chances, air quality, humidity, and more.

---

## 📌 Features

- **Current Weather Card** → shows temperature, condition, city, and last updated time.  
- **Forecast Weather Line Chart** → displays min, max, and avg temperatures across days.  
- **Donut Chart (Humidity vs Cloud)** → visual breakdown of current conditions.  
- **Chance of Rain (Bar Chart)** → daily rain probabilities.  
- **Sunrise & Sunset Panel** → dynamically updates per day.  

---

## 🧮 DAX Measures

### Current Weather

- **Curr_Temp_C** = SUM('Current'[current.temp_c]) & " °C"
- **Curr_Temp_F** = SUM('Current'[current.temp_f]) & " °F"
- **last_update** = "Last Updated, " & FORMAT(FIRSTNONBLANK('Current'[current.last_updated], ""), "dd mmm") 
- **Humidity** = SUM('Current'[current.humidity]) & " %"
- **Wind_Speed** = SUM('Current'[current.wind_kph]) & " Kph"
- **Visibility** = SUM('Current'[current.vis_km]) & " KM"
- **Pressure** = SUM('Current'[current.pressure_mb]) & " mm"
- **UV_Index** = SUM('Current'[current.uv])
-  **Precipitation** = SUM('Current'[current.precip_mm]) & " mm"

### ✅ Forecast Insights (Future Days)

📊 Average Temperature (°C)

For_Temp_C = AVERAGE(Forcast_Day[forecast.forecastday.day.avgtemp_c]) & " °C"


🌧 Rain Probability

Left_Rain_Chance = 100 - SUM(Forcast_Day[forecast.forecastday.day.daily_chance_of_rain])

### 🚀Tech Stack

Power BI – data visualization & dashboards

DAX – custom measures & calculations

Weather Data – Current and Forecast_Day tables

### 👩‍💻 Connect with Me
- **LinkedIn**- www.linkedin.com/in/sai-subhashree-14681520b 
- **EmailID** -saidalal02@gmail.com

<img width="1205" height="669" alt="image" src="https://github.com/user-attachments/assets/a9ed5578-948b-4a21-abb0-de839fce870c" />



