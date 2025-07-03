# Weather-Data-Collection-Data-Pipeline
Fully automated and scalable data pipeline to collect, process, store, and visualize real-time weather data

This project presents a fully automated and scalable **data pipeline** to collect, process, store, and visualize real-time weather data using **Python**, **Databricks**, and **Delta Lake**. The pipeline fetches weather metrics from a public API, transforms and cleans the data, stores it for historical tracking, and triggers real-time alerts for extreme conditions.

---

## 📌 Project Objectives

- 🔁 **Automate** the collection of weather data from a public API
- 🧹 **Clean**, structure, and validate incoming data
- 🏪 **Store** weather data in **Delta Lake** for efficient querying and updates
- 📊 **Visualize** trends using dashboards (temperature variation, real-time heatmaps)
- 🚨 **Trigger alerts** for adverse conditions like heatwaves or storms

---

## 🌍 Dataset Source

- **API**: [OpenWeatherMap](https://openweathermap.org/api) or similar
- **Collected Fields**:
  - `City Name`
  - `Temperature`
  - `Weather Description` (e.g., clear, rainy)
  - `Timestamp`

Data is collected **at regular intervals** using scheduling libraries and stored in **Delta Lake tables** on Databricks.

---

## 🔧 Technologies Used

| Tool          | Purpose                                       |
|---------------|-----------------------------------------------|
| Python        | Core logic and API handling                  |
| Databricks    | Development environment + Spark + Delta Lake |
| Delta Lake    | Efficient data storage with schema evolution |
| Pandas        | Initial data formatting and transformation   |
| PySpark       | Scalable processing and querying             |
| SQL & Dashboards | Visualization and analysis               |
| schedule      | Triggering repeated API fetches              |
| requests      | Fetching API responses                       |

---

## 🔁 Pipeline Architecture

### 1. **Data Collection**
- Uses `requests` to access the weather API
- Scheduled via the `schedule` library to run periodically

### 2. **Data Transformation**
- Raw data → Pandas DataFrame → Spark DataFrame
- Cleansing:
  - Drop nulls
  - Remove unnecessary fields
  - Enforce consistent schema

### 3. **Error Handling**
- Retry logic on API failure
- Logs generated at every step
- Monitoring enabled for pipeline health

### 4. **Storage**
- Data written to **Delta Lake tables** in Databricks for historical tracking and real-time access

### 5. **Visualization**
- Heatmaps for temperature variation
- Real-time dashboards for:
  - Hottest/coldest cities
  - Alerts for extreme conditions
  - Update counters per city

---

## 📈 Key Observations

- 🌡️ Major daily temperature fluctuations were recorded in specific cities
- 🚨 Real-time **alerts** triggered for extreme weather conditions (e.g., heatwaves)
- 🗺️ **Heatmaps** revealed region-specific weather volatility
- 📊 Live counters provided up-to-date insights per city

---

## ✅ Results

- Pipeline automated to fetch and store weather data at intervals
- Dashboards enabled rapid decision-making for:
  - Disaster response
  - Urban planning
  - Agricultural scheduling
- Real-time alerts improved proactive responses to extreme weather events

---

Run it locally or on Databricks

