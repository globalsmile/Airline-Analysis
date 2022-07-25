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

# Introduction
According to [WikiHow](https://www.wikihow.com/Survive-a-Plane-Crash):

The chances of dying on a commercial airline flight are actually as low as 9 million to 1. That said, a lot can go wrong at 33,000 feet (10,058.4 m) above the ground, and if you’re unlucky enough to be aboard when something does, the decisions you make could mean the difference between life and death. Almost 95% of airplane crashes have survivors, so even if the worst does happen, your odds aren't as bad as you might think

So let's see...

---
# Problem Statement
The main objective of this project is to perform an exploratory data analysis on the dataset and visualize the data to find some weird or interesting insights.
However we will also try to find answers to the following questions:
- How many planes crashed yearly?
- How many people were aboard?
- what is the number of crashes by operator?
- what is the number of crashes by the type of aircraft?
- How is the airplane crash geographically distributed?

# Data Sourcing
This Dataset was created on Kaggle in September 2016 but the original version was hosted by Open Data by Socrata at:
https://opendata.socrata.com/Government/Airplane-Crashes-and-Fatalities-Since-1908/q2te-8cvq (no longer available). The dataset contains data of airplane accidents involving civil, commercial and military transport worldwide from `1908-09-17 to 2009-06-08`

Data:  Data can be accessed from this link  https://aka.ms/30DLDATGitHubRepo Locate project folder and download the csv file.
The dataset contains `13 columns and 5268 rows` of data.

# Data Transformation
For the purpose of this analysis, Microsoft Power BI was used to transform the data.

Data transformation begins in Power query after the data has been loaded into Microsoft Power BI.

- In Power query the table containing the dataset is named `Airplane_Crashes_and_Fatalities_since_1908`. It contains `13 columns and 5268 rows` data we will be working with.

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

- To clean the data, power query was used to check the column's profile, quality, and distribution. it was found out that some columns were missing some values.

The table below shows the number of missing values in each of the columns:
| Column Name | No. of missing values |
| ----------- | ----------- |
| Date | 0 |
| Time | 1539 |
| Location | 5 |
| Operator | 10 |
| Flight | 3663 |
| Route | 762 |
| Type | 14 |
| Registration | 271 |
| Cn/Ln | 663 |
| Aboard | 0 |
| Fatalities | 0 |
| Ground | 0 |
| Summary | 59 |

- To account for the missing values, each column containing a missing value had to be manipulated.

The table below shows each of the column with a missing value and the kind of manipulation that was done:
| Column Name | Data manipulation |
| ----------- | ----------- |
| Time | Replaced the missing values with an arbitrary time values - (00:00) |
| Location | Replaced the missing values with 'unknown'|
| Operator | Replaced the missing values with 'unknown' |
| Flight | Replaced the missing values with 'unknown' |
| Type | Replaced the missing values with 'unknown' |
| Registration | Replaced the missing values with 'unknown' |
| Cn/Ln | Replaced the missing values with 'unknown' |
| Summary | Replaced the missing values with 'unknown' |

After the columns with missing values were manipulated, each column in the table `Airplane_Crashes_and_Fatalities_since_1908`  was then validated to have the correct data type to ensure data accuracy.

- Given that we have numerous dates and time in the dataset, a date table was needed so as to reference the date and the time more accurately.
A date table was created with the M-formula `List.Dates(#date(1908,09,17), 365*101, #duration(1,0,0,0)`

Here is a breakdown of what the formula does:

For airplane crash and fatalities data, we want the start date to reflect the earliest date that we have in the data: September 17, 1908. Additionally, you want to see date for the 101 years, including dates in the future.This approach ensures that, as new airplane crash and fatalities data flows in you won't have to re-create this table.Also the duration represents data point for everyday.

The date table was named `Calender` and the flight column was renamed to `Flight ID` for clarity.

---

# Data Modeling

