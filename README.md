# Cyclistic Bike-Share Analysis

This project aims to analyze the Cyclistic bike-share dataset to gain insights into user behavior and membership types. The analysis is performed in Python, and visualizations are generated to highlight key findings. Below is a summary of the steps taken and visual results.

First we got the yearly data in monthly archives from this site: https://divvy-tripdata.s3.amazonaws.com/index.html 
we downloaded the last 12 months and then used python to concatenate them into one.

## Table of Contents

- [Project Overview](#project-overview)
- [Libraries Used](#libraries-used)
- [Data Preprocessing](#data-preprocessing)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Visualizations](#visualizations)
- [Conclusions](#conclusions)

## Project Overview

Cyclistic, a bike-share company, wants to understand the differences in usage between casual users and members. The purpose of this analysis is to explore usage trends and suggest strategies to convert casual riders into members.

## Libraries Used

We start by loading the necessary libraries for data analysis and visualization.

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```


## Data Preprocessing

We load and concatenate monthly datasets from April 2023 to April 2024. These CSV files contain usage data for the bike-share service. The data is cleaned and merged for further analysis.

### Loading Monthly Data

We define a function to load monthly data.

```python
def load_monthly_data(month):
    filename = f"{month}.csv"
    data = pd.read_csv(filename)
    return data
```
## Concatenating All Months

The data from each month is concatenated into a single DataFrame to create a full-year dataset.

files = ['2023_04.csv', '2023_05.csv', ..., '2024_04.csv']
dataframes = []

for file in files:
    df = pd.read_csv(file)
    dataframes.append(df)

CyclYearData = pd.concat(dataframes, ignore_index=True)
CyclYearData.to_csv('CyclYearData.csv', index=False)
```

## Adding 'Month' and 'Season' Columns

To analyze seasonal trends, we create new columns to categorize data by month and season.

CyclYearData['month'] = CyclYearData['started_at'].dt.month

def get_season(month):
    if month in [1, 2, 3]:
        return 'Winter'
    elif month in [4, 5, 6]:
        return 'Spring'
    elif month in [7, 8, 9]:
        return 'Summer'
    else:
        return 'Fall'

CyclYearData['season'] = CyclYearData['month'].apply(get_season)

```

## Adding 'Month' and 'Season' Columns

To analyze seasonal trends, we create new columns to categorize data by month and season.

```
CyclYearData['month'] = CyclYearData['started_at'].dt.month

def get_season(month):
    if month in [1, 2, 3]:
        return 'Winter'
    elif month in [4, 5, 6]:
        return 'Spring'
    elif month in [7, 8, 9]:
        return 'Summer'
    else:
        return 'Fall'

CyclYearData['season'] = CyclYearData['month'].apply(get_season)

```

## Visualizations

Several visualizations were generated to explore bike usage trends by membership type, season, and other factors.

## Average Ride Length by User Type

We calculate the average ride length for both casual riders and members.

```
ride_length_means = CyclYearData.groupby('member_casual')['ride_length'].mean()
ride_length_means.plot(kind='bar', figsize=(8, 6), title='Average Ride Length by User Type')
plt.show()
```

## Number of Rides by Season

To examine how the number of rides varies by season, we plot the number of rides taken in each season.

```
season_counts = CyclYearData['season'].value_counts()
plt.figure(figsize=(8, 6))
sns.barplot(x=season_counts.index, y=season_counts.values)
plt.title('Number of Rides by Season')
plt.show()

```

## Conclusions

From this analysis, we observed that:
- Members tend to take shorter rides but use the service more frequently.
- Casual riders take longer rides, suggesting that they might use the service more for leisure than for commuting.
- Summer has the highest number of rides, suggesting that promotional strategies could focus on this peak period to convert casual riders into members.
