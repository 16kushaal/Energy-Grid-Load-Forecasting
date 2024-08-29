# Energy-Grid-Load-Forecasting
This study uses machine learning to predict energy load in Spanish cities based on weather data, aiming to optimize grid management and renewable energy integration. It tackles challenges in data cleaning, model selection, and feature engineering, demonstrating ML's superiority in handling complex relationships and improving forecasting accuracy.

### Why is this relevant ?
The electrical grid is a complex network of power generation, transmission, and distribution systems to deliver electricity to end-users. The demand for electricity fluctuates due to factors such as time of day, weather conditions, and economic activities. Load forecasting involves predicting future electricity demand to plan for optimal resource allocation, infrastructure development, and energy market operations. Load forecasting helps prevent imbalances between supply and demand, ensuring a reliable and stable electrical grid.

## Data Sources and Data Extraction
All data sources to develop this research are publicly available, and the data is available in hourly records from January 2015 until December 2018.
The data composition is the following:
1. Historical electricity load, available on hourly post-dispatch reports available publicly on ENTSOE(European Network of Transmission System Operators for Electricity), Transmission Service Operator in Spain.
2. Weather variables, such as temperature, relative humidity, precipitation, cloud cover and wind speed and direction from five main provinces in Spain, are gathered from OpenWeather API which was available on [Kaggle](https://www.kaggle.com/datasets/nicholasjhana/energy-consumption-generation-prices-and-weather?select=weather_features.csv).
All the required data in present in the data folder, which includes 3 .csv files.
  1. energy_og: The original dataset.
  2. energy_data: Creating two new columns, Fossil Total and Hydro Total which are sum of their respecive sub columns.
  3. weather_feaures: Weather dataset
Furthermore, correlation of electric consumption with time lags and weather variables is investigated to check for the strength of association between these variables. 
## Data Pre-processing
In the energy dataset it has no duplicate values. Nevertheless, it has some NaNs and thus, we have to investigate further. Since this is a task, we cannot simply drop the rows with the missing values and it would be a better idea to fill the missing values using interpolation. 
We used linear forward interpolation.Only a small part of our input data will be noisy and it will not affect performance noticeably. The data will be split into train and test set while maintaining the order of observations. The complete data set was partitioned into a test set (30%), training set (70%).
## Machine Learning Model
Various model were used and compared which are attached in the files section.
  1. SVR.ipynb: Contains data pre processing and merging the dataset aling with implementing SVR Model
  2. All Models.ipynb: Contains data pre processing and merging the dataset aling with implementing other ML models.


