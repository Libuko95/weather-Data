#Python Codes for weather-Data
!pip install pandas
import pandas as pd
import numpy as  np
df= pd.read_csv("/content/drive/MyDrive/Weather Data.csv")
df.head()
--1.Find all records where the weather was exactly clear.
clear_weather_records = df[df['Weather'] == 'Clear']
print(clear_weather_records)
--2.Find the number of times the wind speed was exactly 4 km/hr
wind_speed_4_records = df[df['Wind Speed_km/h'] == 4]
num_wind_speed_4 = wind_speed_4_records.shape[0]
print("Number of times the wind speed was exactly 4 km/hr:", num_wind_speed_4)
--3.Check if there are any NULL values present in the dataset.
null_values = df.isnull().sum()
print(null_values)
--4.Rename the column "Weather" to "Weather_Condition."
df = df.rename(columns={'Weather': 'Weather_Condition'})
--5.What is the mean visibility of the dataset?
mean_visibility = df['Visibility_km'].mean()
print("Mean visibility of the dataset: ", mean_visibility)
--6 Find the number of records where the wind speed is greater than 24 km/hr and visibility is equal to 25 km
filtered_records = df[(df['Wind Speed_km/h'] > 24) & (df['Visibility_km'] == 25)]
num_records = filtered_records.shape[0]
print("Number of records where wind speed > 24 km/hr and visibility = 25 km:", num_records)
