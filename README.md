# r_google_trends_data_scale_up_script


Using the [gtrendsr](https://www.rdocumentation.org/packages/gtrendsR/versions/1.4.4) R library, the script ingests a list of pre-defined keyphrases and loops through this list to extract Google Trends data. Once all the data is collected, the script then cleans and exports it to CSV ready for visualisation and analysis

# Motivation

This script was created to be able to automatically extract Google Trends data at scale to allow for speedier analysis into new and emerging trends within specific markets. It was also created to overcome the following challenges with Google Trends front end when trying to analyse trend data:

1. Only being able to download data manually from the UI
2. Only being able to extract data for a maximum of 5 keyphrases at a time
3. Time spent applying various filters within the UI to segment the data
4. Data normalisation in Google Trends

# Installation
- Install R and Rstudio
- Install the following r packages using `install.packages()` within the Rstudio console. For example, `install.packages("gtrendsr")`

  - `library(gtrendsR)`
  - `library(tidyverse)`
  - `library(readr)`
  - `library(here)`
  - `library(lubridate)`
  - `library(data.table)`
  
# How to use

1. Conduct keyphrase research into your target market
2. Insert your keyphrases into `kwr_payload.csv` file in the 1_raw_data folder
3. 
