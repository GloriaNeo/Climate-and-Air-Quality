# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Exploring Climate Data of Singapore
---

#### Contents:

- Context
- Problem Statement
- Outside Research
- Data Cleaning
- Data Dictionary
- Conclusion<br><br>
---

#### Context:
Ongoing climate change, the return of El Nino and La Nina events, recurrent transboundary Southeast Asian Haze. These are some of the major factors that have caused notable shifts in weather patterns. This phenomenon has been apparent in 2023, where we have been experiencing erratic weather variations in Singapore, including heavy rainfall and heatwaves. As such, Air Quality is increasingly a topic of concern. The increased frequency and intensity of extreme weather events contribute to higher levels of air pollutants, including particulate matter (PM2.5 and PM10), nitrogen dioxide (NO2), sulfur dioxide (SO2), and ozone (O3).<br><br>

#### Problem Statement:
You are part of the National Environment Agency (NEA) taskforce set up to develop a set of air quality early warning systems to predict potential periods of air quality deterioration, allowing the government to take necessary precautionary action. As such, your EDA should provide insights to the impact (immediacy, magnitude) that the various weather factors have on air quality.<br><br>

##### Some guiding questions to address:
* How are weather conditions, including temperature, humidity, wind patterns, and rainfall, related to each other?
* How do the various weather conditions affect the various air pollutants?
* Which pollutants fail to meet NEA's target levels, or are at risk of exceeding ideal levels if erratic weather conditions occur?
* Which weather conditions could potentially help in preducting air quality movements?
<br>

---

#### Outside Research:
Research has shown that current weather phenomena have significant impacts on air quality. For instance, studies have demonstrated that temperature inversions, prevalent during stagnant weather conditions, can trap pollutants near the surface, leading to higher concentrations and poorer air quality. Additionally, research has explored the effects of rain versus hot weather on air quality. Rainfall has been found to play a beneficial role by removing pollutants through wet deposition, resulting in improved air quality. On the other hand, hot weather conditions can exacerbate the formation of secondary pollutants like ozone, leading to increased pollution levels.

In response to these challenges, Singapore has implemented a multi-pronged approach of "integrated urban and industrial planning, together with development control', along with additional measures such as "legislation, strict enforcement programmes, and air quality monitoring". Furthermore, Singapore has set ambitious targets for air quality improvement. In July 2010, the Advisory Committee on Ambient Air Quality recommended a set of air quality targets for Singapore - year 2020, in alignment with World Health Organization's guidelines.

---

#### Datasets:

**Datasets corresponding to rainfall information:**

* [`rainfall-monthly-number-of-rain-days.csv`](./data/rainfall-monthly-number-of-rain-days.csv): Monthly number of rain days from 1982 to 2022. A day is considered to have “rained” if the total rainfall for that day is 0.2mm or more.
* [`rainfall-monthly-total.csv`](./data/rainfall-monthly-total.csv): Monthly total rain recorded in mm(millimeters) from 1982 to 2022
* [`rainfall-monthly-highest-daily-total.csv`](./data/rainfall-monthly-highest-daily-total.csv): The highest daily total rainfall for the month recorded
* [`relative-humidity-monthly-mean`](./data/relative-humidity-monthly-mean.csv): The monthly mean relative humidity recorded
* [`SurfaceAirTemperatureMonthlyMeanDailyMaximum`](./data/SurfaceAirTemperatureMonthlyMeanDailyMaximum.csv): The monthly mean daily minimum temperature recorded at the Changi Climate Station
* [`surface-air-temperature-monthly-mean-daily-minimum`](./data/surface-air-temperature-monthly-mean-daily-minimum.csv): The monthly mean daily maximum temperature recorded at the Changi Climate Station
* [`SurfaceAirTemperatureMonthlyAbsoluteExtremeMaximum`](./data/SurfaceAirTemperatureMonthlyAbsoluteExtremeMaximum.csv): The monthly extreme maximum air temperature recorded at the Changi Climate Station
* [`SurfaceAirTemperatureMonthlyAbsoluteExtremeMinimum`](./data/SurfaceAirTemperatureMonthlyAbsoluteExtremeMinimum.csv): The absolute extreme minimum air temperature recorded at the Changi Climate Station
* [`sunshine-duration-monthly-mean-daily-duration`](./data/sunshine-duration-monthly-mean-daily-duration.csv): The monthly mean sunshine hours in a day recorded at the Changi Climate Station

**Datasets corresponding to Air Quality:**
* [`air-pollutant-ozone`](./data/air-pollutant-ozone.csv): Annual daily maximum 8-hr means for ozone (µg/m3)
* [`air-pollutant-particulate-matter-pm2-5`](./data/air-pollutant-particulate-matter-pm2-5.csv): Annual means for PM2.5 (µg/m3)
* [`AirPollutantParticulateMatterPM10`](./data/AirPollutantParticulateMatterPM10.csv): Annual 24-hr means (99th percentile) for PM10 (µg/m3)
* [`AirPollutantCarbonMonoxide2ndMaximum8HourMean`](./data/AirPollutantCarbonMonoxide2ndMaximum8HourMeancsv): Annual maximum 8-hr means for carbon monoxide (mg/m3) are based on WHO Air Quality Guidelines (for Europe, 2000).
* [`AirPollutantNitrogenDioxide`](./data/AirPollutantNitrogenDioxide.csv): Annual means for nitrogen dioxide (µg/m3)
* [`AirPollutantSulphurDioxide`](./data/AirPollutantSulphurDioxide.csv): Annual means for sulphur dioxide (µg/m3)
* [`historical-24-hr-psi`](./data/historical-24-hr-psi.csv): Historical regional 24-hr PSI

---

#### Data Cleaning

**Data Import Strategy**<br>
To make things more organised, I will be importing data in 2 batches - 1) Weather-related, 2) Air Quality related. Within these 2 batches, I have decided to combine the dataframes where possible, if there are common identifier variables between the dataframes that I can use to merge.

**Data Cleaning Strategy**<br>
The usual data cleaning of checking for shape, data types, missing values and duplicates are done.
As most of the data came from the same source: data.gov.sg, data was easy to clean with little or no null values. Most NEA-sourced data (for the weather conditions and air pollutants) involved data collected from a similar period, with similar date-time formatting.

---

#### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**date**|*datetime*|all datasets|1982, January to 2023, May|
|**year**|*datetime*|all datasets|1982 to 2023|
|**month**|*datetime*|all datasets|Jan - Dec, represented by 01 - 12 respectively|
|**rainy_days**|*int*|rainfall-monthly-number-of-rain-days|The number of rain days (day with rainfall amount of 0.2mm or more) in a month recorded| 
|**total_rainfall**|*float*|rainfall-monthly-total|The total monthly rainfall in mm| 
|**max_daily_rainfall**|*float*|rainfall-monthly-highest-daily-total|The highest daily total rainfall for the month| 
|**mean_rh**|*float*|relative-humidity-monthly-mean|The monthly mean relative humidity recorded|
|**min_daily_temp**|*float*|SurfaceAirTemperatureMonthlyMeanDailyMaximum|The monthly mean daily minimum temperature recorded| 
|**max_daily_temp**|*float*|surface-air-temperature-monthly-mean-daily-minimum|The monthly mean daily maximum temperature recorded|
|**extr_max_temp**|*float*|SurfaceAirTemperatureMonthlyAbsoluteExtremeMaximum|The monthly extreme maximum air temperature recorded|
|**extr_min_temp**|*float*|SurfaceAirTemperatureMonthlyAbsoluteExtremeMinimum|The absolute extreme minimum air temperature recorded| 
|**mean_sunshine_hrs**|*float*|sunshine-duration-monthly-mean-daily-duration|The monthly mean sunshine hours in a day recorded| 
|**ozone_max_mean**|*float*|air-pollutant-ozone|Annual daily maximum 8-hr means for ozone (µg/m3)|
|**pm2.5_mean**|*float*|air-pollutant-particulate-matter-pm2-5|Annual means for PM2.5 (µg/m3)|
|**pm10_mean**|*float*|AirPollutantParticulateMatterPM10|Annual 24-hr means (99th percentile) for PM10 (µg/m3)|
|**co_max_mean**|*float*|AirPollutantCarbonMonoxide2ndMaximum8HourMean|Annual maximum 8-hr means for carbon monoxide (mg/m3)| 
|**no2_mean**|*float*|AirPollutantNitrogenDioxide|Annual means for nitrogen dioxide (µg/m3)|
|**so2_mean**|*float*|AirPollutantSulphurDioxide|Annual means for sulphur dioxide (µg/m3)| 
|**psi**|*float*|historical-24-hr-psi|Historical regional 24-hr PSI|

---

#### Conclusion

Some key takeaways and recommendations

* We can see the effects of global warming in the graphs, with temperatures generally rising, and total rainfall amounts falling over time.
* From the research done, theory tells us it is likely possible that decreased rainfall, and hotter temperatures should lead to deterioration of air quality. Through comparisen between figure 1 and figure 3, we can see that as per our research, pollutant levels are generally decreasing too. However, correlation is not strong, and more in depth analysis would have to gain more insights. As majority of the pollutant datasets only provide a yearly mean, data was of lower granularity. 
* Temperature and rainfall are seasonal variables, and the seasonality remains quite stable over time for the Singapore context. Considering we would like to develop a set of air quality early warning systems to predict air quality, it is a good sign that weather conditions are generally stable, so that any variations would be able to serve as an alert to prepare for potential air quality changes.
* Relative humidity seems to have the strongest correlation to the various pollutants, so this relationship should be further explored for the modelling and prediction stage.

It is also important to note that while our focus is currently on weather and its impact on air quality, we would need to consider several other factors in order to develop a comprehensive air quality early warning system. Other factors would include:
* Emissions from human activities - Industrial plants, transportation, etc.
* Natural sources of pollution (volcanic eruptions, wildfires, etc) from our surrounding countries leading to transboundary haze

---

