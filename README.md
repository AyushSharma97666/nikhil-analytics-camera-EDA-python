# Nikhil Analytics Camera EDA Project

## Overview
This repository contains an exploratory data analysis (EDA) project conducted in Python focusing on a dataset of approximately 1000 cameras. The project aims to explore, clean, and derive insights from this dataset containing various properties such as weight, focal length, price, etc.

## Project Tasks
- **Task 1:** Create a DataFrame "Camera_data" using the provided "Camera.csv".
  ```
  import pandas as pd 
  df = pd.read_csv('Camera.csv')
  df
  ```
- **Task 2:** Find the percentage of blank values in each column.
  ```
  (df.isnull().sum()/len(df))* 100
  ```
- **Task 3:** View the statistical summary of the data.
  ```
  df.describe()
  ```
- **Task 4:** Replace all blank values with NaN.
- **Task 5:** Replace blank values with respective column medians.
  ```
  df= df.replace('', "NaN")
  df['Max resolution'] =df['Max resolution'].fillna(df['Max resolution'].median())
  df['Low resolution'] = df['Low resolution'].fillna(df['Low resolution'].median())
  df['Storage included']= df['Storage included'].fillna(df['Storage included'].median())
  df['Weight (inc. batteries)'] = df['Weight (inc. batteries)'].fillna(df['Weight (inc. batteries)'].median())
  df['Dimensions'] = df['Dimensions'].fillna(df['Dimensions'].median())
  df['Zoom wide (W)'] = df['Zoom wide (W)'].fillna(df['Zoom wide (W)'].median())
  df['Macro focus range'] = df['Macro focus range'].fillna(df['Macro focus range'].median())
```
- **Task 6:** Add a new column "Discounted_Price" with a 5% discount on the Price column.
```
df['Discounted_Price'] = df['Price'] *0.95
```
- **Task 7:** Drop columns "Zoom Tele" & "Macro Focus range".
```
df = df.drop(['Zoom tele (T)' , 'Macro focus range'] , axis =1)
df.info()
```
- **Task 8:** Replace the Model Name "Agfa ePhoto CL50" with "Agfa ePhoto CL250".
```
df1= df
df1['Model'].replace('Agfa ePhoto CL50' , 'Agfa ePhoto CL250', inplace=True)
df1[df1['Model'] == 'Agfa ePhoto CL250']
```
- **Task 9:** Rename the column from "Release Date" to "Release Year".
```
df1= df1.rename(columns={'Release Date' : 'Release Year'} , inplace=True)
```
- **Task 10:** Identify the most expensive camera.
```
df2 = df1[df1['Price'] == df1['Price'].max() ]
df2[['Model', 'Price' ]]
```
- **Task 11:** Find the camera with the least weight.
```
df_least_weight_camera = df1[df1['Weight (inc. batteries)'] == df1['Weight (inc. batteries)'].min()]
df_least_weight_camera[['Model', 'Weight (inc. batteries)']]
```
- **Task 12:** Group the data based on release year.
```
new_grouped_data = df1.groupby(by='Release Year')['Model'].count()
new_grouped_data_1 = new_grouped_data.reset_index()
```
- **Task 13:** Extract specific columns: Name, Storage Include, Price, Discounted_Price & Dimensions.
```
New_df = df1[['Model' , 'Storage included' , 'Price' , 'Discounted_Price' , 'Dimensions']]
New_df
```
- **Task 14:** Extract records for cameras released in 2005 & 2006.
```
df_2005_2006 = df1[df1['Release Year'].isin([2006,2005])] 
df_2005_2006
```
- **Task 15:** Identify the most expensive & cheapest camera in 2007.
```
df_2007 = df1[df1['Release Year'] == 2007]
df_cheap_2007 = df_2007[df_2007['Price'] == df_2007['Price'].min()]
dff11 = df_cheap_2007[['Model' , "Price"]].drop_duplicates()
dff11
```
- **Task 16:** Determine the year with the maximum number of models released.
```
new_grouped_data = df1.groupby(by='Release date')['Model'].count()
new_grouped_data_1 = new_grouped_data.reset_index()
df111 = new_grouped_data_1 [new_grouped_data_1['Model'] == new_grouped_data_1['Model'].max()]
df111['Release date']
```

## Files
- `Camera.csv`: Dataset used for the analysis.
- `python_script.py` (or `notebook.ipynb`): Python script or Jupyter Notebook containing the code for the tasks.

## Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/YourUsername/Nikhil-Analytics-Camera-EDA-Python.git
