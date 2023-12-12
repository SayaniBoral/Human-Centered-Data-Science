
__INTRODUCTION__
In this study, we will be understanding the impact of wildfire smoke on the respiratory health of the population residing in Grand Island in Hall County, Nebraska. According to this NCBI article2, wildfires elevate the risk of smoke exposure for a significant portion of the US population. However, certain groups, particularly outdoor workers, firefighters and socially disadvantaged communities with limited adaptive capacity, face a disproportionately higher risk of exposure. The health impacts associated with exposure to wildfire smoke are highlighted, affecting both children and adults. These impacts include the exacerbation of pre-existing respiratory conditions such as asthma and chronic obstructive pulmonary disease (COPD), adverse effects on birth outcomes, and an increased incidence of cardiovascular and respiratory diseases. We want to focus on studying the correlation between these key metrics: AQI, Smoke impact Estimate, ER visits, Hospitalization and mortality attributed to COPD and Asthma. We want to also understand if a certain population demographic like ethnicity or gender is more vulnerable or not.

Increasingly, summers in the mid & western United States are marked by wildfires, with smoke spreading across numerous states in the region. Various factors have been suggested as potential causes, including climate change, US Forestry policy, and heightened awareness. Regardless of the underlying reasons, the repercussions of wildland fires are extensive. A growing body of research underscores the adverse effects of smoke on health, tourism, property, and various societal aspects.


__MOTIVATION & GOAL__
There are many studies(see References) on the impact of wildfire smoke on public health and I have been most motivated by a research study 3 done by Darling et al : The Burden of Wildfire Smoke on Respiratory Health in California at the Zip Code Level: Uncovering the Disproportionate Impacts of Differential Fine Particle Composition. This study is aimed at quantifying the health burden of respiratory hospitalizations related to particulate matter (PM) exposure in California from 2006 to 2019, considering the differential impact of wildfire smoke. The findings suggest that previous estimates may have underestimated respiratory hospitalizations associated with PM exposure by approximately 13%, with higher underestimations in northern California and vulnerable areas. The study highlights the importance of considering the specific health impact of wildfire smoke in air pollution guidelines to better protect at-risk communities.
I wanted to adopt the methodology and data sources discussed in this paper and apply the analyses to Grand Island, Hall County , Nebraska. Some of the data I found are at county level instead of city level , so we will be extending some of the analyses to Hall County. 
The focus of this study will be based on the following:
Hypothesis - Find out if there is a strong correlation between wildfire smoke (measured by AQI, Smoke Estimate) and incidence of respiratory diseases like COPD, Asthma (measured by ER Visits, Hospitalization, Mortality)
Analysis - What is the demographics  of Grand Island’s population that is most likely to be affected by COPD and asthma caused due to wildfire smoke?

The ultimate objective is to provide valuable insights to policymakers, city managers, city councils, or other civic institutions, enabling them to formulate well-informed plans to address or decide whether to develop strategies for mitigating future wildfire impacts.

__REPOSITORY STRUCTURE__

All code associated with the repository is stored in the Notebook folder.
- 1_wild_fire_estimation.ipynb - Contains code to extract wilfire data for Grand Island,Nebraska from USGS dataset (Combined wildland fire datasets for the United States and certain territories, 1800s-Present combined wildland fire polygons)
- 2_fire_epa_air_quality_history_example.ipynb - Contains code to extract AQI data from US Environmental Protection Agency (EPA) Air Quality Service (AQS) API
- 3_smoke_estimate_and_visualizations.ipynb - Contains code to perform EDA on the wildfire and AQI data, perform correlation study, build ARIMA model
- 4_assessing_smoke_impact_on_copd_asthma_cases.ipynb - Contains code to perform EDA on public health data and correlation study with AQI.

__DATA GLOSSARY__

Important column names and their description are noted below:

Wildfire data

| Column Name          | Description                                    |
|----------------------|------------------------------------------------|
| wf_year              | Year of the wildfire event                     |
| wf_name              | Name or identifier of the wildfire             |
| wf_size              | Area in acres that was burnt by fire           |
| wf_type              | Type of wildfire (Prescribed, Actual , Likely) |
| ring_data            | Data related to the wildfire radius            |
| distance             | Distance of the wildfire from Grand Island     |
| closest_lat_long     | Latitude and longitude of the closest point    |
| wf_smoke_estimate    | Estimate of smoke produced by the wildfire     |


AQI Data

| Column Name          | Description                                           |
|----------------------|-------------------------------------------------------|
| sample_duration      | Duration of the sampling period (e.g., 24-HR BLK AVG) |
| observation_count    | Number of observations during the sampling period     |
| aqi                  | Air Quality Index (AQI) calculated for the observation |
| obsv_date            | Date of the observation                              |


COPD/ Asthma data

| Column Name               | Description                                                               |
|---------------------------|---------------------------------------------------------------------------|
| YearStart                 | Starting year of the data                                                 |
| Question                  | Indicates whether response is for ER Visit, Hospitalization or Mortality  |
| DataValueType             | Indicates whether the data value is an absolute number or rate.           |
| DataValue                 | Absolute number or metric                                                 |
| StratificationCategory1   | Dimension to slice on: can be Gender or Race                              |
| Stratification1           | If Category is Gender, then male/female. If Category is Race, then White, Black, Hispanic, etc                                                                                    |
| LocationDesc              | US State name for which CDC has published the data                        |


__DETAILED REPORT__
A detailed analysis of the problem , findings from our datasets , reflection and advice to city council members/policy makers is available here: 
https://docs.google.com/document/d/1WViAv4EkTCJYnUNa0TTlMkFHiUD4TDrTgXFDNUYwyvY/edit?usp=sharing