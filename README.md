## Data guide to the UST-Global Hackathon on the 6th October 2020

### Overview
This guide provides an overview of all the data sources within the Covid-19 dataset used for the hackathon. To be used in conjuction with the associated API guides and notebooks containing examples of data innovation with the dataset.

### List of datasets within the Covid-19 dataset
All the data that collectively form our Covid-19 dataset are listed below, with sources and where and how we have enriched this data.

#### 1. Covid-19 incidence related data

#### Daily incidence rates (Local Authority level)
Reporting daily on the number of [newly recorded Covid-19 cases](https://coronavirus.data.gov.uk/cases) by Local Authority. This data also reports the Local Authority population size, enabling the incidence rate (typically per 10,000 or per 100,000 people) of Covid-19 to be derived.

This data can be accessed via [this API](https://coronavirus.data.gov.uk/cases) and a notebook with analysis examples is [here.](https://coronavirus.data.gov.uk/cases)

#### Daily NHS 111 and 999 Covid-19 Triage rates (Local Authority level)
NHS Digital publishes the number of NHS 111 and 999 triages for Covid-19 daily. Reporting by age and gender at a Clinical Commissioning Group (CCG) level, we have attributed these figures at a Local Authority level to make them comparable with other incidence and demography data and also the business and economic metrics we outline in section 3 below.


#### 2. Population demography related data

#### England/Wales age distribution (Local Authority/LSOA level)

This data is sourced directly from the [Office for National Statistics](https://www.ons.gov.uk/peoplepopulationandcommunity/populationandmigration/populationestimates/datasets/lowersuperoutputareamidyearpopulationestimates) who provide mid-year estimates of the usual resident population for Lower layer Super Output Areas (LSOAs) in England and Wales. The data also contains information at Local Authority level.

The table contains a full breakdown of ages, with columns representing each age up to 90 years old. Residents of 90 years or older are grouped together. 

This data can be accessed via [this API](https://coronavirus.data.gov.uk/cases) and a notebook using this data can be found [here](https://coronavirus.data.gov.uk/cases).

#### England/Wales ethnicity distribution (LSOA level)

The source for this data is the most recent publicly available [UK census estimate (March 2011)](https://www.nomisweb.co.uk/census/2011/lc2101ew). The data has been directly transcribed from the public records available by selecting the type of area as super output area - lower. 

The data contains a breakdown of the total population of each LSOA by both race and ethnic group. All LSOAs in England and Wales are included. 

Data for other area types can be accessed through the nomisweb site by altering the dropdown filters.

This data can be accessed via [this API](https://coronavirus.data.gov.uk/cases) and a notebook using this data can be found [here](https://coronavirus.data.gov.uk/cases). 

#### Index of Multiple Deprivation (LSOA level)

The Index of Multiple Deprivation (IMD) is a measure of relative deprivation between different area groups. 

The IMD data for England at LSOA level is publicly made available through the [Ministry of Housing, Communities & Local Government](https://opendatacommunities.org/resource?uri=http%3A%2F%2Fopendatacommunities.org%2Fdata%2Fsocietal-wellbeing%2Fimd2019%2Findices), the most recent data having been collected in 2019.

Along with an IMD score and ranks for each LSOA in England, the data includes columns representing the variables used in calculating the IMD score. These variables include health indicators, employment percentages, crime levels and average income (amongst others). 

This data can be accessed via [this API](https://coronavirus.data.gov.uk/cases) and a notebook using this data can be found [here](https://coronavirus.data.gov.uk/cases). 


#### 3. Industry and economy related data

#### 4. GIS data

#### 5. Other data

