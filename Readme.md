# Introduction

In this project, I am going to analyse the immigration dataset, city demograhic, Temperature Dataset provided by udacity as well as the airline datset I have downloaded from openflights.org to perform many analytics analysis by building a star schema.

This schema gives flexibility running different analysis and answering questions like:
* tourist are going mostly to which area in each month of the year
* most popular arlines and if direct flights or not
* people are coming to which state reference to home country
* female between 20 and 40 going to which city with high foreign born
* Bussiness vistors analysis and relation with city demographic in terms of population

# Data sources:

* I94 Immigration Data: This data comes from the US National Tourism and Trade Office. A data dictionary is included in the workspace. This is where the data comes from https://travel.trade.gov/research/reports/i94/historical/2016.html
* World Temperature Data: This dataset came from Kaggle. You can read more about it from: https://www.kaggle.com/berkeleyearth/climate-change-earth-surface-temperature-data
* U.S. City Demographic Data: This data comes from OpenSoft. You can read more about it from: https://public.opendatasoft.com/explore/dataset/us-cities-demographics/export/
* Airport Code Table: This is a simple table of airport codes and corresponding cities. It comes from: https://datahub.io/core/airport-codes#data
* the airline datset I have downloaded from openflights.org

# Overview for the structure of the tables

![image.png](attachment:image.png)

# Data Dictionary

Fact table logs_immigration coming from the immigration data:
* cicid: record identifier
* I94YR: Year of the immigration record
* I94MON: Month of the immigration record
* I94PORT: port of entry
* ARRDATE: arrival date of immigrant
* I94MODE: mode of arrival 
* DEPDATE: departure date 
* COUNT: always 1 for some statistics evaluation 
* DTADFILE: dates in the format YYYYMMDD 
* AIRLINE: Airline used to arrive in U.S. 
* FLTNO: Flight number of Airline used to arrive in U.S. 
* ADMNUM: Admission Number of the Visa 
* municipality: the city of arrival in the US

Dimensions table:

1.Immigrant:
* cicid: record identifier
* I94CIT: immigrant's country of citizenship
* I94RES: immigrant's country of residence 
* I94ADDR: immigrant's address inside US
* I94BIR: Age of immigrant in Years 
* OCCUP: Occupation that will be performed in U.S. 
* BIRYEAR:  4 digit year of birth 
* GENDER: Non-immigrant sex 
* INSNUM:  INS number 

2.Visa:
* VISAPOST: State where where Visa was issued 
* DTADDTO: Date to which admitted to U.S. (allowed to stay until) 
* ADMNUM: Admission Number
* VISATYPE: Class of admission legally admitting the non-immigrant to temporarily stay in U.S.
* I94VISA: Visa codes ( Business, pleasure, student)
* ENTDEPA: Arrival Flag - admitted or paroled
* ENTDEPD: Departure Flag - Departed, lost I-94 or is deceased
* ENTDEPU: Update Flag - Either apprehended, overstayed, adjusted to perm residence
* MATFLAG: Match flag - Match of arrival and departure records 


3.Airline:
* Airline ID: Unique OpenFlights identifier for this airline.
* Name: Name of the airline
* Alias: Alias of the airline. For example, All Nippon Airways is commonly known as "ANA".
* IATA: 2-letter IATA code, if available.
* ICAO: 3-letter ICAO code, if available.
* Callsign: Airline callsign.
* Country: Country or territory where airport is located
* Active: status if the airline is active or not

4.Temperature:
* AverageTemperature: average temperature at that city in 2012
* AverageTemperatureUncertainty: level of uncertainty in the temperature value
* City: city name
* Country: country name

5.Airport_Data:
* type: airport type (small, medium, big,...)
* name: airport name
* elevation_ft: airport elevation reference to sea level
* continent: continent name where the airport exists
* iso_country: country name of the airport
* iso_region: region name
* municipality: municipality/city name of the airport
* gps_code: airport code on GPS system
* iata_code: airport code on IATA system
* local_code: airport loca; code
* coordinates: airport GPS coordinates

6.Demograhic:
* City: city name
* State: state name
* Median_Age: average age in the city
* Male_Population: male population in number
* Female_Population: female population in number
* Total_Population: total population in number
* Number_of_Veterans: number of Veterans in number
* Foreign_born: number of foreign born inside that city
* Average_Household_Size: avergae size of the household
* State_Code: state code
* Race: dominant race in that city (White, Hispanic or Latino, Asian, Black or African-American, or American Indian and Alaska Native)
* Count: number of people of that race in the city
