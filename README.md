# 🚕 Uber Fares Dataset Analysis using Python & Power BI

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![Power BI](https://img.shields.io/badge/Power%20BI-Analysis-yellow.svg)](https://powerbi.microsoft.com)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-green.svg)](https://pandas.pydata.org)

**Course:** Introduction to Big Data Analytics (INSY 8413)  
**Instructor:** Eric Maniraguha  
**Student:** Ishimwe Egîdë – AUCA  
**Submission Date:** 25 July 2025

## 📋 Table of Contents

- [Overview](#overview)
- [Dataset Description](#dataset-description)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Data Preprocessing](#data-preprocessing)
- [Analysis & Insights](#analysis--insights)
- [Power BI Visualizations](#power-bi-visualizations)
- [Key Findings](#key-findings)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This project analyzes Uber ride fare data to identify trends and patterns that can inform business decisions. Using Python for data preprocessing and exploratory analysis, combined with Power BI for interactive visualizations, we explore factors such as:

- Pickup time patterns
- Geographic distribution
- Passenger behavior
- Fare pricing trends
- Seasonal demand variations

The insights derived support dynamic pricing strategies and operational improvements for ride-sharing services.

## 📊 Dataset Description

| Field | Description |
|-------|-------------|
| `pickup_datetime` | Date and time of ride pickup |
| `pickup_latitude` | Latitude coordinate of pickup location |
| `pickup_longitude` | Longitude coordinate of pickup location |
| `dropoff_latitude` | Latitude coordinate of dropoff location |
| `dropoff_longitude` | Longitude coordinate of dropoff location |
| `passenger_count` | Number of passengers |
| `fare_amount` | Total fare amount |
| `trip_distance` | Distance of the trip |
| `Time_of_Booking` | Time category of booking |
| `Peak_Indicator` | Whether trip occurred during peak hours |
| `day_of_week` | Day of the week |
| `season` | Season (engineered feature) |
| `Total_Trips` | Trip count (engineered feature) |

## 🛠 Prerequisites

- Python 3.8+
- Power BI Desktop
- Required Python libraries (see Installation)

## 📦 Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/uber-fares-analysis.git
cd uber-fares-analysis
```

2. Install required Python packages:
```bash
pip install pandas matplotlib seaborn numpy
```

3. Download the dataset and place it in the project directory as `uber_dataset.csv`

## 🧹 Data Preprocessing

The data preprocessing pipeline includes:

### Data Cleaning
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load and clean data
df = pd.read_csv("uber_dataset.csv")
df['pickup_datetime'] = pd.to_datetime(df['pickup_datetime'])

# Remove nulls and duplicates
df.dropna(inplace=True)
df.drop_duplicates(inplace=True)
```

### Feature Engineering
```python
# Extract time-based features
df['pickup_hour'] = df['pickup_datetime'].dt.hour
df['day_of_week'] = df['pickup_datetime'].dt.day_name()

# Create seasonal categories
df['season'] = df['pickup_datetime'].dt.month.map({
    12: 'Winter', 1: 'Winter', 2: 'Winter',
    3: 'Spring', 4: 'Spring', 5: 'Spring',
    6: 'Summer', 7: 'Summer', 8: 'Summer',
    9: 'Fall', 10: 'Fall', 11: 'Fall'
})

# Calculate trip counts
df['Total Trips'] = 1
```

## 🔍 Analysis & Insights

### Peak Hours Analysis
**Question:** What are the busiest hours for Uber pickups?

```python
df.groupby('pickup_hour')['Total Trips'].sum().plot(kind='bar', figsize=(10,5))
plt.title("Total Uber Pickups by Hour")
plt.xlabel("Hour of Day")
plt.ylabel("Total Trips")
plt.show()
```

**Result:** Peak hours identified between 7-9 AM and 5-7 PM, correlating with work commute times.

### Seasonal Demand Analysis
**Question:** How do seasonal trends affect Uber demand?

Analysis conducted using Power BI clustering and time-series visualization.

## 📈 Power BI Visualizations

### 1. 🌤️ Seasonal Demand Analysis
- **Chart Type:** Clustered Column Chart
- **Axes:** Season (X) vs Total Trips (Y)
- **Filters:** Day of week, Hour, Peak indicator
- **Insight:** Summer and Fall show highest demand

### 2. ⏰ Hourly Pickup Distribution
- **Chart Type:** Bar Chart
- **Axes:** Hour (X) vs Total Trips (Y)
- **Insight:** Clear peaks during commute hours

### 3. 📍 Geographic Distribution
- **Chart Type:** Map Visualization
- **Fields:** Pickup/Dropoff coordinates
- **Insight:** High density in urban centers

### 4. 💰 Fare Analysis by Time
- **Chart Type:** Line Chart
- **Axes:** Time of Booking (X) vs Average Fare (Y)
- **Insight:** Higher fares during evening hours

### 5. 👥 Passenger Group Analysis
- **Chart Type:** Donut Chart
- **Field:** Passenger Count
- **Insight:** Majority are solo or two-passenger trips

### Interactive Filters
- Season
- Day of week
- Pickup hour
- Peak indicator
- Time of booking
- Passenger count
- Trip distance

## 🎯 Key Findings

| Finding | Business Impact |
|---------|----------------|
| 🕐 **Peak Hours:** 7-9 AM & 5-7 PM | Optimize driver allocation during commute times |
| 💲 **Higher Evening Fares** | Implement dynamic pricing strategies |
| 🌞 **Summer/Fall Peak Demand** | Seasonal marketing and capacity planning |
| 🏙️ **Urban Concentration** | Focus resources on high-density areas |
| 👤 **Solo/Duo Trips Dominant** | Vehicle type optimization |

## 🚀 Usage

1. **Data Analysis:**
   ```bash
   python data_preprocessing.py
   python exploratory_analysis.py
   ```

2. **Power BI Dashboard:**
   - Open `uber_analysis.pbix` in Power BI Desktop
   - Refresh data connections
   - Interact with filters and slicers

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Contact

**Ishimwe Egîdë**  
African University College of Agriculture (AUCA)  
Email: [your.email@example.com](mailto:your.email@example.com)

## 🙏 Acknowledgments

- Eric Maniraguha - Course Instructor
- AUCA - African University College of Agriculture
- Uber - For providing the dataset structure reference

---

⭐ **Star this repository if you found it helpful!**
