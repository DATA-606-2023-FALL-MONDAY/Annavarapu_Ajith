## 1. Title and Author

**Project Title:** Energy Forecaster

Prepared for UMBC Data Science Master Degree Capstone by Dr Chaojie (Jay) Wang

**Author Name:** Ajith Annavarapu

**GitHub:** https://github.com/Ajith-oo7

**LinkedIn:** https://www.linkedin.com/in/ajith-anna-11369b291/ 

**PowerPoint presentation file:**

**Link to your YouTube video:** 
    
## 2. Background

**Project Description:**

Energy Predictor forecasts how changes in climatic conditions will affect a building's energy consumption by integrating the building's hourly energy consumption data with hourly weather data, enabling facility managers to make the optimal choices among 
1. Take no action! 
1. Invest in renovations to reduce operational costs in the future! 
1. Only invest money when necessary!

**Project Background:**

The objective of this project is to demonstrate the possibilities achievable through machine learning.  This illustration is relevant to asset management, engineering condition assessment, and decision-making concerning engineering capital and maintenance. Some potential applicable scenarios include:
- Utilizing Pump SCADA (Supervisory Control and Data Acquisition) data, weather data, HVAC (Heating, Ventilation, and Air Conditioning) SCADA, and energy consumption data to develop optimized strategies for controlling building mechanical systems, aimed at reducing energy consumption.
- Employing Air Blower SCADA data, influent sewage SCADA data (including flow rate and temperature), effluent SCADA data, and weather information to enhance the efficiency of variable-frequency drives (VFDs) for air blowers.
- Enhancing predictive environmental assessment by considering various factors such as public, human, and engineering-related elements.

**Project Objectives:**

How would annual energy expenditure change under the following scenarios:
- Average annual temperature increase by 0.2 degree, 0.4 degree, 0.8 degree, 1.2 degrees, 1.8 degrees, 3 degrees, 5 degrees, 10 degrees, and 15 degrees.

Increase in Annual Temperature: The model indicates that a rise in the average annual temperature will lead to reduced energy intensity and costs for the targeted building. This happens because as the annual temperature increases, the energy needed to maintain the building's warmth during winter decreases. Even though more energy is required to cool the building in hotter summers, overall energy consumption decreases with a rise in the annual average temperature. The model demonstrates 10 temperature scenarios. For example, a 0.4°C increase in the annual average temperature results in a $1.0k increase in annual energy costs.

- Average annual temperature decrease by 0.2 degree, 0.4 degree, 0.8 degree, 1.2 degrees, 1.8 degrees, 3 degrees, 5 degrees, 10 degrees, and 15 degrees.

Decrease in Annual Temperature: The model demonstrates that a decrease in the average annual temperature will lead to increased energy intensity and costs for the target building. This is primarily due to colder winter temperatures. Despite the cooler summer weather requiring less energy for cooling, the overall energy costs rise. The model presents 10 temperature scenarios. For instance, a 0.4°C decrease in the annual average temperature leads to a $1.2k increase in annual energy costs.

- Average annual temperature **increase only in spring and summer, and decrease in fall and winter by 0.2 degree, 0.4 degree, 0.8 degree, 1.2 degrees, 1.8 degrees, 3 degrees, 5 degrees, 10 degrees, and 15 degrees.

The modeled temperature conditions align more closely with reality, depicting hotter summers and colder winters. Colder winters result in higher energy consumption to maintain the building's temperature, while hotter summers increase the energy required for cooling. The model indicates that climate change and extreme weather can escalate building energy costs. It generates 10 different temperature, demonstrating, for instance, that a 0.4°C annual temperature variation can increase annual energy costs by $1.7k.
  
It's essential to note that the building in focus is an academic establishment housing offices for professors and classrooms for students. The building's energy consumption primarily stems from mechanical and electrical equipment. Should a model be created for industrial facilities with high energy usage for production, future variations in temperature could elevate energy costs. In such cases, a strong business case might justify upgrading existing equipment to curtail operational costs.

## 3. Data 

**Data Explanation:**

The project involves the utilization of 3 distinct datasets: one pertains to building energy consumption, and the other comprises weather data.

For the energy consumption data in this project, the source is the Building Data Genome 2 (BDG2) dataset. BDG2 is an openly available dataset consisting of data from 3,053 energy meters across 1,636 buildings. This dataset spans a two-year timeframe and encompasses data from more than 30 academic buildings situated in Ottawa, Canada. From this dataset, a specific building is selected as the subject of the case study.

The weather data for Ottawa is obtained from Statistics Canada, which serves as the national statistical office of Canada. Statistics Canada plays a crucial role in providing essential information on various aspects of Canada's environment, society, and economy, including weather data.

**Data sources:**
- https://www.researchgate.net/publication/341895125_The_Building_Data_Genome_Project_2_energy_meter_data_from_the_ASHRAE_Great_Energy_Predictor_III_competition
 https://zenodo.org/record/3887306

**Data size:**
- Building Dataset : 264 KB
- Weather Dataset : 18.2 MB
- Meter Dataset : 16.08 KB

**Data shape:** 
Building Dataset : 1636 Rows and 32 Columns
Weather Dataset : 331166 Rows and 10 Columns
Meter Dataset : 349757 Rows and 5 Columns

**Data Description:**
- Building Dataset: The building dataset is made up of 1,636 buildings and their associated information.
- Meter Dataset: Meter dataset includes the measurement of 3,053 energy meters. The time range for the measurement is two full years (2016 & 2017). The measurement frequency is hourly.
- Weather Dataset: weather dataset covers the weather information for the time span of 2 full years. The measurement frequency is hourly.

**Data dictionary:**
- **Columns name**
  - **Data type**
  - **Defition**
  - **Potential values**

Building Dataset:

- **building_id**
  - Data type: Numeric
  - Definition: Building identification number.
  - Potential values: Panther_lodging_Dean

- **site_id**
  - Data type: Numeric
  - Definition: Site identification number.
  - Potential values: Panther

- **building_id_kaggle**
  - Data type: Numeric
  - Definition: Kaggle building identification number.
  - Potential values: 2
 
- **site_id_kaggle**
  - Data type: Numeric
  - Definition: Kaggle site identification number.
  - Potential values: 0

- **primaryspaceusage**
  - Data type: Categorical (Text)
  - Definition: Primary space usage of all buildings categorized using the EnergyStar scheme building description types.
  - Potential values: Lodging/residential

- **sub_primaryspaceusage**
  - Data type: Categorical (Text)
  - Definition: Subcategory of the energystar scheme building description types.
  - Potential values: Residence Hall

- **sqm**
  - Data type: Numeric
  - Definition: Floor area of the building in square meters (m²).
  - Potential values: 508.8

- **sqft**
  - Data type: Numeric
  - Definition: Floor area of the building in square feet (ft²).
  - Potential values: 5477

- **lat**
  - Data type: Numeric
  - Definition: Latitude of the building's location at the city level.
  - Potential values: 28.51768858

- **lng**
  - Data type: Numeric
  - Definition: Longitude of the building's location at the city level.
  - Potential values: -81.3790388

- **timezone**
  - Data type: Categorical (Text)
  - Definition: The timezone of the site where the building is located.
  - Potential values: US/Eastern

- **electricity**
  - Data type: Categorical (Text)
  - Definition: Indicates the presence of an electricity meter in the building. "Yes" if affirmative, NaN if negative.
  - Potential values: Yes

- **hotwater**
  - Data type: Categorical (Text)
  - Definition: Indicates the presence of a hot water meter in the building. "Yes" if affirmative, NaN if negative.
  - Potential values: Yes

- **chilledwater**
  - Data type: Categorical (Text)
  - Definition: Indicates the presence of a chilled water meter in the building. "Yes" if affirmative, NaN if negative.
  - Potential values: Yes

- **steam**
  - Data type: Categorical (Text)
  - Definition: Indicates the presence of a steam meter in the building. "Yes" if affirmative, NaN if negative.
  - Potential values: Yes

- **water**
  - Data type: Categorical (Text)
  - Definition: Indicates the presence of a water meter in the building. "Yes" if affirmative, NaN if negative.
  - Potential values: Yes

- **irrigation**
  - Data type: Categorical (Text)
  - Definition: Indicates the presence of an irrigation meter in the building. "Yes" if affirmative, NaN if negative.
  - Potential values: Yes

- **solar**
  - Data type: Categorical (Text)
  - Definition: Indicates the presence of a solar meter in the building. "Yes" if affirmative, NaN if negative.
  - Potential values: Yes

- **gas**
  - Data type: Categorical (Text)
  - Definition: Indicates the presence of a gas meter in the building. "Yes" if affirmative, NaN if negative.
  - Potential values: Yes

- **industry**
  - Data type: Categorical (Text)
  - Definition: Industry type corresponding to the building.
  - Potential values: Education

- **subindustry**
  - Data type: Categorical (Text)
  - Definition: More detailed breakdown of the industry type corresponding to the building.
  - Potential values: College/University

- **heatingtype**
  - Data type: Categorical (Text)
  - Definition: Type of heating system used in the building.
  - Potential values: Heat network

- **yearbuilt**
  - Data type: Numeric (YYYY format)
  - Definition: Year when the building was first constructed.
  - Potential values: 1989

- **date_opened**
  - Data type: Date (D/M/YYYY format)
  - Definition: Date when the building was opened for use.
  - Potential values: 1/1/1986

- **numberoffloors**
  - Data type: Numeric
  - Definition: Number of floors in the building.
  - Potential values: 271

- **occupants**
  - Data type: Numeric
  - Definition: Usual number of occupants in the building.
  - Potential values: 284

- **energystarscore**
  - Data type: Numeric
  - Definition: Rating of the building according to the EnergyStar scheme (Energy Star Score).
  - Potential values: 62

- **eui**
  - Data type: Numeric
  - Definition: Energy use intensity of the building, measured in kilowatt-hours per year per square meter (kWh/year/m²).
  - Potential values: 136

- **site_eui**
  - Data type: Numeric
  - Definition: Energy use intensity of the site (consumed/purchased), measured in kilowatt-hours per year per square meter (kWh/year/m²).
  - Potential values: 111.3

- **source_eui**
  - Data type: Numeric
  - Definition: Total primary energy consumption normalized by area, taking into account the conversion efficiency of primary energy into secondary energy.
  - Potential values: 61.9

- **leed_level**
  - Data type: Categorical (Text)
  - Definition: LEED rating of the building (Leadership in Energy and Environmental Design), a widely used green building rating system.
  - Potential values: None

- **rating**
  - Data type: Categorical (Text)
  - Definition: Other building energy ratings.
  - Potential values: D1

Weather Dataset:

- **timestamp**
  - Data type: Date and time
  - Definition: Date and time in the format MM-DD-YYYY hh:mm:ss. Local timezone.
  - Potential values: 1/1/2016 0:00

- **site_id**
  - Data type: String
  - Definition: Animal-code-name for the site.
  - Potential values: Panther

- **airTemperature**
  - Data type: Float
  - Definition: The temperature of the air in degrees Celsius (ºC).
  - Potential values: 19.4

- **cloudCoverage**
  - Data type: Float
  - Definition: Portion of the sky covered in clouds, in oktas.
  - Potential values: 6

- **dewTemperature**
  - Data type: Float
  - Definition: The dew point (the temperature to which a given parcel of air must be cooled at constant pressure and water vapor content in order for saturation to occur) in degrees Celsius (ºC).
  - Potential values: 19.4

- **precipDepth1HR**
  - Data type: Float
  - Definition: The depth of liquid precipitation that is measured over a one-hour accumulation period (mm).
  - Potential values: 0

- **precipDepth6HR**
  - Data type: Float
  - Definition: The depth of liquid precipitation that is measured over a six-hour accumulation period (mm).
  - Potential values: 0

- **seaLvlPressure**
  - Data type: Float
  - Definition: The air pressure relative to Mean Sea Level (MSL) (mbar or hPa).
  - Potential values: 1019.4

- **windDirection**
  - Data type: Integer
  - Definition: The angle, measured in a clockwise direction, between true north and the direction from which the wind is blowing (degrees).
  - Potential values: 0

- **windSpeed**
  - Data type: Float
  - Definition: The rate of horizontal travel of air past a fixed point (m/s).
  - Potential values: 0

Meter Dataset:
- **sno**
  - Data type: Integer
  - Definition: Row count 
  - Potential values: 0
    
- **index**
  - Data type: Integer
  - Definition: Index value for each row
  - Potential values: 0
    
- **building_id**
  - Data type: Integer
  - Definition: Building identification number.
  - Potential values: 789
    
- **timestamp**
  - Data type: Integer
  - Definition: Date and time in the format MM-DD-YYYY hh:mm:ss. Local timezone
  - Potential values: 1/1/2016 12:00:00 AM
    
- **meter_reading**
  - Data type: Integer
  - Definition: representing the recorded consumption or usage of a utility
  - Potential values: 516.43
 

## Data Wrangling:

### Buildings Dataset:

**Missing Values:**

We can see there are many columns with missing data, Some columns has very high missing data and some has few or no missing data. We will be treating the missing data before modelling.

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/3e7efb28-b826-42c3-a540-6b2a0d68a358)

**Meter Type Observation:**

There are 8 types of energy meters potentially installed for each building: electricity, hotwater, chilledwater, steam, water, irrigation, solar, gas. We will first investigate how many energy meters are installed for 307 buildings.

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/ac794aed-c195-4158-9c70-b646f7f804b2)
![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/a36b447f-dccf-46e7-a868-aa59c09d0a4e)
             
From our initial observations, we have identified that gas, solar, irrigation, and water meters are installed in our target buildings. A single building may have multiple types of energy meters installed. Electrical meters are the most common type of meter across all buildings.

Our goal for this project is to understand the TOTAL energy consumption of each building. Based on our initial observations of the energy data, we see that the total energy consumption for each building is provided for each hour. Therefore, we can safely say that we will not need to use the meter type data in our analysis, and it can be removed from the dataset.

**Building Area Observation:**

Quick view of the total area of buildings. Majority of the buildings are below 20,000 sqm.

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/92c83531-af28-45a7-bce0-9fa255afd653)
![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/1020b7e9-1d5f-40ca-a1ed-f873b04f20b5)



**Building Category Observation:**

There are four columns: primaryspaceusage, sub_primaryspaceusage, industry, subindustry.

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/f0ad862e-179d-44db-b092-de4a53626de7)
![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/ca5db34f-f130-461f-aa65-9b683107cb57)

It has over 70 office buildings and about 46 education buildings in our dataset. This suggests that we could use them to create a model to predict energy consumption only for office and education buildings, but we need more data to confirm this. We also noticed that the features "sub_primaryspaceusage" and "subindustry" do not provide much information, so we removed them from the dataset.


**Building Energy Use Intensity:**

The columns "energystarscore", "eui", "site_eui", "source_eui", "leed_level", "rating" are associated with building EUI (energy use intensity). We will examine them one by one.

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/31863959-e9b1-4196-a1a2-33e489dfdefa)

Noticing that majority of the data for energy score is missing. We will drop the column.

Now we will review the following columns: 'eui', 'site_eui','source_eui'. All of them represent building energy use intensity.

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/0426592a-3143-4631-a0dd-15bf2185b52d)

Interesting note that two parking lots have the highest eui values. Majority of the eui stays between 0-500

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/c082f743-fee6-4e29-aa1e-5fd918a3c963)


**Other Building Parameters:**

We have less than 10% of data points for the columns: "heatingtype", "yearbuilt", "data_opened", "nuumberoffloors","occupants". It is not possible to find the data online. We will remove them from our analysis.
We used lat and lng information to identify building locations, we can have them removed.


### Weather Dataset:

**Missing Values:**

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/4460fc16-4d8d-4173-ba4e-674e6fc4482d)
![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/c12409cf-0525-428c-9aea-a0d644a3e06d)


**Timestamp:**

Timedelta('730 days 23:00:00')

There are 366 days in 2016 and 365 days in 2017, according to a fast google search. We should have 731 entries in our dataset overall. given that we are spread out over three sites. Each of us will conduct our own research.

This indicates that we should have 17,544 data points for our weather information assuming there are no missing data. A cursory glance indicates that more research is necessary, although it is most certainly not the case that we are missing any weather data at location Minneapolis.


**Cornell - airTemperature & dewTemperature**

About 3% of the data for the air temperature and dew temperature is missing. According to my knowledge from Google and my expertise in chemical engineering, the dew point is the temperature at which the air can precisely retain the moisture content. At any given temperature, the atmosphere has a limited capacity to store water vapour when it rains. Consequently, room temperature and the dew point are same. The dew point temperature and air temperature comparison provides useful information about humidity, which influences building energy usage. We'll hold onto them and carry out additional EDA research to fill in the blanks.

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/9334b505-0a63-4494-99a2-49c2932475ec)


**Cornell - windSpeed & windDirection**

The wind rose diagram for Cornell shows the distribution of wind speeds and wind directions for the year 2016. The wind rose is divided into eight sectors, each representing a different wind direction. The length of each sector represents the percentage of time that the wind blew from that direction. The thickness of each sector represents the average wind speed for that direction.

The wind rose shows that the prevailing wind direction in Cornell is from the southwest (SW). The wind blows from the SW for about 15% of the time. The average wind speed from the SW is about 14.5 miles per hour (mph).

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/ddd060f6-38fa-4667-9801-c4fdba1cdfbf)


**Ottawa - airTemperature & dewTemperature**

The chart shows the average air temperature and dew temperature in Ottawa, Ontario, Canada, for the year 2016. The air temperature is the average temperature in Ottawa, while the dew temperature is the temperature at which the air becomes saturated with water vapor and condensation begins to form.

The chart shows that the air temperature in Ottawa varies throughout the year, with the coldest months being January and February and the warmest months being July and August. The average air temperature in Ottawa ranges from -10.4°C in January to 22.1°C in July.

The dew temperature in Ottawa also varies throughout the year, but it is generally lower than the air temperature. The average dew temperature in Ottawa ranges from -15.6°C in January to 17.7°C in August.

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/7c9f1548-952f-4027-9ff7-76a505779d75)


**Ottawa - windSpeed & windDirection**

The wind rose diagram for Ottawa shows the distribution of wind speeds and wind directions for the year 2016. The wind rose is divided into eight sectors, each representing a different wind direction. The length of each sector represents the percentage of time that the wind blew from that direction. The thickness of each sector represents the average wind speed for that direction.

The wind rose shows that the prevailing wind direction in Ottawa is from the west (W). The wind blows from the W for about 15% of the time. The average wind speed from the W is about 12.1 mph.

Other common wind directions in Ottawa are from the southwest (SW) and the northwest (NW). The wind blows from the SW for about 11% of the time, and the average wind speed from the SW is about 11.8 mph. The wind blows from the NW for about 10% of the time, and the average wind speed from the NW is about 12.8 mph.

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/70977302-d56c-4240-be85-f8637c316b09)

## EDA:

All buildings are educational buildings and they are all from Ottawa, location and priUsage columns will be dropped.

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/8624f080-740b-4691-addd-c3126b248160)

In all, we have five academic buildings and fifteen college classrooms. The average total surface area, 30,066 sqm, is higher in the college classroom. The academic building is 9,714 square metres smaller. Since they are distinct building types, their patterns of energy use may also differ. When we get all the data, including the weather and energy consumption information, we will review them later. Due to the possibility of imbalanced data, the outcome will show whether we should split the data into different models.

### Correlation:
Dew temperature and air temperature appear to be highly related.



### Feature Engineering:
- Filled airTemperature,dewTemperature,seaLvlPressure, windDirection, windSpeed missing values with interpolation
We have 20 buildings' meter_data in our dataset. For model accuracy, each building's features will be put into a machine learning model for the meter reading prediction.
- We select building ID 789 as our target for analysis. At the mean time, for better accuracy, the dataset for the building will be split based on Canadian seasons.

We will be using 2016 and 2017 data, So the Selected features 

**Target variable:**
 - Meter Readings

**Feature variables:**
 - Air Temperature
 - dew Temperature
 - Sea Level Pressure
 - Wind Direction
 - Wind Speed
 - Month
 - Weekday
 - Hour

_______________________________________________

## Data Modeling:

### Linear Regression:
Linear regression is a statistical method that is used to model the relationship between two variables by fitting a linear equation to observed data. One variable, called the dependent variable, is considered to be influenced by the other variable, called the independent variable.
R Squared result:
training - 0.587, testing - 0.606
Mean Abosulte Error result:
training - 86.786, testing - 85.287

**Linear Regression Cross Validation:** 
Cross validation on the training data shows the scores are not very good (around 0.56 - 0.61). We will use GridSearchCV to find if we can find better linear regression models.

**Linear Regression - Hyper Parameter Search – GridSearchCV:**

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/fb58ed69-8d8b-4e7f-aacc-4399b11e4025)
![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/9affe34f-6b32-493f-8873-67f432f72860)

Even though the above suggests that a good value for k is 8. There was an initial rapid increase with k when k is 2 and 3. The r-square does not improve too much when k is bigger than 4. This is an indication that linear regression model might not be a good model for prediction. However, for curiosity, we will do below to see what features have more positive/negative impact on our results.

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/8a4d2a2b-b169-440f-accf-d8ca612cb522)

It appears that in the best linear regression model, the meter reading data has a positive relationship with hour and wind speed. From an engineering point of view, this may make sense from heat and mass transfer. However, as the R square showed that the linear model does not have good accuracy with an R square value around 0.6.

### Random Forest Model:

Random forest regression is a supervised machine learning algorithm that uses an ensemble of decision trees to make predictions. It is a popular algorithm for regression tasks because it is relatively robust to outliers and noise, and it can handle high-dimensional data.
**Random Forest Result and Cross Validation**
array([0.94986359, 0.96075064, 0.95885135, 0.94929202, 0.95699043])
**Random Forest Hyper Parameter Search - GridSearchCV**

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/aa6eba42-5dc7-4eb1-9e45-92bb5e0aeb92)

The random forest model shows a better performance compared with the linear regression model. The model has an R square score of 0.956 in cross validation. The model shows that the temperature, hour, and month are the top three features that can impact the meter reading.


**LightGBM Model - Random Search CV & Grid Search CV**

Gradient boosting machines (GBMs) are a type of machine learning algorithm that uses an ensemble of weak prediction models to make a more accurate prediction. GBMs are a popular choice for many machine learning applications because they are relatively simple to understand and implement, and they can be very effective in improving the accuracy of prediction models.

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/e2b1d1e6-03f1-4c0a-9fe5-400a3084d38c)

array([0.94256897, 0.95378344, 0.94756481, 0.94469161, 0.95232245])
Overall, the random forest model performed better than LightGBM models. The grid search cv find a better LightGBM models comparing with random search, however it took longer time.

### Model Evaluation:

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/4a7fa29d-9f9e-45c5-a075-78dd805f4fb2)

![image](https://github.com/DATA-606-2023-FALL-MONDAY/Annavarapu_Ajith/assets/51732096/bc462e05-02a4-42c9-9d14-b6e90120c979)

Based on the data presented, the random forest model with the best parameters is selected to be the best model because it has the lowest MAE value and highest r square value.

## Practical Application:

**Scenario 1: Increase in Annual Temperature:**

The model indicates that a rise in the average annual temperature will lead to reduced energy intensity and costs for the targeted building. This happens because as the annual temperature increases, the energy needed to maintain the building's warmth during winter decreases. Even though more energy is required to cool the building in hotter summers, overall energy consumption decreases with a rise in the annual average temperature. The model demonstrates 10 temperature scenarios. For example, a 0.4°C increase in the annual average temperature results in a $1.0k increase in annual energy costs.

**Scenario 2: Decrease in Annual Temperature:**

The model demonstrates that a decrease in the average annual temperature will lead to increased energy intensity and costs for the target building. This is primarily due to colder winter temperatures. Despite the cooler summer weather requiring less energy for cooling, the overall energy costs rise. The model presents 10 temperature scenarios. For instance, a 0.4°C decrease in the annual average temperature leads to a $1.2k increase in annual energy costs.

**Scenario 3: Seasonal Temperature Variations:**
The modeled temperature conditions align more closely with reality, depicting hotter summers and colder winters. Colder winters result in higher energy consumption to maintain the building's temperature, while hotter summers increase the energy required for cooling. The model indicates that climate change and extreme weather can escalate building energy costs. It generates 10 different temperature, demonstrating, for instance, that a 0.4°C annual temperature variation can increase annual energy costs by $1.7k.

It's essential to note that the building in focus is an academic establishment housing offices for professors and classrooms for students. The building's energy consumption primarily stems from mechanical and electrical equipment. Should a model be created for industrial facilities with high energy usage for production, future variations in temperature could elevate energy costs. In such cases, a strong business case might justify upgrading existing equipment to curtail operational costs.

## Conclusion:

This project aims to investigate the impact of minor temperature fluctuations caused by climate change on the energy consumption patterns and expenditures of buildings. The study focuses on academic buildings situated in Southern Ontario, Canada. Different weather conditions and energy usage patterns in various buildings will yield distinct outcomes.

The project commenced with the examination of three datasets: Building Dataset, Meter Dataset, and Weather Dataset. We identified 1,635 buildings and 3,3053 energy meters, along with weather data encompassing parameters such as air temperature, wind speed, and wind direction for a two-year period (2016 and 2017).

Following standard data science procedures, including data wrangling, data cleaning, and statistical analysis, we selected an academic building in Ottawa for data modeling, machine learning model selection, and final data prediction.

## References:

- Miller, C., Kathirgamanathan, A., Picchetti, B. et al. The Building Data Genome Project 2, energy meter data from the ASHRAE Great Energy Predictor III competition. Sci Data 7, 368 (2020). https://doi.org/10.1038/s41597-020-00712-x

- Mel Keytingan M. Shapi, Nor Azuana Ramli, Lilik J. Awalin, Energy consumption prediction by using machine learning for smart building: Case study in Malaysia, Developments in the Built Environment, Volume 5, 2021, 100037, ISSN 2666-1659, https://doi.org/10.1016/j.dibe.2020.100037.

- Lin, X.; Yu, H.; Wang, M.; Li, C.; Wang, Z.; Tang, Y. Electricity Consumption Forecast of High-Rise Office Buildings Based on the Long Short-Term Memory Method. Energies 2021, 14, 4785. https://doi.org/10.3390/en14164785 

- El Khantach, Abdelkarim & Hamlich, Mohamed & Belbounaguia, Nour Eddine. (2019). Short-term load forecasting using machine learning and periodicity decomposition. AIMS Energy. 7. 382-394. 10.3934/energy.2019.3.382. 

- González Briones, Alfonso & Hernández, Guillermo & Pinto, Tiago & Vale, Zita & Corchado Rodríguez, Juan. (2019). A Review of the Main Machine Learning Methods for Predicting Residential Energy Consumption. 1-6. 10.1109/EEM.2019.8916406.
