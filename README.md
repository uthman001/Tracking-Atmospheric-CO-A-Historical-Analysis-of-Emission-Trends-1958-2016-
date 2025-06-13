# Tracking-Atmospheric-CO-A-Historical-Analysis-of-Emission-Trends-1958-2016-
This data science research project investigates the long-term trends in atmospheric carbon dioxide (CO₂) concentrations from 1958 to 2016.


## Project Overview

This data science research project investigates the long-term trends in atmospheric carbon dioxide (CO₂) concentrations from 1958 to 2016.

Utilizing high-resolution time-series data from the Mauna Loa Observatory and other verified sources, the project explores the seasonal and annual patterns of CO₂ emissions over nearly six decades.

Through trend analysis and robust data visualization, the study provides compelling evidence of the accelerating rise in CO₂ levels driven by anthropogenic activity.

By presenting clear, data-backed insights into historical CO₂ emissions, this project aims to inform public discourse, support environmental advocacy, and encourage policy interventions for climate action.


### Objectives

- To analyze the trend of atmospheric CO₂ concentrations from 1958 to 2016.

- To quantify the annual growth rate in CO₂ levels.

- To communicate findings using visualizations that are accessible to both scientific and non-scientific audiences.


  ### Data Source
  
  **Mauna Loa Observatory CO₂ Data:** Provided by NOAA [National Oceanic and Atmospheric Administration](https://gml.noaa.gov/ccgg/trends/)


  ### Methodology
  
- Loaded the data from a CSV file into a Pandas Dataframe

- Converted the data into time-series format for seasonal decomposition

- Handled missing values and smoothed data using rolling averages

- Visualized the data to uncover the trend in co2 emmision from 1958 to 2016.


  ### Data Pre-Processing

  The dataset is provided by NOAA [National Oceanic and Atmospheric Administration](https://gml.noaa.gov/ccgg/trends/),  contains records of the change in climate in the last half a century or so. 

The data is in a CSV file called `climate_change` with three columns. 

- 1. The `"date"` column indicates when the recording was made and is stored in the year-month-date format.
     A measurement was taken on the 6th day of every month from 1958 until 2016. 


- 2. The  `"co2"` column contains measurements of the carbon dioxide in the atmosphere.
     The number shown in each row is parts-per-million of carbon dioxide. 


- 3. The  `"relative_temp"` column denotes the temperature measured at this date, relative to a baseline which is the average        temperature in the first ten years of measurements. 



### Data Loading

__Task_1:__ Follow the appropriate steps in reading a CSV file into a pandas Dataframe, 


and  Read the data stored  in the csv file named:  `climate_change` From on your computer.


The resulting Dataframe should be named : `climate_change_df`

```
import numpy as np
import pandas as pd 
import matplotlib.pyplot as plt


climate_change_df =  pd.read_csv("C:/Users/uthma/OneDrive/Desktop/Data Set/climate_change.csv")

climate_change_df.head()

```
![dataloading](https://github.com/user-attachments/assets/28c1ab4e-7274-4666-8214-f49da222239f)




###  Data Analysis

- **Time-Series Decomposition**: This was used to separate trend, seasonality, and residuals.

- **Visualization:** Created line plots,  seasonal subseries plots, and anomaly detection visuals using Python library (Matplotlib)
```
# Converting the data into Time-Series
import pandas as pd 


climate_change_df =  pd.read_csv("C:/Users/uthma/OneDrive/Desktop/Data Set/climate_change.csv", parse_dates = ["date"], index_col= "date" )

climate_change_df.head()

```
![data analysis](https://github.com/user-attachments/assets/9f542a6f-e884-4b10-9771-bb369ae604dc)



###  Data Inspection(check for missing values),

#check for any missing value
```
climate_change_df.isna().sum()
```
![missing value](https://github.com/user-attachments/assets/8d7e2d9a-df2b-4a5d-826c-90e1b856c113)


```
# number of column and number of roll on the data
climate_change_df.shape
```
![shape](https://github.com/user-attachments/assets/c4657228-8318-4839-80c5-de6be7c8f63c)

```
#average of c02 on the data
climate_change_df["co2"].mean()
```
![average](https://github.com/user-attachments/assets/8c4c8d12-0f81-4207-887a-d9f4088d1bd9)


### Data Cleaning (handling missing values) 

```
# Missing values replace with 352.32

climate_change_df = climate_change_df.fillna(352.32)
climate_change_df.head()
```
![handling missing value](https://github.com/user-attachments/assets/6bf065a6-4278-4111-9f2e-2c0cf6ba501c)



#comfirm for any missing value
```
climate_change_df.isna().sum()
```
![comfirm missing value](https://github.com/user-attachments/assets/f5f49033-0012-4c1d-8044-a3df92f95a39)



### Data Visualization

```
import matplotlib.pyplot as plt 

print("matplotlib imported successfully as plt")

```


#let us Create an empty Figure with a 1 Axes
```
fig , ax = plt.subplots()

#vissulizing the co2 emmision and time(date)
ax.plot(climate_change_df.index, climate_change_df["co2"], color = "r")


#lebelling the x axis and y axis
ax.set_xlabel ("Time")
ax.set_ylabel ("C02 (ppm)", color = "b")


#adding a title to our plut
fig.suptitle("The Atmopheric c02 Emission Trends (1958-2016)")

```

![vissualization](https://github.com/user-attachments/assets/6d7a734d-2223-4042-a3f0-7f1218e6b455)


###  Data Interpretation


- The data vissualization above shows that there is a steady increase of co2 emission from 1958 to 2016


### Key Findings


**Steady Increase**: CO₂ levels rose from approximately 315 ppm in 1958 to over 403 ppm by 2016.

**Seasonal Patterns**: A regular saw-tooth pattern was observed, corresponding to seasonal plant activity (photosynthesis cycles).

**Acceleration in Emissions**: Linear curve indicates steady growth and increasing acceleration in emissions, especially post-2000.



### Conclusion


The findings of this study provide compelling evidence of the dramatic rise in atmospheric CO₂ over the last half-century.

While natural seasonal variations exist, the long-term upward trend is unmistakably driven by industrialization, fossil fuel combustion, and land-use changes. 

These results underscore the urgency for global climate mitigation strategies and support the scientific consensus on anthropogenic climate change.



### Recommendations


I strongly reconmmend  the global adoption of renewable energy sources.

I strongly reconmmend the Promotion of  global CO₂ emission monitoring for real-time policy response.

I strongly reconmmend that this  findings should be used as part of educational material in environmental science curricula.

I strongly reconmmend the Extension of this  study to include temperature anomaly data for correlation analysis.









































































  











