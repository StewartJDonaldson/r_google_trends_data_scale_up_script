# r google trends data scale up script

Using the [gtrendsr](https://www.rdocumentation.org/packages/gtrendsR/versions/1.4.4) R library, the script loops through a list of keyphrases and calls the Google Trends API to extract the search trend data for each keyphrase. Once all the data is collected, the script then cleans and exports it to CSV ready for visualisation and analysis

# Motivation
This script was created to be able to automatically extract Google Trends data at scale to allow for speedier analysis into new and emerging trends within specific markets. It was also created to overcome the following challenges with the Google Trends tool:

1. Only being able to download data manually from the UI
2. Only being able to extract data for a maximum of 5 keyphrases at a time
3. Time spent applying various filters within the UI to segment the data
4. Data normalisation in Google Trends


# Installation
- Install `R` and `Rstudio`

- Install the following r packages using `install.packages()` in the Rstudio console. For example, `install.packages("gtrendsr")`:

	- `library(gtrendsR)`
	- `library(tidyverse)`
	- `library(readr)`
	- `library(here)`
	- `library(lubridate)`
	- `library(data.table)`


# How to use
1. Conduct keyphrase research into your target market

2. Insert your keyphrases into the `kwr_payload.csv` file in the `1_raw_data folder`

3. Use the arguments within the `gtrends()` function to define the specific **location**, **timespan**, **Google property**, **search category**, and **language** you would like the data to be segmented by.

	- By default the script is set to retrieve data from the UK for the past five years:

			gtrends(keyword = kw_payload[[i, 1]], geo = "GB", time = "today+5-y", hl = "en-GB")

	- The full list of arguments can be found [here](https://www.rdocumentation.org/packages/gtrendsR/versions/1.4.4/topics/gtrends).

4. Run Script

5. The script extracts the **"interest over time"** and **"related query data"**, cleans it and then exports it to three CSVs that are saved in the `3_cleaned_data folder`