# Intermediate-Assessment---Codeathon
Intermediate Assessment - Codeathon
# Logistics & Transportation – Fleet Performance & Delivery Efficiency

## 1. Project Overview

This project focuses on analyzing fleet performance and delivery efficiency for a logistics company using Microsoft Power BI.

The main objective is to evaluate on-time deliveries, fuel efficiency, and transportation costs to identify opportunities for improving route performance and fleet utilization.

The project uses trip data and vehicle master data to develop an interactive logistics dashboard that supports data-driven decision-making.

## 2. Problem Statement

A logistics company wants to analyze its fleet performance in terms of:

- On-time deliveries
- Fuel efficiency
- Cost per kilometer

The analysis helps the company monitor delivery operations, evaluate vehicle performance, identify inefficient routes, and optimize fleet usage.

## 3. Dataset Description

The project uses two datasets:

**Trip Data**
- Trip ID
- Vehicle ID
- Driver ID
- Origin
- Destination
- Distance (km)
- Fuel Consumed (liters)
- Delivery Status (On-Time/Late)
- Delivery Date

**Vehicle Master**
- Vehicle ID
- Vehicle Type
- Capacity
- Maintenance Cost

## 4. Tools & Technologies

- **Microsoft Excel** – Initial data inspection and preparation.
- **Power Query** – Data cleaning and transformation.
- **Power BI Desktop** – Data modeling, DAX calculations, and dashboard development.

## 5. Data Cleaning & Data Modeling

The following activities were performed:

- Removed unnecessary rows and columns.
- Cleaned and corrected Trip ID values.
- Handled missing and null values.
- Corrected data types.
- Addressed missing fuel consumption values using the average fuel consumption of the respective vehicle type.
- Established a relationship between Trip Data and Vehicle Master using Vehicle ID.
- Prepared the data for analysis and visualization.

## 6. DAX Measures

Created DAX measures to calculate important logistics performance metrics.

### Fuel Efficiency

Measures the distance travelled per liter of fuel consumed.

```DAX
Fuel_Efficiency =
DIVIDE(
    SUM('Trip_Data (2)'[Distance_km]),
    SUM('Trip_Data (2)'[Fuel_Consumed_L])
)
```

Unit: km/L

### On-Time Delivery %

Measures the percentage of trips delivered on time.

```DAX
On_Time_Delivery % =
DIVIDE(
    CALCULATE(
        COUNTROWS('Trip_Data (2)'),
        'Trip_Data (2)'[Delivery_Status] = "On-Time"
    ),
    COUNTROWS('Trip_Data (2)')
) * 100
```

### Late Delivery

Calculates the total number of late deliveries.

```DAX
Late Delivery =
CALCULATE(
    COUNTROWS('Trip_Data (2)'),
    'Trip_Data (2)'[Delivery_Status] = "Late"
)
```

### Cost per km

According to the assignment, cost per kilometer is calculated using:

**Cost per km = (Fuel Cost + Maintenance Cost) / Distance**

This metric helps evaluate transportation expenses relative to the distance travelled.

## 7. Dashboard Visualizations

The interactive dashboard includes the following visualizations:

### 1. Bar Chart – On-Time Delivery % by Route
- Compares delivery performance across different routes.
- Helps identify routes with lower on-time delivery rates.

### 2. Line Chart – Fuel Efficiency Trend by Month
- Displays monthly fuel efficiency trends.
- Helps monitor fuel consumption relative to distance travelled.

### 3. KPI Cards
Displays important performance indicators:
- Average Delivery Time
- Cost per km

Additional performance indicators include total trips, late deliveries, and on-time delivery percentage.

### 4. Map Visual – Delivery Performance by Route
- Displays delivery locations using Origin and Destination.
- Provides geographical insights into logistics operations.

## 8. Project Objectives

- Improve on-time delivery performance.
- Monitor fuel efficiency across the fleet.
- Analyze transportation cost per kilometer.
- Identify routes requiring operational improvement.
- Support better fleet utilization and route optimization.

## 9. Key Skills Demonstrated

- Data Cleaning
- Data Transformation
- Power Query
- Data Modeling
- DAX Calculations
- KPI Development
- Data Visualization
- Business Intelligence
- Logistics Performance Analysis

## 10. Conclusion

The Logistics & Transportation Dashboard provides insights into fleet performance, delivery efficiency, and fuel consumption.

By transforming raw logistics data into meaningful visualizations, this project helps identify operational challenges and supports data-driven decisions to improve transportation efficiency and optimize fleet usage.

---

**Project Title:** Logistics & Transportation – Fleet Performance & Delivery Efficiency

**Project Type:** Data Analytics

**Visualization Tool:** Microsoft Power BI
