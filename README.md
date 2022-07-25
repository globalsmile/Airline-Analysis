# Airplane Crashes and Fatalities Analysis(1908 - 2009)
<img align="right" alt="Data Analytics" width="1000" height = "400" src="https://user-images.githubusercontent.com/106287208/180620178-7696afd1-82f1-48fb-81e4-6e87db068d07.jpg">

---


## Table of Contents

- [Introduction](https://github.com/globalsmile/Airline-Analysis#introduction)
- [Problem Statement](https://github.com/globalsmile/Airline-Analysis#Problem-Statement)
- [Data Sourcing](https://github.com/globalsmile/Airline-Analysis#Data-Sourcing)
- [Data Transformation](https://github.com/globalsmile/Airline-Analysis#Data-Transformation)
- [Data Modeling](https://github.com/globalsmile/Airline-Analysis#Data-Modeling)
- [Data Visualization](https://github.com/globalsmile/Airline-Analysis#Data-Visualization)
- [Data Analysis](https://github.com/globalsmile/Airline-Analysis#Data-Analysis)
- [Insights](https://github.com/globalsmile/Airline-Analysis#Insights)

---

## Introduction
According to [WikiHow](https://www.wikihow.com/Survive-a-Plane-Crash):

The chances of dying on a commercial airline flight are actually as low as 9 million to 1. That said, a lot can go wrong at 33,000 feet (10,058.4 m) above the ground, and if you’re unlucky enough to be aboard when something does, the decisions you make could mean the difference between life and death. Almost 95% of airplane crashes have survivors, so even if the worst does happen, your odds aren't as bad as you might think

So let's see...

---
## Problem Statement
The main objective of this project is to perform an exploratory data analysis on the dataset and visualize the data to find some weird or interesting insights.
However we will also try to find answers to the following questions:
- How many planes crashed yearly?
- How many people were aboard?
- what is the number of crashes by operator?
- what is the number of crashes by the type of aircraft?
- How is the airplane crash geographically distributed?

## Data Sourcing
This Dataset was created on Kaggle in September 2016 but the original version was hosted by Open Data by Socrata at:
https://opendata.socrata.com/Government/Airplane-Crashes-and-Fatalities-Since-1908/q2te-8cvq (no longer available). The dataset contains data of airplane accidents involving civil, commercial and military transport worldwide from `1908-09-17 to 2009-06-08`

Data:  Data can be accessed from this link  https://aka.ms/30DLDATGitHubRepo Locate project folder and download the csv file.
The dataset contains `13 columns and 5268 rows` of data.

## Data Transformation
For the purpose of this analysis, Microsoft Power BI was used to transform the data.

Data transformation begins in Power query after the data has been loaded into Microsoft Power BI.

In Power query the table containing the dataset is named `Airplane_Crashes_and_Fatalities_since_1908`. It contains `13 columns and 5268 rows` data we will be working with.

The table below shows the column names and their description:
| Column Name | Description |
| ----------- | ----------- |
| Date | Represents the date of the accident |
| Time | Represents the time(local) of the accident in 24hrs and in the format hh:mm |
| Location | Represents the location of the accident |
| Operator | Represents the airline or the operator of the aircraft |
| Flight | Represents the flight ID assigned by the aircraft operator |
| Route | Represents the  complete or partial route flown prior to the accident |
| Type | Represents the aircraft type |
| Registration | Represents ICAO registration of the aircraft |
| Cn/Ln | Represents the construction or serial number/line or fuselage number |
| Aboard | Represents the total number of people aboard the plane |
| Fatalities | Represents the number of fatalities |
| Ground | Represnts the total number of people killed on the ground by the aircraft |
| Summary | Contains brief description of the accident and cause if known |

