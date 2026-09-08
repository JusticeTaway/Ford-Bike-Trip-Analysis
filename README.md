# 🚲 Bike-Sharing Business Intelligence & Operations Analytics | Power BI

## 📌 Project Overview

This project is an end-to-end **Business Intelligence and Business Analytics project** built around bike-sharing trip data.

The objective was not simply to create charts, but to transform raw operational data into a decision-support dashboard that answers four levels of business questions:

1. **Descriptive — What is happening?**
2. **Diagnostic — What does the performance tell us and where are the problems?**
3. **Predictive — What is likely to happen next?**
4. **Prescriptive — What should the business do about it?**

The project covers the complete analytics workflow, from data preparation and cleaning in **Microsoft Excel**, through data transformation and modelling in **Power BI**, to interactive dashboard development, operational analysis, forecasting, and evidence-based recommendations.

The final dashboard focuses on:

- Ride demand and overall usage
- Rider demographics and behavior
- Station performance
- Peak-period demand
- Bike utilization
- Demand trends and forecasting
- Operational efficiency
- Strategic recommendations

> **Portfolio objective:** Demonstrate the ability to move from raw data to business insight and from business insight to actionable recommendations.

---

# 🎯 Business Problem

A bike-sharing company generates large volumes of trip data, but raw trip records do not automatically provide management with useful answers.

Management needs to understand:

- How heavily is the bike-sharing system being used?
- When does demand peak?
- Who are the primary users?
- Which age groups and user types contribute the most rides?
- Which stations generate the greatest demand?
- Which stations attract the most arriving riders?
- Which stations appear underutilized?
- Which bikes are being used most frequently?
- Are ride patterns changing over time?
- What future demand patterns should operations prepare for?
- What actions could improve bike availability, station performance, customer engagement, and operational efficiency?

This project converts the available trip-level data into a structured analytical solution designed to support those decisions.

---

# 🧠 Analytical Framework

The project follows the four stages of analytics:

| Analytics Level | Business Question | Project Application |
|---|---|---|
| Descriptive Analytics | What is happening? | Total rides, average duration, user composition, demand patterns |
| Diagnostic Analytics | What does the performance show? | Station rankings, user behavior, bike utilization, peak periods |
| Predictive Analytics | What may happen? | Time-based demand trends and forecasting |
| Prescriptive Analytics | What should be done? | Operational, customer, station, and asset recommendations |

This framework ensures that the dashboard goes beyond reporting numbers and supports business decision-making.

---

# 📊 Dataset

The dataset contains individual bike-sharing trip records.

Key fields used in the analysis include:

| Field | Description | Analytical Use |
|---|---|---|
| `Bike_id` | Identifier for the bike used | Bike utilization |
| `Duration_sec` | Trip duration in seconds | Trip duration analysis |
| `Start_time` | Date and time the ride started | Time-series and peak-hour analysis |
| `End_time` | Date and time the ride ended | Trip completion and duration validation |
| `Start_date` | Start date | Daily/period analysis |
| `Start_station_id` | Starting station identifier | Station analysis |
| `Start_station_name` | Starting station name | Station demand |
| `Start_station_latitude` | Starting station latitude | Geographic analysis |
| `Start_station_longitude` | Starting station longitude | Geographic analysis |
| `End_station_id` | Ending station identifier | Destination analysis |
| `End_station_name` | Ending station name | Destination demand |
| `End_station_latitude` | Ending station latitude | Geographic analysis |
| `End_station_longitude` | Ending station longitude | Geographic analysis |
| `Member_gender` | Rider gender | Demographic analysis |
| `Member_birth_year` | Rider birth year | Age calculation/segmentation |
| `User_type` | Rider/customer type | Customer segmentation |
| `Age Range` | Age classification used in the project | Demographic segmentation |

### Important data consideration

The dataset does **not** contain direct revenue, pricing, maintenance records, repair history, or actual station inventory levels.

Therefore, the project does not claim to measure revenue or actual maintenance failures. Where operational recommendations are made, they are based on observable proxies such as ride volume, trip duration, station activity, and bike utilization.

This distinction is important because good analytics should separate **what the data proves** from **what the analyst recommends management investigate**.

---

# 🔄 End-to-End Data Analytics Workflow

The project followed this workflow:

```text
Raw Dataset
     ↓
Initial Data Inspection
     ↓
Data Cleaning in Excel
     ↓
Data Quality Checks
     ↓
Import into Power BI
     ↓
Power Query Transformation
     ↓
Data Type Validation
     ↓
Calculated Columns & DAX Measures
     ↓
Data Modelling
     ↓
Exploratory Analysis
     ↓
Dashboard Development
     ↓
Business Insights
     ↓
Forecasting
     ↓
Recommendations
     ↓
Final Portfolio Dashboard
```

---

# 1. 🔍 Initial Data Inspection

Before building any dashboard, the dataset was reviewed to understand:

- Available columns
- Data types
- Missing values
- Duplicate records
- Invalid values
- Date and time formats
- Numerical fields
- Categorical fields
- Station identifiers
- User attributes
- Potential analytical questions

The first step was to understand the **business meaning of each field** rather than immediately creating visualizations.

This helped determine which fields could support:

- Customer analysis
- Operational analysis
- Station analysis
- Time-series analysis
- Forecasting

---

# 2. 🧹 Data Cleaning in Microsoft Excel

Excel was used for the initial data-cleaning and quality-control stage.

The cleaning process focused on making the dataset consistent and suitable for analysis.

## 2.1 Reviewed Missing Values

Columns were checked for blank or missing values, particularly:

- Gender
- Birth year
- User type
- Station information
- Start/end times
- Duration
- Bike ID

Missing values were reviewed before being used in calculations or segmentation.

## 2.2 Checked Duplicate Records

Duplicate records were reviewed to ensure that the ride count would not be artificially inflated.

Because a trip-level dataset generally treats each valid row as one ride, it was important to understand whether duplicate rows represented:

- Genuine repeated trips
- Duplicate records
- Data-entry issues

## 2.3 Reviewed Data Consistency

Categorical fields were checked for inconsistent spellings, spacing, or labels.

Examples include:

- User type
- Gender
- Station names

Standardized categories are important because Power BI treats different spellings as different categories.

## 2.4 Reviewed Date and Time Fields

The start and end time fields were checked to ensure they represented valid date/time values.

This was particularly important because later analysis required:

- Hour extraction
- Daily trends
- Peak-hour analysis
- Time-series analysis
- Forecasting

## 2.5 Reviewed Numerical Fields

Numerical fields such as:

- `Duration_sec`
- `Member_birth_year`
- Station coordinates

were reviewed for inappropriate values and formatting issues.

---

# 3. ⚙️ Importing the Data into Power BI

After the initial Excel cleaning, the dataset was imported into Power BI.

The goal at this stage was to prepare the data for analytical modelling rather than simply reproduce the Excel spreadsheet.

---

# 4. 🔄 Data Transformation in Power Query

Power Query was used to prepare the dataset for analysis.

Key transformation activities included:

### Data type conversion

Fields were assigned appropriate types:

- Date
- Date/Time
- Whole number
- Decimal number
- Text

This was especially important for `Start_time` and `End_time`.

### Time transformation

The start-time field was transformed into usable time attributes so that ride activity could be analyzed by hour.

For example:

```text
00 → 12 AM
07 → 7 AM
13 → 1 PM
17 → 5 PM
23 → 11 PM
```

### Date preparation

Date fields were prepared for time-based analysis, allowing rides to be aggregated by:

- Day
- Week
- Month
- Other relevant periods

### Categorical preparation

Fields such as gender and user type were prepared for segmentation and visual analysis.

---

# 5. 🧮 DAX Measures & Calculated Columns

DAX was used to create reusable analytical calculations.

## 5.1 Total Rides

Each valid trip record represents one ride, so the main ride-volume measure was based on the number of records.

```DAX
Total Rides =
COUNTROWS(BikeShare)
```

> Replace `BikeShare` with the actual table name used in your Power BI model.

This measure was used throughout the dashboard rather than repeatedly counting rows manually.

---

## 5.2 Average Trip Duration

The original duration field was stored in seconds.

It was converted to minutes for easier business interpretation.

```DAX
Avg Trip Duration (Min) =
ROUND(
    AVERAGE(BikeShare[Duration_sec]) / 60,
    1
)
```

This produces a business-friendly metric such as:

> Average Trip Duration = 17.8 minutes

---

## 5.3 Ride Hour

The start time was used to identify the hour in which each ride began.

```DAX
Ride Hour =
HOUR(BikeShare[Start_time])
```

This enabled peak-hour analysis.

For example:

- 07 = 7 AM
- 08 = 8 AM
- 17 = 5 PM
- 18 = 6 PM

---

## 5.4 Day Name

A day-of-week field was created for operational analysis.

```DAX
Day Name =
FORMAT(BikeShare[Start_time], "dddd")
```

This allowed ride volume to be compared across:

- Monday
- Tuesday
- Wednesday
- Thursday
- Friday
- Saturday
- Sunday

---

## 5.5 Age Calculation

Rider age was derived from birth year.

For historical analysis, the age reference year should ideally correspond to the ride date rather than the current date.

A simplified approach is:

```DAX
Age =
YEAR(BikeShare[Start_time])
    - BikeShare[Member_birth_year]
```

Where appropriate, age calculations should also account for whether the rider's birthday had occurred at the time of the ride.

---

# 6. 👥 Rider Age Segmentation

Raw birth years are difficult for executives to interpret, so age was transformed into meaningful demographic groups.

The project used the following business segmentation:

- **Young Adult:** 21–50
- **Old Adult:** 51–150

Example DAX:

```DAX
Age Group =
SWITCH(
    TRUE(),
    BikeShare[Age] >= 21 && BikeShare[Age] <= 50, "Young Adult",
    BikeShare[Age] >= 51 && BikeShare[Age] <= 150, "Old Adult",
    "Unknown"
)
```

This segmentation allows management to compare ride behavior across broader customer groups.

> In a production environment, the upper age limit should be reviewed and unrealistic ages should be treated as data-quality exceptions rather than automatically classified as valid customers.

---

# 7. 📐 Data Model & Analytical Measures

Reusable measures were preferred over hard-coded calculations inside individual visuals.

Core measures included:

```DAX
Total Rides =
COUNTROWS(BikeShare)
```

```DAX
Avg Trip Duration (Min) =
ROUND(
    AVERAGE(BikeShare[Duration_sec]) / 60,
    1
)
```

```DAX
Total Bikes Used =
DISTINCTCOUNT(BikeShare[Bike_id])
```

These measures allowed the same business definitions to be used consistently across multiple dashboard pages.

---

# 8. 📊 Dashboard Design

The dashboard was divided into separate analytical pages rather than putting every visual on one screen.

The final structure was:

```text
Page 1 → Executive Overview
Page 2 → Rider Behavior
Page 3 → Station Performance
Page 4 → Operations & Forecasting
Page 5 → Strategic Recommendations
```

Each page has a specific business purpose.

---

# PAGE 1 — Executive Overview

## Business Question

> **What is happening across the bike-sharing system?**

This page provides an executive-level summary.

### Key analyses

#### 1. Total Rides

**Question:**

> How heavily is the bike-sharing system being used?

**Visual:**

- KPI/Card

**Measure:**

- Total Rides

---

#### 2. Average Trip Duration

**Question:**

> How long does the average rider use a bike?

**Visual:**

- KPI/Card

**Measure:**

- Avg Trip Duration (Min)

---

#### 3. Peak Hours

**Question:**

> When is demand highest?

**Visual:**

- Clustered column chart

**Axis:**

- Ride Hour

**Value:**

- Total Rides

---

#### 4. Usage Trend

**Question:**

> How does ride demand change over time?

**Visual:**

- Line chart

**Axis:**

- Ride Date

**Value:**

- Total Rides

---

#### 5. Gender Split

**Question:**

> What is the gender composition of riders?

**Visual:**

- Donut chart

**Legend:**

- Member Gender

**Value:**

- Total Rides

---

#### 6. User Type Split

**Question:**

> Which customer type contributes the most rides?

**Visual:**

- Donut chart

**Legend:**

- User Type

**Value:**

- Total Rides
****Screenshot / Demos**
  
  show what the Dashboard looks like - https://github.com/JusticeTaway/Ford-Bike-Trip-Analysis/blob/main/Ford%20Bike%20Dashboard%201.jpg
  Example: [Dashboad preview] (https://github.com/JusticeTaway/Ford-Bike-Trip-Analysis/blob/main/Ford%20Bike%20Dashboard%201.jpg)
---

# PAGE 2 — Rider Behavior

## Business Question

> **Who is using the service and how do different rider groups behave?**

### Key analyses

#### Age Group Distribution

**Question:**

> Which age group contributes the most rides?

**Visual:**

- Clustered bar chart

**Fields:**

- Age Group
- Total Rides

---

#### Ride Duration by Gender

**Question:**

> Do different genders have different average riding durations?

**Visual:**

- Clustered column chart

**Fields:**

- Member Gender
- Avg Trip Duration

---

#### User Type & Duration

**Question:**

> Which user type takes longer trips?

**Visual:**

- Clustered column chart

**Fields:**

- User Type
- Avg Trip Duration

---

#### Gender Ride Frequency

**Question:**

> Which gender contributes the greatest share of rides?

**Visual:**

- Donut chart

---

#### User Type Ride Frequency

**Question:**

> Which user group dominates system usage?

**Visual:**

- Donut chart

---

#### Riding Time by User Type

**Question:**

> Do subscribers and casual users ride at different times?

**Visual:**

- Stacked column chart

**Fields:**

- Ride Hour
- User Type
- Total Rides

This can reveal commuter-oriented versus leisure-oriented patterns.

---

# PAGE 3 — Station Performance

## Business Question

> **Which stations are performing well, and where should operations focus?**

Because the project environment did not allow the use of an interactive map, the station analysis focused on non-map visuals that still provide operational insight.

### Key analyses

#### Top Starting Stations

**Question:**

> Which stations generate the highest number of departures?

**Visual:**

- Horizontal bar chart

**Fields:**

- Start Station Name
- Total Rides

A Top 10 filter can be applied.

---

#### Top Destination Stations

**Question:**

> Which stations receive the highest number of completed trips?

**Visual:**

- Horizontal bar chart

**Fields:**

- End Station Name
- Total Rides

---

#### Average Duration by Station

**Question:**

> Which starting stations are associated with longer trips?

**Visual:**

- Horizontal/clustered bar chart

**Fields:**

- Start Station Name
- Avg Trip Duration

---

#### User Type by Station

**Question:**

> Which stations primarily serve subscribers versus casual users?

**Visual:**

- Stacked bar chart

**Fields:**

- Start Station Name
- User Type
- Total Rides

This helps distinguish commuter-oriented and leisure-oriented locations.

---

#### Station Performance Table

A matrix/table can combine multiple station indicators:

- Station
- Total Rides
- Average Trip Duration
- Distinct Bikes Used
- User Type mix

This provides a more detailed operational view behind the charts.

---

# PAGE 4 — Operations & Forecasting

## Business Question

> **When will demand put the greatest pressure on operations, and what future patterns should the business prepare for?**

### Key analyses

#### Demand Trend & Forecast

**Question:**

> Is ride demand increasing, decreasing, or showing recurring patterns?

**Visual:**

- Line chart
- Power BI forecasting capability where appropriate

**Fields:**

- Ride Date
- Total Rides

---

#### Demand by Day of Week

**Question:**

> Which days create the greatest operational demand?

**Visual:**

- Clustered column chart

**Fields:**

- Day Name
- Total Rides

---

#### Peak-Hour Demand

**Question:**

> Which hours place the greatest pressure on bike availability?

**Visual:**

- Area chart or column chart

**Fields:**

- Ride Hour
- Total Rides

---

#### Bike Utilization

**Question:**

> Which bikes are used most frequently?

**Visual:**

- Horizontal bar chart

**Fields:**

- Bike ID
- Total Rides

A Top 10 view can highlight heavily utilized bikes.

This is a **maintenance planning signal**, not proof that a bike is defective.

---

#### Average Duration Trend

**Question:**

> Is average riding time changing over the analysis period?

**Visual:**

- Line chart

**Fields:**

- Ride Date
- Avg Trip Duration

---

#### User Type Demand Trend

**Question:**

> Which customer segment is driving changes in demand?

**Visual:**

- Stacked area chart

**Fields:**

- Ride Date
- User Type
- Total Rides

---

# PAGE 5 — Strategic Recommendations

## Business Question

> **What should management do based on the evidence?**

The recommendation page translates analysis into action.

The recommendations follow:

```text
Finding → Business Implication → Recommendation
```

## 1. Operational Efficiency

### Issue / Finding

Peak demand is concentrated around high-activity commuting periods, particularly where the analysis identifies morning and evening demand spikes.

### Recommendation

Increase bike redistribution and availability at high-demand stations before peak periods to improve service availability and reduce the risk of shortages.

---

## 2. Customer Growth

### Issue / Finding

Usage is concentrated among the strongest-performing age and user-type segments.

### Recommendation

Develop targeted campaigns, referral programs, and promotional offers to increase adoption among underrepresented rider segments while retaining high-value users.

---

## 3. Station Optimization

### Issue / Finding

Station performance is uneven, with some locations generating substantially more activity than others.

### Recommendation

Review underperforming stations for relocation, improved visibility, local partnerships, or targeted marketing before committing additional operational resources.

---

## 4. Asset Management

### Issue / Finding

Bike utilization is uneven, with some bikes recording substantially more trips than others.

### Recommendation

Use utilization data to prioritize preventive inspection and maintenance scheduling and consider asset rotation to balance usage.

> This recommendation should be presented as a planning recommendation because the dataset does not contain actual repair or maintenance records.

---

# 📈 Key Business Insights the Project Can Generate

The dashboard is designed to identify patterns such as:

- Peak demand periods
- High-performing stations
- Underutilized stations
- Dominant customer segments
- Differences in rider behavior
- Differences in trip duration
- Highly utilized bikes
- Changes in demand over time
- Potential future demand patterns

The exact conclusions should always be based on the actual values displayed by the final dashboard rather than assumptions.

---

# 💡 Business Analyst Thinking Used in the Project

One of the main objectives of this project was to avoid the common mistake of building visuals simply because they look attractive.

Each visual was selected because it answers a business question.

For example:

| Business Question | Analytical Metric | Visual |
|---|---|---|
| How much is the service used? | Total Rides | KPI Card |
| How long are trips? | Avg Trip Duration | KPI Card |
| When is demand highest? | Rides by Hour | Column Chart |
| Is demand changing? | Rides over Time | Line Chart |
| Who uses the service? | Gender | Donut Chart |
| Which customer type dominates? | User Type | Donut Chart |
| Which ages ride most? | Age Group | Bar Chart |
| Which stations are busiest? | Rides by Station | Bar Chart |
| Where do riders finish? | Destination Rides | Bar Chart |
| Which stations have longer trips? | Avg Duration | Bar Chart |
| Which bikes are heavily utilized? | Rides by Bike | Bar Chart |
| What might happen next? | Time-based Demand | Forecast/Line Chart |
| What should management do? | Findings | Recommendation Panel |

---

# 🛠️ Tools & Technologies

### Microsoft Excel

Used for:

- Initial data inspection
- Data cleaning
- Data-quality checks
- Basic preparation

### Microsoft Power BI

Used for:

- Power Query transformation
- Data modelling
- DAX calculations
- Interactive visualizations
- Dashboard development
- Time-series analysis
- Forecasting
- Business intelligence reporting

### DAX

Used for:

- KPI calculations
- Ride counts
- Average duration
- Age calculations
- Time attributes
- Distinct bike counts
- Reusable analytical measures

---

# 🎨 Dashboard Design Principles

The dashboard was designed around several BI principles:

### 1. Business-first design

Every major visual should answer a specific business question.

### 2. Executive readability

Important KPIs are positioned prominently.

### 3. Visual hierarchy

Large/high-priority insights receive more screen space than secondary analysis.

### 4. Consistent visual language

Similar analytical concepts use consistent chart types and formatting.

### 5. Minimal clutter

The dashboard avoids unnecessary charts and focuses on decision-relevant information.

### 6. Interactive exploration

Where appropriate, Power BI filters and slicers can allow users to investigate specific periods, stations, user groups, or demographics.

---

# 🔎 Data Limitations

A responsible analyst must clearly identify limitations.

This dataset does not provide:

- Revenue
- Pricing
- Customer acquisition cost
- Actual station capacity
- Real-time bike inventory
- Maintenance records
- Repair history
- Weather conditions
- Traffic conditions
- Marketing expenditure
- Customer satisfaction scores

Therefore:

- Revenue performance cannot be calculated.
- Profitability cannot be calculated.
- Actual bike shortages cannot be directly confirmed from trip records alone.
- Maintenance failures cannot be directly identified.
- Forecasts should be treated as demand estimates, not guarantees.
- Recommendations concerning inventory or maintenance are operational recommendations based on usage patterns and should be validated with additional business data.

This limitation section is important because it demonstrates analytical judgment rather than overstating what the data can prove.

---

# 🚀 Potential Future Improvements

The project could be expanded significantly by adding:

## Revenue Data

Add:

- Fare per trip
- Subscription revenue
- Customer acquisition cost
- Revenue by station

This would enable profitability analysis.

## Maintenance Data

Add:

- Maintenance dates
- Repair costs
- Downtime
- Fault types
- Bike condition

This would enable actual predictive maintenance analysis.

## Real-Time Inventory

Add:

- Bikes available by station
- Dock capacity
- Station occupancy

This would allow genuine bike shortage and rebalancing analysis.

## Weather Data

Combine the trip dataset with:

- Temperature
- Rainfall
- Wind
- Weather conditions

This could reveal the impact of weather on demand.

## Advanced Forecasting

Future versions could use:

- Python
- Machine learning
- Time-series models
- Regression
- More advanced forecasting techniques

to improve demand prediction.

---

# 📁 Suggested GitHub Repository Structure

```text
bike-sharing-powerbi-analysis/
│
├── README.md
│
├── data/
│   └── bike-sharing-data.xlsx
│
├── excel/
│   └── cleaned-bike-sharing-data.xlsx
│
├── powerbi/
│   └── bike-sharing-dashboard.pbix
│
├── screenshots/
│   ├── executive-overview.png
│   ├── rider-behavior.png
│   ├── station-performance.png
│   ├── operations-forecasting.png
│   └── recommendations.png
│
└── documentation/
    └── data-dictionary.md
```

> If the original dataset has licensing or redistribution restrictions, do not upload the raw data. Upload the project documentation and dashboard screenshots instead, or provide instructions for obtaining the dataset.

---

# 📸 Dashboard Preview

Add screenshots of the completed dashboard below.

Example:

```markdown
## Executive Overview

![Executive Overview](screenshots/executive-overview.png)

## Rider Behavior

![Rider Behavior](screenshots/rider-behavior.png)

## Station Performance

![Station Performance](screenshots/station-performance.png)

## Operations & Forecasting

![Operations & Forecasting](screenshots/operations-forecasting.png)

## Strategic Recommendations

![Recommendations](screenshots/recommendations.png)
```

---

# 📌 Project Outcomes

This project demonstrates practical skills in:

- Data cleaning
- Data transformation
- Data quality assessment
- Exploratory data analysis
- Business intelligence
- Power BI
- Power Query
- DAX
- KPI development
- Customer segmentation
- Operational analytics
- Station performance analysis
- Time-series analysis
- Demand forecasting
- Data visualization
- Business storytelling
- Prescriptive analytics
- Recommendation development

---

# 👨‍💻 Portfolio Value

This project demonstrates an end-to-end approach to analytics:

```text
Raw Data
   ↓
Clean Data
   ↓
Transformed Data
   ↓
Analytical Model
   ↓
KPIs & DAX
   ↓
Interactive Dashboard
   ↓
Business Insights
   ↓
Forecast
   ↓
Recommendations
```

The central principle is:

> **Don't just report what happened. Explain what it means, identify where the business can improve, and recommend what should happen next.**

---

# 📚 What I Learned

Through this project, I strengthened my ability to:

1. Approach a dataset from a business-question perspective.
2. Clean and validate data before analysis.
3. Transform raw fields into business-friendly analytical dimensions.
4. Build reusable DAX measures.
5. Select visualizations based on the question being answered.
6. Analyze customer behavior and operational performance.
7. Distinguish descriptive, diagnostic, predictive, and prescriptive analytics.
8. Translate analytical findings into business recommendations.
9. Recognize the limitations of a dataset before making business claims.
10. Build a complete BI portfolio project from raw data to decision support.

---

# ⭐ Final Takeaway

The purpose of this project is not simply to demonstrate that I can use Power BI.

It demonstrates the ability to connect:

**Data → Analysis → Insight → Decision → Action**

A successful Business Intelligence solution should help decision-makers understand not only **what happened**, but also **why it matters, what may happen next, and what they can do about it**.

---

## 📬 Author

**Justice Obeng Asiedu**

Business Analytics | Business Intelligence | Supply Chain & Operations Analytics

Interested in using data, analytics, and technology to solve operational and business problems.

---

## 🔖 Suggested Repository Topics

`Power-BI` `Business-Intelligence` `Business-Analytics` `Data-Analytics` `DAX` `Power-Query` `Data-Visualization` `Customer-Analytics` `Operational-Analytics` `Demand-Forecasting` `Bike-Sharing` `Business-Analysis`
