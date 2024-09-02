# Cyclistic Data Analysis Project

## Overview
This project is an in-depth analysis of Cyclistic's bike-sharing data, starting with data cleaning and preprocessing using Python. The cleaned data was then visualized in Power BI for further analysis. This project was completed as part of the capstone for the Google Data Analytics Professional Certificate.

## Objective
The main objective of this project is to explore the riding behaviors of Cyclistic’s casual riders and annual members. The insights gained from this analysis can help shape strategies to convert casual riders into annual members.

## Dataset
The dataset used for this project spans from April 2023 to April 2024 and includes:
- **ride_id**: Unique identifier for each ride.
- **rideable_type**: Type of bike (electric, docked, or standard).
- **started_at**: Timestamp for when the ride began.
- **ended_at**: Timestamp for when the ride ended.
- **start_station_name**: Name of the station where the ride started.
- **end_station_name**: Name of the station where the ride ended.
- **member_casual**: Rider category (casual or member).

## Data Cleaning and Preprocessing

### Tools Used:
- **Python Libraries**: Pandas, NumPy, Matplotlib.
- **Notebook Environment**: Jupyter Notebook.

### Key Steps:
1. **Loading Data**: The raw data was imported from multiple CSV files covering different months from here: https://divvy-tripdata.s3.amazonaws.com/index.html
  

2. **Data Transformation**:
    - **Datetime Conversion**: Converted `started_at` and `ended_at` columns to datetime objects for time-based analysis.
    - **Creating New Columns**: Added new columns like `ride_length` (in minutes) and `month` to enable detailed analysis.
    - **Season Classification**: Created a `season` column to categorize rides by Winter, Spring, Summer, and Fall.
    

## Jupyter Notebook
The full Python code for data cleaning and preprocessing is available in the `Proyect.ipynb` file.

## Analysis and Visualization
After cleaning the data in Python, it was exported to Power BI for further analysis and visualization. The Power BI visualizations highlight key trends and insights, such as:
- **Seasonal Trends**: How ride patterns vary across different seasons.
- **User Behavior**: Differences in riding habits between casual riders and members.

## Results
- **Casual Riders**: Tend to ride more on weekends and for longer durations.
- **Members**: Show consistent usage patterns throughout the week.
- **Seasonal Impact**: Summer has the highest ride volume, especially among casual riders.

## File Information
- **Proyect.ipynb**: Contains the Python code for data cleaning and preprocessing.
- **Cyclicist.pbix**: Power BI file for visualized analysis. [Download Link](<Insert Your Cloud Storage Link Here>)

## How to Use
1. **Python Notebook**:
   - Ensure you have the necessary Python libraries installed: `pandas`, `numpy`, `matplotlib`.
   - Open `Proyect.ipynb` in Jupyter Notebook or a compatible environment.
   - Run the cells to load, clean, and preprocess the data.

2. **Power BI**:
   - Download the `Cyclicist.pbix` file.
   - Open it in Power BI Desktop to explore the visualizations and insights.

## Conclusion
This project demonstrates an end-to-end data analysis process, from data cleaning in Python to visualization in Power BI. The insights gained can help Cyclistic in enhancing user engagement and conversion strategies.

## Contact
For questions or feedback, please contact me at [your email address].
