# IS 477 Course Project 

## 1. Overview

Our overall goal of the project is to investigate the relationships between building energy performance, neighborhood socioeconomic conditions, and reported crime rates across Chicago. We are interested in this topic, given the rising crime rates in Chicago, to understand if crime rates are associated with differences in building energy use intensity, greenhouse gas emissions, household income, and poverty. We also want to observe patterns within energy usage intensity, greenhouse gas emission, household income, and poverty.

To achieve our goal, we will collect publicly available datasets like the City of Chicago’s Energy Benchmarking, crime datasets and socioeconomic estimates from the U.S. Census Bureau’s American Community Survey (ACS). We will assess data quality by identifying missing values, duplicates, inconsistent formats, and differences in geographic and temporal coverage. Using Python and pandas, we will clean and standardize all relevant variables. Then we will integrate the energy and crime datasets using Chicago’s 77 community areas variable as the common geographic unit. We will investigate geographic boundary files and appropriate aggregation methods to incorporate census tract estimates into our analysis.

After dataset integration, we will conduct exploratory data analysis to identify patterns and associations among our three broad variables: building energy performance, socioeconomic characteristics, and crime rates using several data analysis methods, such as groupby and visualizations. We will document our whole workflow and evaluate limitations related to our datasets and our analysis to produce a well-documented, reproducible analysis that demonstrates how data management, curation, and integration can support meaningful exploration of urban conditions.

## 2. Team

## 3. Research Questions

Our project will investigate the relationship between building energy performance, neighborhood socioeconomic conditions, and reported crime rates across Chicago. Our primary research question is: How is building energy performance associated with neighborhood socioeconomic conditions and reported crime rates across Chicago?

To address this question, we will examine how building energy performance varies across neighborhoods and building types, focusing on measures such as energy use intensity and greenhouse gas emissions. We will investigate whether neighborhood socioeconomic characteristics, including household income and poverty, are associated with differences in building energy performance. Additionally, we will examine how energy performance and socioeconomic conditions vary across neighborhoods with different reported crime rates.

We will use exploratory data analysis to identify geographic patterns and associations among these variables. By combining building energy benchmarking data with socioeconomic estimates and crime records, we aim to develop a better understanding of how building performance and neighborhood conditions vary across Chicago. 

## 4. Datasets

### 4.1 Chicago Energy Benchmarking

**Source:** [Chicago Data Portal - Chicago Energy Benchmarking](https://data.cityofchicago.org/Environment-Sustainable-Development/Chicago-Energy-Benchmarking/xq83-jr8c/about_data)

The Chicago Energy Benchmarking dataset provides annual information about the energy performance and characteristics of buildings covered by Chicago’s Energy Benchmarking Ordinance. Relevant variables include `Data Year`, `ID`, `Primary Property Type`, `Gross Floor Area - Buildings (sq ft)`, `Site EUI (kBtu/sq ft)`, `Total GHG Emissions (Metric Tons CO2e)`, `GHG Intensity (kg CO2e/sq ft)`, and `Community Area`. These variables will allow us to compare building energy performance across property types, reporting years, and Chicago community areas.

We will assess missing values, duplicate records, and inconsistencies across reporting years. We will also examine the availability of energy performance measurements and distinguish missing or unavailable values from meaningful zero values. The `ID` and `Data Year` fields will help us identify individual properties across annual records, while `Community Area` will serve as the geographic identifier for neighborhood-level analysis.

### 4.2 American Community Survey

**Source:** [U.S. Census Bureau - American Community Survey](https://www.census.gov/data/developers/data-sets/acs-5year.html)

The American Community Survey (ACS) provides estimates of demographic, socioeconomic, and housing characteristics for communities across the United States. We will use ACS five-year estimates to examine characteristics such as median household income, poverty rates, population, and housing conditions in Chicago neighborhoods. These variables will provide socioeconomic context for analyzing differences in building energy performance and reported crime rates across community areas.

Because ACS estimates are reported for census tracts rather than Chicago community areas, we will use geographic boundary data to match census tracts to community areas and aggregate the selected variables. We will document the aggregation method used for each variable and account for limitations arising from differences in geographic boundaries and the multiyear period covered by ACS estimates.

### 4.3 Chicago Crime Data

**Source:** [Chicago Crime Data]([https://data.cityofchicago.org/Public-Safety/Chicago-Crime-Data/gsj2-yds5](https://data.cityofchicago.org/Public-Safety/Crimes-by-date/ata4-bx2a/about_data))

The Chicago crime incident dataset provides information about reported crime incidents, including incident dates, crime classifications, and geographic information. Relevant variables include `Date`, `Primary Type`, `Description`, `Year`, and `Community Area`. These fields will allow us to examine how reported crime patterns vary across neighborhoods and compare those patterns with building energy performance and socioeconomic characteristics.

We will clean and standardize incident dates and crime classifications, examine duplicate records and missing geographic information, and select a reporting period compatible with the other datasets. We will aggregate incidents by community area and year where appropriate. We will also calculate population-adjusted crime rates using compatible population estimates where appropriate, rather than relying exclusively on raw incident counts. The analysis will focus on reported crime patterns and will account for differences in neighborhood population when comparing crime rates across community areas.

### 4.4 Data Integration

We will integrate the three primary datasets using Chicago's 77 community areas as the common geographic unit. The energy benchmarking dataset and crime incident dataset both contain a `Community Area` field, allowing us to aggregate building energy performance and reported crime incidents to the community-area level. We will align reporting years where possible to support meaningful comparisons over time.

To integrate socioeconomic information, we will use ACS five-year estimates and appropriate geographic boundary files to aggregate census tract data to Chicago community areas. We will select compatible variables and document the aggregation procedure, including how estimates are combined and how differences in geographic boundaries and reporting periods may affect the results.

We will assess the quality of the integrated dataset by examining missing values, duplicate observations, unmatched geographic records, and differences in temporal coverage. We will document all cleaning and integration procedures and evaluate how data limitations affect the analysis. The resulting dataset will support exploratory analysis of associations among building energy performance, neighborhood socioeconomic conditions, and reported crime rates across Chicago's community areas.

## 5. Timeline

## 6. Constraints

## 7. Gaps

