# ✈️ Airline On-Time Performance Analysis (2007)

<p align="center">
  <img src="plots/airplane_header.png" alt="Airplane" width="80%">
</p>

[![Python](https://img.shields.io/badge/Python-3.10-blue.svg)](https://www.python.org/)  
[![Pandas](https://img.shields.io/badge/Library-pandas-informational)](https://pandas.pydata.org/)  
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)  
[![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange)](https://jupyter.org)

---

## 🛫 Overview

This project analyzes the 2007 U.S. Airline On-Time Performance dataset using Apache Hive and SQL on Hadoop, and Python for data visualization. The goal is to uncover patterns in flight delays and cancellations, identify major contributing factors, and highlight problematic routes, airlines, and airports.

---

## 📊 Key Insights

### 1. ⏱️ Delay Patterns

- **Time of Day:**  
  - *Morning flights* had the lowest average delays (**Departure: 5.24 min, Arrival: 4.10 min**).
  - *Evening flights* experienced the highest delays (**Departure: 18.7 min, Arrival: 16.9 min**).

  ![Average Delay by Time of Day](plots/delay_by_timeofday_combined.png)

- **Day of Week:**  
  - *Fridays* had the highest average delays (**Arrival: 13.30 min, Departure: 13.74 min**).
  - *Tuesdays* were most punctual (**Arrival: 8.41 min, Departure: 9.48 min**).

  ![Average Delay by Day of Week](plots/delay_by_dayofweek_combined.png)

- **Month/Season:**  
  - *June and December* had the highest delays (over **15 min**).
  - *May and September* had the lowest delays (**~7–8 min**).
  - *Summer* was the worst season (**Arrival: 14.43 min, Departure: 15.00 min**), while *Autumn* was the best (**Arrival: 5.10 min, Departure: 7.23 min**).

  ![Average Delay by Month](plots/delay_by_month_seasonal.png)

---

### 2. ⛔ Delay Factors

- **Late aircraft delays**: **38%** of total delay minutes.
- **Carrier-related delays**: **28%**.
- **NAS (airspace/traffic control)**: **28%**.
- **Weather**: **5.7%**.
- **Security**: **<0.2%**.

  ![Delay Reasons Breakdown](plots/delay_factors_combined.png)

---

### 3. 🚫 Cancellations

- **Main reasons:**  
  - *Carrier issues*: **22,606 cancellations**  
  - *Weather*: **11,863**  
  - *NAS*: **7,368**  
  - *Security*: **1**

- **By airline:**  
  - *Mesa Airlines* had the highest cancellation rate (**3.72%**).
  - *JetBlue* and *Aloha Airlines* had the lowest (**0.23%** and **0.21%**).

  ![Cancellation Rate by Airline](plots/cancel_by_airline_top10_with_total_flights.png)

- **By airport:**  
  - *Telluride Regional* had the highest origin cancellation rate (**14.81%**).
  - Smaller regional airports showed higher cancellation rates due to low flight volumes.

- **By month:**  
  - *February* had the highest cancellation rate (**1.27%**), *May* the lowest (**0.26%**).

  ![Cancellation Rate by Month](plots/cancel_by_month_dayofweek_combined.png)

---
### 4. 🚨 High-Risk Routes

Top 5 most problematic routes by cancellation rate:

<div align="center">

<table>
  <thead>
    <tr>
      <th>Route</th><th>Airline</th><th>Cancel %</th><th>Avg Delay (Dep/Arr)</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>BWI → EWR</td><td>ExpressJet</td><td>30.56%</td><td>35.2 / 31.8 min</td></tr>
    <tr><td>AZO → ORD</td><td>Skywest</td><td>29.91%</td><td>18.8 / 25.7 min</td></tr>
    <tr><td>DTW → EWR</td><td>Northwest</td><td>26.83%</td><td>33.4 / 44.9 min</td></tr>
    <tr><td>IAD → EWR</td><td>ExpressJet</td><td>26.33%</td><td>38.5 / 32.9 min</td></tr>
    <tr><td>ORF → EWR</td><td>ExpressJet</td><td>25.70%</td><td>42.4 / 40.9 min</td></tr>
  </tbody>
</table>

</div>

> 🚧 Common cause: NAS & Late Aircraft issues

---

## 🔍 Methodology

- **Data Processing:** Apache Hive SQL on Hadoop (via Ambari)
- **Visualization & Analysis:** Python (Pandas, Seaborn, Matplotlib)
- **Statistical Testing:** Levene’s test, Welch’s t-test for group comparisons

---

## ✅ Recommendations

- **Fly in the morning or midweek** for best on-time performance.
- **Avoid peak months** (June, December) and high-cancellation routes.
- **Airlines and airports** should focus on reducing late aircraft and carrier-related delays, and improve scheduling on problematic routes.

---

📂For more plots and visualizations, please see the [plots folder](./plots).

---

## 👨‍🎓 Author 

**Author:** Azrul Zulhilmi Ahmad Rosli | P153478
**Course:** STQD6324 - Data Management (Semester 2 2024/2025)
**Lecturer:** Dr Bernard

## License

This project is for academic purposes. Data source: [Kaggle - Airline On-Time Data](https://www.kaggle.com/datasets/wenxingdi/data-expo-2009-airline-on-time-data/data?select=1993.csv).

---
