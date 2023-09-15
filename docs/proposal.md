## 1. Title and Author

**Project Title:** Energy Forecaster

Prepared for UMBC Data Science Master Degree Capstone by Dr Chaojie (Jay) Wang

**Author Name** Ajith Annavarapu

**GitHub:** https://github.com/Ajith-oo7

- LinkedIn : 
- Link to your PowerPoint presentation file
- Link to your YouTube video 
    
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
- Average annual temperature decrease by 0.2 degree, 0.4 degree, 0.8 degree, 1.2 degrees, 1.8 degrees, 3 degrees, 5 degrees, 10 degrees, and 15 degrees.
- Average annual temperature **increase only in spring and summer, and decrease in fall and winter by 0.2 degree, 0.4 degree, 0.8 degree, 1.2 degrees, 1.8 degrees, 3 degrees, 5 degrees, 10 degrees, and 15 degrees.

## 3. Data 

**Describe the datasets you are using to answer your research questions:**

The project involves the utilization of two distinct datasets: one pertains to building energy consumption, and the other comprises weather data.

For the energy consumption data in this project, the source is the Building Data Genome 2 (BDG2) dataset. BDG2 is an openly available dataset consisting of data from 3,053 energy meters across 1,636 buildings. This dataset spans a two-year timeframe and encompasses data from more than 30 academic buildings situated in Ottawa, Canada. From this dataset, a specific building is selected as the subject of the case study.

The weather data for Ottawa is obtained from Statistics Canada, which serves as the national statistical office of Canada. Statistics Canada plays a crucial role in providing essential information on various aspects of Canada's environment, society, and economy, including weather data.

**Data sources:**
-https://zenodo.org/record/3887306

**Data size:**
Building Dataset : 264 KB
Weather Dataset : 18.2 MB

**Data shape:** 
Building Dataset : 1636 Rows and 32 Columns
Weather Dataset : 331166 Rows and 10 Columns

**Time period:** 
Building Dataset : 2016-2017
Weather Dataset : 2016-2017

**What does each row represent?**(a patient, a school, a crime, etc.):
Building Dataset : Each row in the dataset represents a distinct building, providing detailed information about its location, primary usage, total area, and resource utilization 

Weather Dataset : Each row in the dataset represents a specific timestamp at a particular site (site_id) and provides detailed weather information for that moment. 

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







 
**Which variable/column will be your target/label in your ML model?**
 - Air Temperature
 - Cloud Coverage
 - Dew Point
 - Wind Direction
 - Wind Speed
 - Building Footprint
 - Hour
 - Weekday
 - Month
 - Sea Level Pressure
 - Meter Readings

**Which variables/columns may be selected as features/predictors for your ML models?**
 - Air Temperature
 - dew Temperature

