# NTSB Aviation Accident Analysis Data Story
 
*By Jason Guan*
 
## Overview
This project analyzes over four decades of NTSB aviation accident data to identify trends in accident frequency, injury severity, weather conditions, geographic distribution, and aircraft manufacturer performance across the United States.
 
The goal is to analyze:
- Long-term aviation accident trends (1982–2022)
- Seasonal injury patterns throughout the year
- The impact of weather conditions on accident severity
- Geographic accident distribution within the United States
- Fatal injury trends across Boeing and Cessna aircraft models
  
**Technical Tools Used:**
- Tableau Public
- Microsoft Excel
- Data Visualization
- Exploratory Data Analysis (EDA)
- Data Storytelling
  
**Data Pipeline**
 
NTSB Aviation Dataset -> Excel Cleaning & Transformation -> Processed Dataset -> Tableau Dashboards -> Interactive Tableau Story
 
## The Data
 
The dataset was obtained from the National Transportation Safety Board (NTSB) and contains approximately 88,000 aviation accident records spanning 1982–2022. Each record describes an aviation accident, including aircraft information, location, weather conditions, and injury outcomes.
 
Key Fields:
- `event_date`, `city`, `state`
- `aircraft_manufacturer`, `aircraft_model`
- `weather_condition` (VMC / IMC)
- `injury_severity`
- `fatal_injuries`, `serious_injuries`, `minor_injuries`, `uninjured_passengers`
  
## Data Processing
 
Key Transformations:
- Split the original `location` column into separate `city` and `state` fields for geographic analysis
- Created a `total_injuries` field by combining multiple injury-related columns into a single metric
- Extracted `month` and `year` from `event_date` to support trend and seasonal analysis
- Removed unnecessary columns not relevant to the research questions
- Standardized fields to improve dashboard performance and filtering
  
## Tableau Data Story
 
[View Live Data Story Here](https://public.tableau.com/views/NTSBAviationAccidentAnalysisWeatherGeographyManufacturerTrendsDataStory/NTSBAviationAccidentAnalysis?:language=en-US&:sid=&:display_count=n&:origin=viz_share_link)
 
This Tableau Story consists of 5 connected dashboards that guide users from high-level trends to more detailed insights:
 
- **Aviation Accident Trends (1982–2022)** — line chart showing annual accident frequency, highlighting long-term changes over four decades
- **Monthly Injury Analysis** — compares average fatal injuries, total injuries, and uninjured passengers to surface seasonal patterns
- **Weather Impact Analysis** — compares accidents under Visual Meteorological Conditions (Clear Visibility) vs. Instrument Meteorological Conditions (Poor Visibility) to examine how weather influences severity
- **Geographic Analysis** — interactive map focused on the United States region, displaying accident distribution by location
- **Aircraft Manufacturer Analysis** — bar chart comparing Boeing and Cessna aircraft models by fatal injury totals and historical accident distribution

## Key Takeaways
 
**Long-Term Trends**
- Aviation accident frequency generally declined between 1982 and 2022
- The downward trend may reflect improvements in aviation technology, pilot training, aircraft reliability, and safety regulations
**Weather Conditions**
- Accidents occurring under Instrument Meteorological Conditions (Poor Visibility) were associated with more severe outcomes than those under Visual Meteorological Conditions (Clear Visibility)
- Poor visibility appears to play an important role in accident severity
**Seasonal Patterns**
- Injury outcomes fluctuate throughout the year
- Monthly comparisons reveal differences in average fatal injuries, total injuries, and uninjured passengers
**Geographic Distribution**
- Aviation accidents are distributed across multiple locations within the United States region
- Geographic visualization helps identify areas with higher historical accident activity
**Aircraft Manufacturers**
- Several Boeing and Cessna aircraft models recorded higher cumulative fatal injury totals than others in the dataset
- These findings reflect historical accident records and should not be interpreted as indicators that a particular aircraft model is inherently less safe — flight hours, fleet size, aircraft age, maintenance history, pilot experience, and utilization were not available in the dataset
  
## Recommendations
 
Based on the trend, weather, seasonal, and manufacturer analysis, several directions could extend this work:
 
- **Automate the data cleaning step**: replacing manual Excel transformations with a Python or SQL pipeline would make it easier to refresh the dataset as NTSB releases updates.
- **Add richer filtering**: interactive filters for aircraft type, state, and injury severity would let users drill into the specific segments that matter to them.
- **Integrate FAA datasets**: combining NTSB records with FAA data (e.g. flight hours, fleet size) would help move from descriptive trends toward more defensible comparisons across manufacturers.
- **Explore predictive modeling**: a model of accident severity based on weather, aircraft type, and seasonal factors could complement the descriptive dashboards.
- **Move to Tableau Cloud/Server**: this would support scheduled data refreshes rather than static, one-time publishing.
  
## Project Limitations
 
This analysis is based on publicly available NTSB aviation accident records and identifies associations rather than causal relationships. Several variables that influence aviation safety were unavailable in the dataset, including flight hours, fleet size, aircraft utilization, aircraft age, maintenance history, pilot experience, and airline operating procedures. Conclusions should be read as descriptive trends rather than evidence of aircraft reliability or safety performance.
