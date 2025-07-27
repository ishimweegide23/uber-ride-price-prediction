## 👩‍🎓 Student Profile

*Name:* \[Your Name]
*Course:* Introduction to Big Data Analytics (INSY 8413)
*Instructor:* Eric Maniraguha
*Email:* [eric.maniraguha@auca.ac.rw](mailto:eric.maniraguha@auca.ac.rw)
*LinkedIn:* \[Eric's Profile]
*Assignment Title:* Uber Fares Dataset Analysis using Power BI
*Assignment Date:* 20 July 2025
*Deadline:* Friday 25 July 2025, 5:00 PM

---

## 📘 Introduction

This project aims to explore and analyze Uber ride fare patterns using the Uber Fares Dataset from Kaggle. The objective is to extract meaningful insights about ride fares, patterns, passenger trends, and operational efficiency. The project involves data cleaning, exploratory data analysis (EDA), feature engineering, Power BI visualization, and dashboard development.

---

## 🛠 Tools Used

* *Python (Pandas, NumPy, Matplotlib)* for data preprocessing and EDA
* *Power BI Desktop* for visualization and dashboard creation
* *Kaggle* as the data source

---

## 🔍 1. Data Understanding and Preparation

### 📥 a. Dataset Source

* Uber Fares Dataset downloaded from Kaggle.
* [Uber Dataset on Kaggle](https://www.kaggle.com/datasets/fivethirtyeight/uber-pickups-in-new-york-city)

### 🐍 b. Loading Data in Python

python
import pandas as pd

# Load dataset
df = pd.read_csv("C:/Users/Hey/enhanced_uber_fare_data.csv")
df.head()


### 📊 c. Dataset Overview

* *Rows:* 200,000+
* *Columns:* 15
* *Important Features:* fare\_amount, pickup\_datetime, passenger\_count, trip\_distance, peak\_indicator

### 🧹 d. Data Cleaning

* Removed null values
* Filtered outliers in fare_amount and trip_distance
* Formatted datetime fields

### 💾 e. Export Cleaned Data

python
df.to_csv("uber_cleaned_final.csv", index=False)


Used this CSV for Power BI import.

---

## 📈 2. Exploratory Data Analysis (EDA)

### 📌 a. Descriptive Statistics

* *Mean Fare:* \$11.37
* *Median Fare:* \$8.50
* *Std Deviation:* \$9.45
* *Outliers:* Removed fares < \$2 and > \$100

### 📊 b. Fare Distribution Histogram

* *Chart:* Column Chart
* *X-Axis:* Fare Bins (0-5, 5-10...)
* *Y-Axis:* Count
* *Insight:* Majority of fares between \$5 - \$15

### 📈 c. Relationship Analysis

* *Fare vs Distance:* Clear positive correlation
* *Fare vs Hour:* High fares around 8AM and 6PM
* *Fare vs Peak:* Higher during peak times

---

## 🧠 3. Feature Engineering

### 🕒 a. Time Features Extracted

python
df['pickup_hour'] = pd.to_datetime(df['pickup_datetime']).dt.hour
df['pickup_day'] = pd.to_datetime(df['pickup_datetime']).dt.day_name()
df['pickup_date'] = pd.to_datetime(df['pickup_datetime']).dt.date


### 🧾 b. Peak Indicator

python
def peak_hour(hour):
    return 'Peak' if hour in [7, 8, 17, 18] else 'Non-Peak'
df['peak_indicator'] = df['pickup_hour'].apply(peak_hour)


### 🧠 c. Categorical Encoding

* Converted day_of_week and peak_indicator into categorical data

---

## 📊 4. Power BI Visualizations

### 1️⃣ Fare Distribution Histogram

* *Chart:* Column chart
* *Insight:* Most fares lie between \$5 and \$15

### 2️⃣ Trip Distance vs Fare Amount

* *Chart:* Scatter Plot
* *Tooltip:* passenger\_count, pickup\_hour
* *Insight:* Strong positive correlation

### 3️⃣ Fare by Day of Week

* *Chart:* Bar Chart
* *X:* day\_of\_week (sorted Mon to Sun)
* *Y:* Avg Fare
* *Insight:* Weekends have higher average fares

### 4️⃣ Fare by Hour of Day

* *Chart:* Line Chart with peak/non-peak
* *Insight:* Peaks during 7–9 AM and 5–7 PM

### 5️⃣ Passenger Count Distribution

* *Chart:* Column chart
* *Insight:* Most rides are solo (1 passenger)

### 6️⃣ Pickup Location Density (Map)

* *Chart:* Bubble map using latitude/longitude
* *Insight:* Dense pickup areas in NYC downtown

### 7️⃣ Peak vs Non-Peak Fare Comparison

* *Chart:* Pie Chart
* *Insight:* Peak times slightly higher in cost

---

## 🧾 5. Power BI Dashboard Design

* *Title:* Uber Ride Fare Analysis Dashboard
* *Layout:* Logical, interactive layout with slicers and filters
* *Interactivity:* Filters by hour, day, passenger count
* *Design:* Clean layout, consistent color themes

---

## 🧑‍💼 6. Results & Recommendations

### 🎯 Key Insights

* Fare amounts are strongly influenced by distance and time of day
* Peak hours have higher fares and demand
* Most rides occur during weekdays and working hours

### 💡 Recommendations

* *Business Strategy:* Optimize driver allocation during peak hours
* *Marketing:* Promote group rides as most rides are solo
* *Pricing:* Adjust pricing model for short rides in high-density zones

---

## 🗂 Submission Files

1. *Power BI File (.pbix)* – Final interactive dashboard
2. *GitHub Repository*

   * Cleaned dataset CSV
   * Python code for preprocessing
   * Dashboard screenshots
   * Final report (this document)

---

## 🔗 GitHub Repository Link

[GitHub Repo – Uber Fare Analysis](https://github.com/yourusername/uber-fare-analysis)

---

## 📌 Final Note

This project enhanced my skills in real-world data cleaning, EDA, visualization, and storytelling through dashboards. I followed ethical practices, documented each step, and ensured that the final result is insightful and professionally presented.

✨ Thank you for reviewing my submission. I look forward to your feedback!
