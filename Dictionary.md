**Data dictionary**

This dictionary is made considering df.dtypes output.


***Rates_of Cases_or_Deaths.csv***



|Field                    |Data type |Description                  |
|-------------------------------|---------------|----------------------------------|
|Outcome                    |object     |Covid-19 cases or deaths.|
|Month                      |object     |calendar and year corresponding to MMWR week. Format: M(str)/YYYY|
|MMWR week                  |int64      |morbidity and mortality weekly report. MMWR week represents the weeks in a year coded for epidemiologic report.|        |Age group                  |object     |0-4 years; 5-11 years; 12-17 years; 18-29 years; 30-49 years; 50-64 years; |
|                               |               |-65-79 years; 80+ years; and all_ages_adj.|
|Vaccine product            |object     |FDA-authorized COVID-19 vaccine product: Janssen; Moderna; Pfizer; all_types |
|                               |               |(Janssen, Moderna, Pfizer and unknown FDA-approved vaccine product)|
|Vaccinated with outcome    |int64      |number of vaccinated individuals with a specific outcome (case or death).|
|Fully vaccinated population|float64    |total population fully vaccinated.|
|Unvaccinated with outcome  |int64      |number of unvaccinated individuals with a specific outcome (case or death).|
|Unvaccinated population    |float64    |the total population unvaccinated.                            |
|Crude vax IR               |float64    |crude incidence rate for vaccinated individuals.                       |
|Crude unvax IR             |float64    |crude incidence rate for unvaccinated individuals.                        |
|Crude IRR                  |float64    |crude incidence rate ratio comparing vaccinated to unvaccinated.          |
|Age adjusted vax IR        |float64    |age-adjusted incidence rate for vaccinated individuals                    |
|Age adjusted unvax IR      |float64    |age-adjusted incidence rate for unvaccinated individuals.            |
|Age adjusted IRR           |float64    |age-adjusted incidence rate ratio.                                      |
|Continuity correction      |int64      |indicates whether a continuity correction was applied. It helps avoid overestimations|
|                               |               |or underestimations when comparing groups (vaccinated vs. unvaccinated).             |



***County_Level_of_community_Transmission.csv***



|Field               |Data type           |Description                                                                        |
|---------------------|-------------------|----------------------------------------|
|state_name           |object               |US State                             |
|county_name          |object           |US county.|
|fips_code            |int64           |county Federal Information Processing Standards (FIPS) code.|
|date               |object|Week ending date for the 7-day period for the case rate and the percent positivity.|
|               |                  |The last day of a 7-day period used to calculate case rate and percent positivity for COVID-19 data.|
|cases_per_100K_7_day_count_change|object |total number of new cases per 100,000 persons within the last 7 days.                |
|percent_test_results_reported_positive_last_7_days|float64|percentage of positive diagnostic and screening tests during the last 7 days.|
|community_transmission_level                      |object  |Community Transmission Level Indicator (low, moderate, substantial, high)|




***merged_df (merged SQL_data.db two tables (Covid_rates and trans_level)*** 



|Field                   |Data type |Description                                                   |
|--------------------------|---------|--------------------------------------------------------------------------------------------------------|
|date                    |converted to datetime64[ns]|Week ending date for the 7-day period for the case rate and the percent positivity.|
|                           |                                |The last day of a 7-day period used to calculate case rate and percent positivity |
|                            |                               |for COVID-19 data.                                                                 |
|community_transmission_level|object                 |Community Transmission Level Indicator (low, moderate, substantial, high)|
|date_formatted              |object                 |merged data formatted to MM/YYYY                                                   |
|month                       |datetime64[ns]         |calendar and year corresponding to MMWR week.                                      |
|Vaccinated with outcome     |float64                |number of vaccinated individuals with a specific outcome (case or death).        |
|Unvaccinated with outcome  |float64                 |number of unvaccinated individuals with a specific outcome (case or death)       |



