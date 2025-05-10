

# HVAC Sensor Data Analysis

**By Santhosh G**
**2nd Year, Mechanical Engineering**
**ARM College of Engineering & Technology**
**Course: Data Analysis in Mechanical Engineering**

---

## Project Overview

This project focuses on analyzing data from HVAC (Heating, Ventilation, and Air Conditioning) sensors. The goal is to understand how different environmental and operational factors such as temperature, humidity, airflow, CO₂ levels, occupancy, and energy usage relate to each other. By studying this data, we can gain insights that could help improve the energy efficiency and indoor comfort of a building.

The study mainly helps in:

* Discovering patterns in HVAC system behavior.
* Spotting conditions that might cause excessive energy usage.
* Supporting decision-making for building maintenance and automation.

---

## Description of the Dataset

The dataset includes time-based readings of various HVAC parameters. Below is a summary of the main features:

| Feature Name              | Description                                    |
| ------------------------- | ---------------------------------------------- |
| Date\_Logged              | Date and time of the recorded data             |
| Temperature (C)           | Indoor temperature in Celsius                  |
| Humidity (%)              | Relative indoor humidity                       |
| Air\_Flow (CFM)           | Airflow rate measured in cubic feet per minute |
| CO2\_Level (ppm)          | Carbon dioxide concentration in ppm            |
| Occupancy                 | Number of people in the room                   |
| Energy\_Consumption (kWh) | Energy used by the HVAC system                 |

---

## Steps in Data Preprocessing

1. **Loading and Exploring the Data**
   The data was loaded using pandas, and a quick check was done to understand the structure and contents.

2. **Datetime Formatting**
   The `Date_Logged` column was converted into a datetime format to support time-based analysis.

3. **Handling Missing Values**
   Missing values in some features like `CO2_Level` and `Air_Flow` were filled using the average (mean) of the column.

4. **Creating New Features**
   From the timestamp, I created:

   * `Hour`: Hour of the day (0 to 23)
   * `DayOfWeek`: Day of the week (0 = Monday, 6 = Sunday)

---

## Exploratory Data Analysis (EDA)

To explore the data, I used visualizations to better understand how different features are related.

* **Time-Based Patterns**

  * Energy consumption tends to increase during daytime, especially during work hours.
  * CO₂ levels and temperature also follow similar patterns based on how many people are present.

* **Correlation Between Features**

  * `Energy_Consumption` has a moderate relationship with `Temperature` and `Air_Flow`.
  * `CO2_Level` is strongly related to `Occupancy`, which makes sense because people produce CO₂.

* **Distribution of Values**

  * By using histograms and boxplots, I noticed that some values like airflow and energy use have skewed distributions and possible outliers.

---

## Summary of Insights

* **Occupancy and CO₂ are closely linked**: More people in a room means more CO₂, as expected.
* **Airflow increases with occupancy**: The HVAC system likely responds to more people by increasing airflow.
* **Energy use peaks during working hours**: Especially between 9 AM and 6 PM on weekdays.
* **Temperature and humidity remain mostly stable**: This shows that the HVAC system is doing a good job of keeping conditions steady.

---

## Future Improvements

* Use outlier detection methods (like the IQR method) to clean up the data.
* Build prediction models to estimate energy usage or detect unusual HVAC behavior (as a future step).

---

## Tools and Technologies Used

* **Python** with **pandas** and **NumPy** for data cleaning and analysis
* **Matplotlib** and **Plotly** for visualizations
* **Jupyter Notebook** for writing and running the code
