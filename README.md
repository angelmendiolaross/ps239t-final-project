# ps239t-final-project

## Short Description

This analysis cleans and brings together data from five different sources to run an analysis of police spending in California cities from 2000 to 2018. It involves merging two different policing files for a longer time-series, using the Census API, linearly interpolating Census data in order to run my panel models, and eventually running a fixed-effects regression model using the plm package.

## Dependencies

1. R, Version 1.2.5033

I rely on a range of packages for cleaning, visualizing, and analyzing my data. Each script begins with the required packages.

## Files

#### /

1. Narrative.Rmd: Provides a 5 page narrative of the project, main challenges, solutions, and results.
2. Narrative.pdf: A knitted pdf of 00_Narrative.Rmd. 
3. slides.pdf: Slides from class presentation on 5/6/2020.

#### analysis/

1. 01_get_renter_seg_census: Collects data from the Census API and exports raw data tenure_by_ data to the Data/Raw folder
2. 01_prepping_pre2003_policing_data: Reads, cleans, and merges 1992-2017 policing data with the 2018 policing data and saves out the policing_long file in the Data directory
3. 02_computing_segregation_measures: Brings in data from the Census API and a Census crosswalk to compute renter segregation measures and saves output to Plots and Data
4. 02_joining_cleaning_full_police_dataset: Merges policing data with other city financial data, adjusts policing data for inflation, leads the policing data, analyzes policing data, and saves out to Plots and Data
5. 03_merging_crime_zillow_vote_data: Merges crime and Zillow housing data with voter turnout data from presidential elections and saves out to Plots and Data
6. 04_interpolating_census_data: Merges policing and city financial data with crime, zillow, and voter data, and interpolates Census data between 2000 and 2009 before saving out to Plots and Data
7. 05_analyzing_data: Conducts the fixed effects panel analysis on the combined dataset and saves out to Plots, Results, and Data 

#### data/

1. all_data: merged data with all years available
2. census_data: demographic data generated from Census API
3. city_fin_sensus_crosswalk: a crosswalk to match city financial data with Census data
4. city_fin_data: city financial data from 2003 to 2018
5. city_service_responsibility: the responsibility of policing for each CA city
6. crime_data: crime data from the FBI's Uniform Crime Reporting Statistics
7. d_panel: merged data for years 2000 to 2018 with panel structure
8. data_no_census: merged data without the census data
9. finance_crime: city financial data and crime data joined
10. policing_complete_lead: the cleaned policing dataset with policing leaded t+1 and t+2
11. policing_complete: same as above minus the leaded policing variables
12. policing_data_9217: policing data from 1997 to 2017
13. pop_density: population density data from Social Explorer
14. raw: folder with raw data that is then cleaned and saved out to the Data folder
15. renter_seg_city: renter segregation measures at the city-level
16. renter_seg: renter segregation measures at the tract-level
17. vote_with_geo: voter turnout data with geographical information
18. zillow: housing price data from zillow

#### results/

1. d_panel_csv: final combined dataset
2. fixed_effects_regression.png: fixed effects regression results
3. infl_adj_police_spending.pdf: natural logarithm of inflation-adjusted police spending over time
4. infl_adj_police_spending_boxplot: box plot of the natural logarithm of inflation-adjusted police spending over time

#### plots/

1. infl_adj_police_spending_boxplot: box plot of the natural logarithm of inflation-adjusted police spending over time
2. infl_adj_police_spending: natural logarithm of inflation-adjusted police spending over time
3. pblkrenters: change in the percent of Black renters over time
4. police_spending: nominal police spending over time
5. prop_crime: property crime rate over time
6. renter_segregation_city: renter/homeowner dissimilarity index based on city-level data
7. renter_segregation: renter/homeowner dissimilarity index based on aggregated tract-level data
8. violent_crime: violent crime rate over time
9. ZHVI: Zillow housing value index over time

#### xwalks/

1. census_xwalk_small: only includes the columns of interest for my analysis
2. census_xwalk: full Census LODES block crosswalk for the 2010 Census

## More Information

For any questions, email a.ross@berkeley.edu.
