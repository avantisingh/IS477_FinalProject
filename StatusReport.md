# IS 477 Course Project Milestone 3

## Task Project Updates

Crime Dataset Cleaning and Assessment (Jasmitha)

I was responsible for cleaning and assessing the crime dataset for our project. During the dataset cleaning stage, I filtered the crime data to include the years 2016–2023, converted the Date column into a datetime format, and extracted the Year variable for temporal analysis. I also selected relevant variables, including Date, Primary Type, Community Area, Year, and Arrest, and examined missing values, duplicate records, and the distribution of reported crimes across years and crime categories.

For the dataset assessment stage, I explored the distribution of reported crimes across Chicago's Community Areas and aggregated the data to calculate total reported crimes by Community Area. I also created an additional aggregation of crime counts by Community Area and Year to support potential comparisons across neighborhoods and time. Community Area 0, representing unassigned geographic information, was excluded from neighborhood-level analysis.

## Updated Project Timeline
Completed:
- Find datasets centered around crime and energy performance - Everyone 
- Based on the dataset, determine research question - Everyone 
- Determine all the variables we want to analyze and the scope, as well as the gaps of the project - Everyone 
- Submit the outline - 10/12
Dataset exploration
- Prepare the datasets for assessment (ie cleaning, same type) - 11/1
  - Crime dataset cleaning - Jasmitha
  - Socioeconomic dataset cleaning - Sharanya
  - Energy dataset cleaning - Avanti
Pending:
Data assessment - 11/16
- Assess the most important variable of the dataset and condense the datasets down to the most important variables 
  - Crime dataset assessment- Jasmitha
  - Socioeconomic dataset assessment- Sharanya
  - Energy dataset assessment- Avanti
  - Attach locations to each of the datasets - Anjana
- Proofread others' assessments and cleaning 
- Determine the feasibility of the integration between the datasets
- Convert datasets from one type to another if needed - changes based on which dataset needs to be converted 
Integrated datasets - 11/24
- Once the datasets are integrated and converted into one dataset, we can start analysis 
- Proofread that all the variables are the correct types - Anjana/Jasmitha 
- Additional cleaning if needed/ checking if the dataset could be condensed 
   - Checking whether to keep the datasets separate or together - Avanti/ Sharanya 
Analysis - 12/1
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

## Changes to our Project Plan
Our project plan has very minimal changes. The structure and questions are essentially the same, but our analysis and roles have changed somewhat. Avanti, Jasmitha, and Sharanya will clean and analyze their own datasets. Anjana will take each cleaned CSV and assign a location on a map to understand the geographic patterns across the three datasets. This is the new plan compared to where Anjana would be analyzing an individual geographic pattern CSV. This will also help connect the dots between each of the different datasets. 

## Challenges and Problems Faced 
One major issue is that the ACS gives estimates by census tract, but both the energy and crime statistics are reported by Chicago’s 77 community areas. The 2023 ACS poverty table for the Cook County tracts has been downloaded and cleaned, but this dataset has not yet been linked to the other data. Work is in coordination with Anjana regarding generating a crosswalk to align the tracts with the community areas; unmatched records will be searched for afterward.

Moreover, the datasets cover different timelines, in that, the energy and crime data is annual, while the 2023 ACS statistics cover the period of 2019–2023. The measures from the ACS are intended to provide socioeconomic context for the comparison in 2023 – and this limitation is justified.

Broader ACS national totals were first accidentally downloaded. To rectify this problem, we used only the census tracts from Cook County. In the prepared and processed poverty data table, four of the census tracts had zero values for poverty status, resulting in undefined values for poverty rates. Since we had missing poverty rates rather than zero values, we kept them as missing instead of assigning a zero value. 

Now, one final scope issue remains in regard to the inclusion of household income in the project. Currently, the ACS table in use pertains mainly to poverty, thus the scope of the project needs to be defined either by adding the income table or by narrowing it down to solely poverty consideration.

One of the challenges we faced was that the crime dataset was extremely large. Some functions, such as loading the dataframe, were taking too long to run. In order to shorten our dataset, we used a specific timeframe of 2016 to 2023. Yet, the data is still very large which could make it challenging when modelling in the future steps so then we could be using a sampling method.

Another challenge encountered during cleaning the crime dataset was the presence of missing Community Area values and records with unassigned geographic information. Since our project requires comparing crime data with neighborhood-level energy performance and socioeconomic datasets, geographic consistency is important. We examined the missing values and checked that when Community Area is missing, the longitude and latitude are still available except for 4 rows, which we will drop in the future. For the rest of the missing Community Areas, we will aggregate the data using the longitude and latitude variables. 

Lastly, another issue we encountered with the crime dataset was that Community Area 0 was associated with 1,515 reported crimes, despite Chicago having no officially designated Community Area 0. These records represent crimes with unknown or unassigned geographic locations. Since our research focuses on comparing crime rates across Chicago neighborhoods, these records cannot be reliably associated with a specific community area. Therefore, we excluded all rows with Community Area 0 from our neighborhood-level analysis to ensure geographic consistency and meaningful comparisons across community areas.

## Member Contribution Summary
Sharanya - Downloaded the 2023 ACS five-year B17001 poverty data for Cook County and cleaned it. Created a cleaning notebook, retained the poverty estimates and margins of error, calculated poverty rates by tract, and checked for duplicate tract IDs and invalid rates or counts. 4 tracts had a poverty-status population of 0, so their rates are not applicable yet. Mapping the tracts is waiting for the team's crosswalk for the community areas. The ACS is for the period of 2019-2023, while other data for the project are only for 2023.

Jasmitha -  Cleaned and assessed the Chicago crime dataset for 2016–2023. Created a cleaning notebook, converted dates to datetime format, extracted yearly information, retained relevant crime and geographic variables, and examined missing values and crime distributions. Aggregated crime counts by Community Area and year for future analysis. Excluded 1,515 records assigned to Community Area 0 due to unknown geographic locations.

Anjana - Coordinated updated time line and project plan. Started to attach locations to the cleaned csv. Making sure that the location exists by checking that either the zip-code, latitude and longitude are valid, or city. 
