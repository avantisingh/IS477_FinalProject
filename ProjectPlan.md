# IS 477 Course Project 

## 1. Overview

Our overall goal of the project is to investigate the relationships between building energy performance, neighborhood socioeconomic conditions, and reported crime rates across Chicago. We are interested in this topic, given the rising crime rates in Chicago, to understand if crime rates are associated with differences in building energy use intensity, greenhouse gas emissions, household income, and poverty. We also want to observe patterns within energy usage intensity, greenhouse gas emission, household income, and poverty.

To achieve our goal, we will collect publicly available datasets like the City of Chicago’s Energy Benchmarking, crime datasets and socioeconomic estimates from the U.S. Census Bureau’s American Community Survey (ACS). We will assess data quality by identifying missing values, duplicates, inconsistent formats, and differences in geographic and temporal coverage. Using Python and pandas, we will clean and standardize all relevant variables. Then we will integrate the energy and crime datasets using Chicago’s 77 community areas variable as the common geographic unit. We will investigate geographic boundary files and appropriate aggregation methods to incorporate census tract estimates into our analysis.

After dataset integration, we will conduct exploratory data analysis to identify patterns and associations among our three broad variables: building energy performance, socioeconomic characteristics, and crime rates using several data analysis methods, such as groupby and visualizations. We will document our whole workflow and evaluate limitations related to our datasets and our analysis to produce a well-documented, reproducible analysis that demonstrates how data management, curation, and integration can support meaningful exploration of urban conditions.

## 2. Team
We decided to split up our work based on datasets rather than a phase of the project. This is so everyone can work on each phase and there is no gaps in understanding between the datasets and the reasoning as to why we made some choices. We also will changed roles in the future so everyone can work with different datasets and also gives us a chance to proof-read everything so there are not any major information being missed or skimmed over. Our starting roles are going to be: 
- Crime dataset analyst: Jasmitha
- Geographic pattern analyst: Anjana 
- Energy Performance analyst: Avanti
- Socioeconomic analyst:  Sharanya 


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

**Source:** [Chicago Crime Data](https://data.cityofchicago.org/Public-Safety/Crimes-by-date/ata4-bx2a/about_data)

The Chicago crime incident dataset provides information about reported crime incidents, including incident dates, crime classifications, and geographic information. Relevant variables include `Date`, `Primary Type`, `Description`, `Year`, and `Community Area`. These fields will allow us to examine how reported crime patterns vary across neighborhoods and compare those patterns with building energy performance and socioeconomic characteristics.

We will clean and standardize incident dates and crime classifications, examine duplicate records and missing geographic information, and select a reporting period compatible with the other datasets. We will aggregate incidents by community area and year where appropriate. We will also calculate population-adjusted crime rates using compatible population estimates where appropriate, rather than relying exclusively on raw incident counts. The analysis will focus on reported crime patterns and will account for differences in neighborhood population when comparing crime rates across community areas.

### 4.4 Data Integration

We will integrate the three primary datasets using Chicago's 77 community areas as the common geographic unit. The energy benchmarking dataset and crime incident dataset both contain a `Community Area` field, allowing us to aggregate building energy performance and reported crime incidents to the community-area level. We will align reporting years where possible to support meaningful comparisons over time.

To integrate socioeconomic information, we will use ACS five-year estimates and appropriate geographic boundary files to aggregate census tract data to Chicago community areas. We will select compatible variables and document the aggregation procedure, including how estimates are combined and how differences in geographic boundaries and reporting periods may affect the results.

We will assess the quality of the integrated dataset by examining missing values, duplicate observations, unmatched geographic records, and differences in temporal coverage. We will document all cleaning and integration procedures and evaluate how data limitations affect the analysis. The resulting dataset will support exploratory analysis of associations among building energy performance, neighborhood socioeconomic conditions, and reported crime rates across Chicago's community areas.

## 5. Timeline
Project ideation
- Find datasets centered around crime and energy performance - Everyone 
- Based on the dataset, determine research question - Everyone 
- Determine all the variables we want to analyze and the scope, as well as the gaps of the project - Everyone 
- Submit the outline - 10/12
Dataset exploration
- Prepare the datasets for assessment (ie cleaning, same type) - 10/20
  - Crime dataset cleaning - Jasmitha
  - Socioeconomic dataset cleaning - Sharanya
  - Energy dataset cleaning - Avanti
  - Geographic pattern dataset cleaning - Anjana
Data assessment - 10/29
- Assess the most important variable of the dataset and condense the datasets down to the most important variables 
  - Crime dataset assessment- Jasmitha
  - Socioeconomic dataset assessment- Sharanya
  - Energy dataset assessment- Avanti
  - Geographic pattern dataset assessment- Anjana
- Proofread others' assessments and cleaning 
- Determine the feasibility of the integration between the datasets
- Convert datasets from one type to another if needed - changes based on which dataset needs to be converted 
Integrated datasets - 11/7
- Once the datasets are integrated and converted into one dataset, we can start analysis 
- Proofread that all the variables are the correct types - Anjana/Jasmitha 
- Additional cleaning if needed/ checking if the dataset could be condensed 
   - Checking whether to keep the datasets separate or together - Avanti/ Sharanya 
Analysis - 11/20
- Create plots 
  - Plot between crime and socioeconomic standing - Jasmitha
  - Plot between socioeconomic and energy usage - Sharanya
  - Plot between geographic pattern and crime - Anjana
  - Plot between all 3 of them, keeping socioeconomic as the x-axis- Avanti
- Correlation table - Anjana 
- K - values, determines the strength of the relationship between data - Jasmitha 
- Box plot and quartile graph and info - Sharanya 
- Detailed paragraph about each section that everyone worked on and backing it up with quantitative data - everyone 
Final deliverable - 12/07
- Detailed review of the entire project 
  - Introduction - Jasmitha 
  - Cleaning and why - Sharanya 
  - Integration and conversions - Avanti 
  - Types of analyses and why - Anjana 
  - Detailed paragraphs of our findings : Everyone 
- Conclusion - Whoever wants to 


## 6. Constraints

There are a few constraints that our project may face related to data completeness, geographic alignment, differences in reporting periods, and much more. 

Data completeness and quality: The Chicago energy benchmarking dataset does not cover every building in Chicago, as it focuses on buildings subject to the city’s benchmarking requirements. Similarly, the crime dataset only has reported crimes, but reported crimes do not necessarily present all criminal activity in a neighborhood. This missing information can skew our results, leading to biased results. It also affects how representative our findings are. To address this concern, we should avoid generalizing our findings beyond the available data. 

Geographic alignment: The energy benchmarking and crime datasets include community area identifiers, while ACS data is organized by census tract. Aggregating census tract estimates to community areas may introduce uncertainty because geographic boundaries do not always align perfectly. 

Temporal alignment: The energy and crime datasets cover different time periods, so we will be using the overlapping years in order to make direct comparisons. Additionally, ACS data combines five years of survey data to produce more reliable estimates, particularly for smaller geographic areas. The trade-off is that it doesn't provide a clean snapshot of a single year.

Correlation does not equal causation: Our exploratory data analysis may reveal an association between building energy performance, socioeconomic conditions, and reported crime rates. This does not necessarily equal causation. There are many other factors that may influence observed patterns, like population density, demographics, and much more, so we will interpret our findings as associations rather than evidence that one variable directly causes changes in another. 

Ethical considerations: Although the datasets are publicly available, we will avoid interpreting crime statistics as definitive measures of neighborhood safety, and we will acknowledge potential reporting biases and avoid making unsupported generalizations about communities. Additionally, we will consider the margins of error associated with ACS estimates when interpreting socioeconomic patterns and comparing community areas.

## 7. Gaps
- Scope and feasibility
- Interpretation of findings
- Renovation and energy performance
- Dataset integration

Several aspects of this project will require further investigation as we begin data collection and analysis. First, we need to determine which reporting years provide the most appropriate basis for comparison across the Chicago Energy Benchmarking, American Community Survey, and the Chicago Crime Data datasets.

We also need to select the ACS variables that best represent neighborhood socioeconomic conditions, particularly income, poverty, and housing characteristics. In addition, we must determine an appropriate method for aggregating census tract estimates to Chicago’s community areas so that socioeconomic data can be compared with the other datasets.

We also need to assess whether each community area has enough usable energy benchmarking records to support meaningful comparisons. Preliminary data assessment will help determine whether missing values or unmatched geographic records limit the project’s feasibility. We will also consider how differences in building types and crime reporting may affect interpretation, so that observed associations are not presented as causal relationships. 

Finally, we need to determine how to compare building energy performance and reported crime across community areas. This includes deciding how to summarize energy performance across multiple buildings in each area and how to account for differences in population size when comparing crime rates. 

