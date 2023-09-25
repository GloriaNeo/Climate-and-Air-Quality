# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Exploring Climate Data of Singapore
---

#### Contents:

- Problem Statement
- Background
- Data Cleaning
- EDA
- Conclusion<br><br>
---

#### Problem Statement:
With abundant rainfall and predominantly low-lying terrain, the management of floods remains a continual challenge in Singapore. PUB, which stands for Public Utilities Board, is responsible for various aspects of flood protection in Singapore.<br><br>
We have been hired by PUB to analyse rainfall trends in Singapore. The analysis could provide insights to identifying flood-prone areas, implementing proper stormwater management, and maintaining the functionality of drainage infrastructure. <br><br>

#### Background:


<br>


---

#### Datasets:

There are 2 datasets provided, these correspond to rainfall information. 

* [`rainfall-monthly-number-of-rain-days.csv`](./data/rainfall-monthly-number-of-rain-days.csv): Monthly number of rain days from 1982 to 2022. A day is considered to have “rained” if the total rainfall for that day is 0.2mm or more.
* [`rainfall-monthly-total.csv`](./data/rainfall-monthly-total.csv): Monthly total rain recorded in mm(millimeters) from 1982 to 2022

<mark>Other relevant weather datasets that were used:

* [`rainfall-monthly-number-of-rain-days.csv`](./data/rainfall-monthly-number-of-rain-days.csv): Monthly number of rain days from 1982 to 2022. A day is considered to have “rained” if the total rainfall for that day is 0.2mm or more.
* [`rainfall-monthly-total.csv`](./data/rainfall-monthly-total.csv): Monthly total rain recorded in mm(millimeters) from 1982 to 2022
<br>

#### Additional Data
<mark>Relevant flooding and drainage related datasets:

* [`rainfall-monthly-number-of-rain-days.csv`](./data/rainfall-monthly-number-of-rain-days.csv): Monthly number of rain days from 1982 to 2022. A day is considered to have “rained” if the total rainfall for that day is 0.2mm or more.
* [`rainfall-monthly-total.csv`](./data/rainfall-monthly-total.csv): Monthly total rain recorded in mm(millimeters) from 1982 to 2022

---

#### Data Cleaning

The usual data cleaning of checking for shape, data types, missing values and duplicates are done.

Special Mentions are:

Train Data Set:


Irrelevent features dropped: 

In summary, _ columns and _ duplicated rows were dropped from the train dataset.

---

#### EDA

After cleaning our datasets, we carry out an initial exploratory analysis. Through use of various plots and graphs, we are able to visualize the data and derive some preliminary insights. We used a series of charts for data visualation such as plotly for the map charts, and scatter plots for relationships. We also plotted the weather features to look at its significance to mosquitoes and wnv. The Spray dataset was combined with train and was plotted using plotly to give us a visual of the areas with high number of mosquitoes caught, wnv pressense and the spray area.

---

#### Conclusion

After cleaning our datasets, we carry out an initial exploratory analysis. Through use of various plots and graphs, we are able to visualize the data and derive some preliminary insights. We used a series of charts fo

---

