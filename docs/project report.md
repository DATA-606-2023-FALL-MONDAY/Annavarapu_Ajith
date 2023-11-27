## 1. Title and Author

**Project Title:** Energy Forecaster

Prepared for UMBC Data Science Master Degree Capstone by Dr Chaojie (Jay) Wang

**Author Name:** Ajith Annavarapu

**GitHub:** https://github.com/Ajith-oo7

**LinkedIn:** https://www.linkedin.com/in/ajith-anna-11369b291/ 

**PowerPoint presentation file:**

**Link to your YouTube video:** 
    
## 2. Background

**What is the Project about?**

Energy Predictor forecasts how changes in climatic conditions will affect a building's energy consumption by integrating the building's hourly energy consumption data with hourly weather data, enabling facility managers to make the optimal choices among 
1. Take no action! 
1. Invest in renovations to reduce operational costs in the future! 
1. Only invest money when necessary!

**Why does it matter?**

The objective of this project is to demonstrate the possibilities achievable through machine learning.  This illustration is relevant to asset management, engineering condition assessment, and decision-making concerning engineering capital and maintenance. Some potential applicable scenarios include:
- Utilizing Pump SCADA (Supervisory Control and Data Acquisition) data, weather data, HVAC (Heating, Ventilation, and Air Conditioning) SCADA, and energy consumption data to develop optimized strategies for controlling building mechanical systems, aimed at reducing energy consumption.
- Employing Air Blower SCADA data, influent sewage SCADA data (including flow rate and temperature), effluent SCADA data, and weather information to enhance the efficiency of variable-frequency drives (VFDs) for air blowers.
- Enhancing predictive environmental assessment by considering various factors such as public, human, and engineering-related elements.

**What are your research questions?**

How would annual energy expenditure change under the following scenarios:
- Average annual temperature increase by 0.2 degree, 0.4 degree, 0.8 degree, 1.2 degrees, 1.8 degrees, 3 degrees, 5 degrees, 10 degrees, and 15 degrees.

Increase in Annual Temperature: The model indicates that a rise in the average annual temperature will lead to reduced energy intensity and costs for the targeted building. This happens because as the annual temperature increases, the energy needed to maintain the building's warmth during winter decreases. Even though more energy is required to cool the building in hotter summers, overall energy consumption decreases with a rise in the annual average temperature. The model demonstrates 10 temperature scenarios. For example, a 0.4°C increase in the annual average temperature results in a $1.0k increase in annual energy costs.

- Average annual temperature decrease by 0.2 degree, 0.4 degree, 0.8 degree, 1.2 degrees, 1.8 degrees, 3 degrees, 5 degrees, 10 degrees, and 15 degrees.

Decrease in Annual Temperature: The model demonstrates that a decrease in the average annual temperature will lead to increased energy intensity and costs for the target building. This is primarily due to colder winter temperatures. Despite the cooler summer weather requiring less energy for cooling, the overall energy costs rise. The model presents 10 temperature scenarios. For instance, a 0.4°C decrease in the annual average temperature leads to a $1.2k increase in annual energy costs.

- Average annual temperature **increase only in spring and summer, and decrease in fall and winter by 0.2 degree, 0.4 degree, 0.8 degree, 1.2 degrees, 1.8 degrees, 3 degrees, 5 degrees, 10 degrees, and 15 degrees.

The modeled temperature conditions align more closely with reality, depicting hotter summers and colder winters. Colder winters result in higher energy consumption to maintain the building's temperature, while hotter summers increase the energy required for cooling. The model indicates that climate change and extreme weather can escalate building energy costs. It generates 10 different temperature, demonstrating, for instance, that a 0.4°C annual temperature variation can increase annual energy costs by $1.7k.
  
It's essential to note that the building in focus is an academic establishment housing offices for professors and classrooms for students. The building's energy consumption primarily stems from mechanical and electrical equipment. Should a model be created for industrial facilities with high energy usage for production, future variations in temperature could elevate energy costs. In such cases, a strong business case might justify upgrading existing equipment to curtail operational costs.

## 3. Data 

**Describe the datasets you are using to answer your research questions:**

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

**Data Discription:**
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
 
**Which variable/column will be your target/label in your ML model?**
 - Meter Readings

**Which variables/columns may be selected as features/predictors for your ML models?**
 - Air Temperature
 - dew Temperature
 - Sea Level Pressure
 - Wind Direction
 - Wind Speed
 - Month
 - Weekday
 - Hour







**4. Exploratory Data Analysis (EDA)
 - Perform data exploration using Jupyter Notebook
 - You would focus on the target variable and the selected features and drop all other columns.
 - produce summary statistics of key variables
 - Create visualizations (I recommend using Plotly Express)
 - Find out if the data require cleansing:
 - Missing values?
 - Duplicate rows?
 - Find out if the data require splitting, merging, pivoting, melting, etc.
 - Find out if you need to bring in other data sources to augment your data.
 - For example, population, socioeconomic data from Census may be helpful.
 - For textual data, you will pre-process (normalize, remove stopwords, tokenize) them before you can analyze them in predictive analysis/machine learning.
 - Make sure the resulting dataset need to be "tidy":
 - each row represent one observation (ideally one unique entity/subject).
 - each columm represents one unique property of that entity.


##5. Model Training
 - What models you will be using for predictive analytics?
 - How will you train the models?
 - Train vs test split (80/20, 70/30, etc.)
 - Python packages to be used (scikit-learn, NLTK, spaCy, etc.)
 - The development environments (your laptop, Google CoLab, GitHub CodeSpaces, etc.)
 - How will you measure and compare the performance of the models?
   
##6. Application of the Trained Models
 - Develop a web app for people to interact with your trained models. Potential tools for web app development:
 - Streamlit (recommended for its simplicity and ease to learn)
 - Dash
 - Flask
   
##7. Conclusion
 - Summarize your work and its potetial application 
 - Point out the limitations of your work
 - Lessons learned
 - Talk about future research direction
   
##8. References
 - List articles, blogs, and websites that you have referenced or used in your project.


