## Data guide to the UST-Global Hackathon on the 6th October 2020

### Overview
This guide provides an overview of all the data sources within the Covid-19 dataset used for the hackathon. To be used in conjuction with the associated API guides and notebooks containing examples of data innovation with the dataset.

### List of datasets within the Covid-19 dataset
All the data that collectively form our Covid-19 dataset are listed below, with sources and where and how we have enriched this data.

#### 1. Covid-19 incidence related data

#### Daily incidence rates (Local Authority level)
Reporting daily on the number of [newly recorded Covid-19 cases](https://coronavirus.data.gov.uk/cases) by Local Authority. This data also reports the Local Authority population size, enabling the incidence rate (typically per 10,000 or per 100,000 people) of Covid-19 to be derived.

This data can be accessed via [this API](https://coronavirus.data.gov.uk/cases) and a notebook with analysis examples is [here.](https://coronavirus.data.gov.uk/cases)

#### Daily incidence rates (Middle Layer Super Output Area level)
Reporting daily on the number of [newly recorded Covid-19 cases](https://coronavirus.data.gov.uk/cases) at the 
Middle Layer Super Output Area (MSOA). This data also reports the MSOA population size, enabling the incidence rate (typically per 10,000 or per 100,000 people) of Covid-19 to be derived. The data is updated daily, with a new column added each week, the `latest_7_days` column contains the latest data most of the time, if the column is null then the latest data is contained within the latest `wk_XX` column. 

This data can be retrieved via [this API](https://c19downloads.azureedge.net/downloads/msoa_data/MSOAs_latest.csv) and can be used in conjuction with any other dataset reporting at MSOA level, including the geojson that is available in section 4 below.

#### Daily NHS 111 and 999 Covid-19 Triage rates (Local Authority level)
NHS Digital publishes the number of NHS 111 and 999 triages for Covid-19 daily. Reporting by age and gender at a Clinical Commissioning Group (CCG) level, we have attributed these figures at a Local Authority level to make them comparable with other incidence and demography data and also the business and economic metrics we outline in section 3 below.


<details open>
<summary><strong>Section 1 API details</strong></summary>
<br>
  
| API Number | Method | Endpoint | Description |
|-----------|-------------|----------|----------|
|           |             |          |          |
|           |             |          |          |
|           |             |          |          |

</details>



#### 2. Population demography related data

#### UK population breakdown (Local Authority level)

The Office for National Statistics publishes a [mid-yearly report](https://www.ons.gov.uk/peoplepopulationandcommunity/populationandmigration/populationestimates/datasets/populationestimatesforukenglandandwalesscotlandandnorthernireland) estimating the population breakdown for every Local Authority in the UK, with several pages of supplementary information. We have collated the key attributes from this report into a table which includes an age breakdown, the median age and population density of each Local Authority.

This data can be accessed through [this API](https://coronavirus.data.gov.uk/cases).

#### England/Wales age distribution (Local Authority/LSOA level)

The ONS also separately publishes an [age breakdown at LSOA level for England and Wales](https://www.ons.gov.uk/peoplepopulationandcommunity/populationandmigration/populationestimates/datasets/lowersuperoutputareamidyearpopulationestimates) and their corresponding Local Authorities. Since most of our analysis has been conducted at LSOA level, we have created a separate table for this information. Unfortunately, neither Scotland nor Northern Ireland publish data at LSOA level.

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

#### Area type mapping

We have created several tables, accessible via API, to map between the different area types which occur within our other data. 

The [first API](https://coronavirus.data.gov.uk/cases) maps between LSOA and UTLA (Upper Tier Local Authority). These mappings are publicly available through [the ONS](https://geoportal.statistics.gov.uk/datasets/9f4c270148014f20bf24abff9a7aef62_0).

The second [API maps](https://coronavirus.data.gov.uk/cases) between LTLA (Lower Tier Local Authority) and UTLA (Upper Tier Local Authority). These mappings are also publicly available through [the ONS](https://geoportal.statistics.gov.uk/datasets/lower-tier-local-authority-to-upper-tier-local-authority-april-2019-lookup-in-england-and-wales).

The [third](https://coronavirus.data.gov.uk/cases) maps UK post codes to LTLA, LSOA (Lower layer Super Output Area) and MSOA (Middle layer Super Output Area). Most of the data in this section are reported at LSOA level, so this API is useful for linking to other area types. These mappings are again publicly available through [the ONS](https://geoportal.statistics.gov.uk/datasets/80628f9289574ba4b39a76ca7830b7e9_0).

Here below is a key of these area types in ascending order of size:

Postcode &rightarrow; LSOA &rightarrow; MSOA &rightarrow; LTLA &rightarrow; UTLA 

There may be slight differences in the data for the name of these area types, but each has a correspnding unique area code which can be used to merge/join tables.

<details open>
<summary><strong>Section 2 API details</strong></summary>
<br>
  
| API Number | Method | Endpoint | Description |
|-----------|-------------|----------|----------|
|           |             |          |          |
|           |             |          |          |
|           |             |          |          |

</details>

#### 3. Industry and economy related data

<details open>
<summary><strong>Section 3 API details</strong></summary>
<br>
  
| API Number | Method | Endpoint | Description |
|-----------|-------------|----------|----------|
|           |             |          |          |
|           |             |          |          |
|           |             |          |          |

</details>

#### 4. GIS data

<details open>
<summary><strong>Section 4 API details</strong></summary>
<br>
  
| API Number | Method | Endpoint | Description |
|-----------|-------------|----------|----------|
|           |             |          |          |
|           |             |          |          |
|           |             |          |          |

</details>


#### 5. Other data

<details open>
<summary><strong>Section 5 API details</strong></summary>
<br>
  
| API Number | Method | Endpoint | Description |
|-----------|-------------|----------|----------|
|           |             |          |          |
|           |             |          |          |
|           |             |          |          |

</details>


