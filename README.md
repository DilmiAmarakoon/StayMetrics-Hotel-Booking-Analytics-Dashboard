# 🏨 StayMetrics – Hotel Booking Analytics Dashboard

An interactive hotel booking and performance analytics dashboard developed using Microsoft Excel to transform raw reservation records into actionable business insights.

## 📌 Project Overview

StayMetrics analyzes 119,390 hotel booking records from two hotels in Portugal: a City Hotel and a Resort Hotel. The dashboard explores reservation patterns, cancellations, estimated room revenue, customer segments and seasonal trends through a single interactive interface.

## 🎯 Business Objectives

- Monitor hotel booking performance and cancellation rates.
- Identify seasonal demand patterns and high-revenue arrival months.
- Compare City Hotel and Resort Hotel reservations.
- Understand customer composition, geographic markets and booking channels.
- Support data-driven marketing, reservation management and resource planning.

## 🛠️ Tools & Technologies

- **Microsoft Excel** – Dashboard development and reporting
- **Power Query** – Data cleaning, transformation and feature engineering
- **Power Query M** – Custom calculated columns
- **PivotTables** – Data aggregation and KPI calculations
- **PivotCharts** – Interactive data visualization
- **GETPIVOTDATA & Excel formulas** – Dynamic KPI calculations
- **Slicers** – Interactive filtering across connected PivotTables

## 📂 Dataset

| Attribute | Details |
|---|---|
| Dataset | Hotel Booking Demand |
| Source | Kaggle |
| Records | 119,390 |
| Original columns | 32 |
| Engineered columns | 9 |
| Final columns | 41 |
| Period | July 2015 – August 2017 |
| Hotel types | City Hotel and Resort Hotel |
| Location | Portugal |

Dataset: [Hotel Booking Demand on Kaggle](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand)

Original research: Antonio, N., de Almeida, A., & Nunes, L. (2019). *Hotel booking demand datasets*. Data in Brief, 22, 41–49. [DOI: 10.1016/j.dib.2018.11.126](https://doi.org/10.1016/j.dib.2018.11.126).

## 🧹 Data Preprocessing

- Imported CSV data into Power Query and profiled the entire dataset.
- Checked missing values, conversion errors and data types.
- Replaced missing child counts with zero as an analytical assumption.
- Replaced unavailable country values with `Unknown` and unavailable agent/company IDs with zero as a placeholder.
- Flagged negative ADR values and rates above 1,000 for review.
- Retained zero-rate bookings and original booking records rather than automatically deleting apparent duplicates.

## ⚙️ Feature Engineering

| Feature | Description |
|---|---|
| ADR_Quality | Flags negative rates and potential outliers |
| Total_Guests | Adults + children + babies |
| Total_Nights | Weekday + weekend nights |
| Estimated_Revenue | ADR × total nights for eligible completed stays |
| Booking_Status | Cancelled or Not Cancelled |
| Arrival_Date | Combined year, month and day |
| Guest_Type | Solo, Couple, Family, Group or Invalid |
| Lead_Time_Category | Booking lead-time bands |
| Stay_Duration_Category | Length-of-stay bands |

## 📊 Key Performance Indicators

Unfiltered dashboard results:

| KPI | Value |
|---|---:|
| Total Bookings | 119,390 |
| Non-cancelled Bookings | 75,166 |
| Cancelled Bookings | 44,224 |
| Cancellation Rate | 37.04% |
| Estimated Room Revenue | 25,986,976.03 |
| Average Recorded Daily Rate | 101.83 |

Cancellation rate = cancelled bookings ÷ total bookings × 100.

Estimated revenue includes records with Check-Out status, normal ADR flags and positive guest counts. ADR is averaged across booking records, including cancelled bookings; it is not a weighted realized hotel ADR.

## 📈 Dashboard Visualizations

| Visualization | Chart type |
|---|---|
| Bookings by Hotel Type | Doughnut chart |
| Booking Cancellation Analysis | Doughnut chart |
| Monthly Booking Trend | Line chart |
| Monthly Estimated Revenue | Column chart |
| Bookings by Guest Type | Column chart |
| Bookings by Market Segment | Horizontal bar chart |
| Top 10 Countries by Bookings | Horizontal bar chart |

## 🎛️ Interactive Features

- Year filter (2015, 2016 and 2017)
- Hotel Type filter
- Market Segment filter
- Guest Type filter
- Dynamic KPI cards and connected PivotCharts
- Combined filter selections and clear-filter controls

## 🖼️ Dashboard Preview

![StayMetrics Dashboard](Screenshots/Dashboard_Overview.png)

## 💡 Key Business Insights

- City Hotel recorded 79,330 bookings, compared with 40,060 for Resort Hotel, representing approximately two-thirds of all reservations.
- Around 37% of reservations were cancelled, highlighting the importance of cancellation monitoring and demand planning.
- Online travel agencies were the leading booking segment in the dashboard.
- Portugal was the leading customer country by booking volume.
- The two-adult, no-child guest category (labelled Couple) dominated guest-type bookings.
- Monthly trends reveal seasonal variation in arrivals and estimated revenue.

## 👥 Stakeholders & Recommendations

| Stakeholder | Potential use |
|---|---|
| Hotel management | Monitor overall demand and financial performance |
| Revenue management | Investigate seasonal pricing and cancellation patterns |
| Marketing teams | Target promising customer segments and geographic markets |
| Reservation teams | Review cancellation exposure and booking-channel performance |
| Operations teams | Use arrival and stay patterns to inform staffing and planning |

## 🔄 Project Workflow

```text
Raw CSV Dataset
       ↓
Power Query: Profiling & Cleaning
       ↓
Feature Engineering
       ↓
Cleaned Excel Table
       ↓
PivotTables & KPI Calculations
       ↓
PivotCharts & Interactive Slicers
       ↓
Dashboard & Business Insights
```

## 📁 Project Structure

```text
StayMetrics/
├── Dashboard/
│   └── StayMetrics_Dashboard.xlsx
├── Dataset/
│   └── hotel_bookings.csv
├── Documentation/
├── Screenshots/
│   └── Dashboard_Overview.png
└── README.md
```

## 🚀 How to Use

1. Clone or download this repository.
2. Open `Dashboard/StayMetrics_Dashboard.xlsx` in Microsoft Excel Desktop.
3. Navigate to the `Dashboard` worksheet.
4. Use the slicers to explore booking patterns and performance.
5. Clear the slicers to restore the overall view.
6. To refresh the source data, download the original CSV if needed and update the Power Query source path to your local dataset location, then select **Data → Refresh All**.

## ⚠️ Limitations

- The dataset covers only two hotels and a historical period; it does not represent the entire hotel industry.
- Revenue is estimated, not verified accounting revenue. Monthly revenue is grouped by arrival month.
- The ADR screening threshold and guest/lead-time/stay categories are project-defined analytical rules.
- Missing child counts replaced with zero may introduce minor bias. Guest categories do not establish actual relationships between travelers.
- The dashboard does not calculate true occupancy or RevPAR because available room inventory is not provided.
- The dataset is not a live booking feed; updates require refreshing the source data.

## 🎓 Skills Demonstrated

Data Cleaning · Data Profiling · Exploratory Data Analysis · Feature Engineering · Business Intelligence · KPI Development · Data Visualization · Interactive Dashboard Design · Business Insight Communication

## 🙏 Acknowledgements

Credit to the original Hotel Booking Demand dataset authors and the Kaggle dataset publisher. Dataset redistribution is subject to its applicable license and terms. 
