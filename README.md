
                                                        
                                                        
**COVID-19 Data Analysis**

**Abstract**

COVID 19 Data Analysis is a capstone project for the Code:You Data Analysis course. This study explores COVID-19 data to assess vaccine effectiveness in preventing COVID-19 infections and deaths. 

The goal of this study is to analyze the impact of vaccination and community transmission on COVID-19 infections and deaths, using quantitative data from reliable datasets, and present findings to inform public health strategies.

**Objectives**

-Analyze the Impact of Vaccination Status on Infection and Mortality Rates

-Assess the Influence of Community Transmission

-Identify Geographic disparities

-Develop Data-Driven Public Health Recommendations

**Steps**:

1. Define the study question: impact of vaccination and community transmission on COVID-19 infections and deaths;

2. Determine the primary goal and objectives;

3. Research the datasets needed for analysis;

4. Save datasets as csv file;

5. Perform preliminary analysis of raw data to understand and guide the cleaning process;

6. Clean data;

7. Perform in-depth analysis and visualization.

**Code:You Data Analysis project criteria**

The following criteria have been met:

1. Export two datasets from the Centers for Disease Control and Prevention (CDC) website: 

       https://data.cdc.gov/Public-Health-Surveillance/Rates-of-COVID-19-Cases-or-Deaths-by-Age-Group-and/3rge-nu2a/data_preview
       https://data.cdc.gov/Public-Health-Surveillance/United-States-COVID-19-County-Level-of-Community-T/nra9-vzzn/data_preview

2. Identify the required packages through a Google search, then use pip to install them. The installation of some packages like matplotlib, and seaborn did not work with pip install. They were installed using C:/Users/weare/AppData/Local/Programs/Python/Python312/python.exe -m pip install <name-of-package>.

3. Loading data

Save the two datasets as csv files in the Data/raw folder. Rename and read them in Python using pandas:

- Rates_of_Cases_or_Deaths.csv

- County_Level_of_Community_Transmission.csv

4. Clean and merge data

As you can read in the script 02_Data_Cleaning.ipynb, data were cleaned using pandas: 
                         
 •	Select important columns for analysis and delete unnecessary columns;
                         
 •	Handling duplicates and missing values;
                         
 •	Addressing outliers and inconsistencies. 

From the clean datasets, two tables were created and saved into a database (SQL_data.db), using pandas and SQL.

To analyse the relationship between transmission level and vaccination status, the two tables (Covid_rates and trans_level) were merged in SQL using a common identifier (date_formatted).

5. Present and visualize data

Histograms, heatmap, and scatter plot were used to examine the distribution and variable's relationship.

Example: The following scatter plot shows the number of outcomes for vaccinated and unvaccinated individuals at different levels of transmission.

![Vaccinated vs Unvaccinated Outcomes by Community Transmission Level](Vaccinated_vs_Unvaccinated_Outcomes_by_Community_Transmission_Level.png)

The chi-square test was used to quantify the relationship between vaccination and outcomes/community transmission levels. The result showed there was a statistical significant. Meaning that vaccinated individuals tend to have higher outcomes in areas with high transmission compared to unvaccinated individual.

6. Create pandas pivot tables for aggregation.

Example: create a pivot table from the df_seasons DataFrame and prepare the data for heatmap:

heatmap_data = df_seasons.pivot_table(index='state_name', columns='season', values='numeric_level', aggfunc='mean')

7. Use the virtual environment.
 
8. Build a data dictionary. 

9. Interpret and document.

**Summery of findings**

This analysis provides evidence for optimizing vaccination distribution and tailoring intervention strategies in eventual COVID-19 or other infectious disease 
outbreaks. From this analysis, vaccination plays a crucial role in reducing infections, particularly in older and broader age categories.The analysis shows that:

- Unvaccinated individuals are disproportionately contributing to COVID-19 case and death counts across all age groups. Unvaccinated individuals are more likely to become infected than those who are vaccinated. Younger, socially active groups contribute significantly to the case;

- Deaths among vaccinated individuals were consistently lower across all age groups, reflecting vaccine effectiveness in reducing mortality;

- Transmission levels appear to be relatively stable across seasons for most states, with no significant seasonal spikes or drops. This suggests that transmission levels might not be heavily influenced by seasonal factors in this dataset;

- There is a disparity in transmission level among different states. States like District of Columbia, and Delaware exhibit consistently higher transmission levels across all seasons. Hawaii and Nebraska show consistently lower transmission levels (blue shades).

- Assessing the relationship between transmission levels and vaccination, the study finds that vaccinated individuals tend to have higher outcomes in areas with high transmission compared to unvaccinated individuals (Refer to the scater plot above). This challenges the common belief that vaccination reduces virus transmission. It is important to note that this finding does not imply that vaccines are ineffectives.

**Recommendation**

- Enhance vaccination campaigns such as vaccination drives, and public awareness campaigns in younger, socially active populations;
- Focus on high risk groups (65 years old and plus) for mortality reduction;
- Allocate additional resources and implement stricter public health measures in states with consistently higher transmission levels;
- Develop state-specific strategies for improving vaccination coverage;
- Conduct further research to explore why vaccinated individuals tend to show higher outcomes in areas with high transmission;
- Address misconceptions about vaccine ineffectiveness by demonstrating their role in preventing severe outcomes and reducing deaths rather than completely  stopping transmission.

**Project layout**


|File                                |Description                                                                            | 	
|------------------------------------|---------------------------------------------------------------------------------------|
|README.md                           |General information about the project                                                  |
|Data/raw                            |raw data files                                                                         |
|Data/clean                          |cleaned data files                                                                     |
|Dictionary                      |Dictionary for the raw data                                                                |
|01_Preliminary_Analysis.ipynb        |jupyter notebook showing simple data analysis to understand the raw datasets               | 
|                                    |and guide the cleaning process.                                                        |
|02_Data_Cleaning.ipynb          |jupyter notebook showing the cleaning performed                                    |
|03_Exploratory_Analysis.ipynb   |jupyter notebook showing essential analysis aimed to answer the project's questions|

**Requirements to run the project**

*Git*: if not yet installed, you can download at https://git-scm.com/downloads

*Python*: this project uses python 3.12. If not yet, you can install or update python at https://www.python.org/downloads/

*Jupyter notebook* or *vs code*

*virtual environment(venv)*: 
           Installation: as you will use python 3, the venv is already installed.
           Create venv: python3 -m venv venv or python -m venv venv.
           Activate venv: source/Scripts/activate(for Windows users) or source venv/bin/activate(for Mac and Linux users).

*Package*: pip install requirements.txt. 

**Getting Started**

Clone this repo.

Create a virtual environment and install the packages listed in the requirements.txt file.

Open Data/raw file to view the raw data.

Run 02_Data_Cleaning.ipynb to clean the raw data.

Run 03_Exploratory_Analysis.ipynb file to view the analysis and visualizations.
