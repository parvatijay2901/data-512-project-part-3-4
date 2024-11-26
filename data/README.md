# Data Sources and Licensing

In this analysis, we are working with multiple datasets. Due to space limitations, I have uploaded a few of the larger files to [Google Drive](https://drive.google.com/drive/folders/1yR7RkC28EGOouKa2W3QquWPzH_bZP3I_?usp=sharing). The main ones are included in this repository in the [`data/`](https://github.com/parvatijay2901/data-512-project-part-3-4/tree/main/data) folder.

## Input data
1. **USGS Wildland Fire Combined Dataset** This dataset serves as the primary source of data for the project and contains comprehensive wildfire data. 
    - **Description:** The dataset includes detailed information on wildfires and prescribed fires across the United States from the mid-1800s to the present.​ It merges data from 40 different sources, providing a rich and comprehensive view of wildfire activity over time. The dataset can be accessed from [Combined wildland fire datasets for the United States and certain territories, 1800s-Present (combined wildland fire polygons)](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81) or (can be downloaded directly from [here](https://drive.google.com/file/d/1Q2MNu6gKvN5TLv3YmcEbODpEzxJcOa8e/view?usp=share_link)).
    - **Columns:** The dataset contains a variety of attributes, including: 
        - **Fire_Year:** The calendar year when the fire occurred as determined by the dataset creators.
        - **Fire_Polygon_Tier:** The tier from which the fire polygon was generated; one or more polygons within the tier could be combined to create the fire polygon.
        - **Fire_Attribute_Tiers:** Lists all fire tiers that contributed attributes to the fire feature, indicating where a polygon intersects the fire perimeter in space and time.
        - **GIS_Acres:** The GIS-calculated area of the fire polygon in acres, derived using ArcGIS Pro's Calculate Geometry tool.
        - **GIS_Hectares:** The GIS-calculated area of the fire polygon in hectares, derived using ArcGIS Pro's Calculate Geometry tool.
        - **Source_Datasets:** Lists all original source datasets contributing to either the polygon or its attributes, with the number of polygons contributed indicated in parentheses.
        - **Listed_Fire_Types:** Each fire type from the merged dataset that intersects the polygon in space and time, with the number of features contributing the fire type listed in parentheses.
        - **Listed_Fire_Names:** Each fire name from the merged dataset that intersects the polygon in space and time, with the number of features contributing the fire name listed in parentheses.
        - **Listed_Fire_Codes:** Codes for each fire from the merged dataset that intersect the polygon; number of contributing features is indicated in parentheses.
        - **Listed_Fire_IDs:** Each fire ID from the merged dataset that intersects the polygon in space and time, with the number of contributing features indicated in parentheses.
        - **Listed_Fire_IRWIN_IDs:** Each IRWIN ID from the merged dataset intersecting the polygon, with the number of contributing features indicated in parentheses.
        - **Listed_Fire_Dates:** Dates associated with each fire in the merged dataset that intersect the polygon; the number of contributed features is indicated in parentheses.
        - **Listed_Fire_Causes:** Causes for each fire in the merged dataset that intersect the polygon; the number of contributing features is indicated in parentheses.
        - **Listed_Fire_Cause_Class:** Classifications for the causes of fires in the merged dataset that intersect the polygon; the number of contributing features is indicated in parentheses.
        - **Listed_Rx_Reported_Acres:** Reported acres of prescribed fires in the merged dataset that intersect the polygon; number of contributing features is indicated in parentheses.
        - **Listed_Map_Digitize_Methods:** The methods used to digitize the polygons in the merged dataset that intersect the polygon; the number of contributing features is indicated in parentheses.
        - **Listed_Notes:** Notes related to each fire in the merged dataset that intersects the polygon; the number of contributing features is indicated in parentheses.
        - **Processing_Notes:** Indicates any attribute changes made during processing, along with a justification for the changes.
        - **Wildfire_Notice:** A notice indicating the quality of wildfire data in the dataset.
        - **Prescribed_Burn_Notice:** A notice indicating the quality of prescribed burn data in the dataset.
        - **Wildfire_and_Rx_Flag:** A flag indicating whether the fire was classified as both a wildfire and a prescribed fire; may indicate errors in assignment.
        - **Overlap_Within_1_or_2_Flag:** Flags whether a fire overlaps with previous fires, indicating the extent of overlap and related attributes.
        - **Circleness_Scale:** A measure of how closely the polygon resembles a true circle, calculated using the shape area and perimeter.
        - **Circle_Flag:** Flags whether a polygon's circle-ness value is indicative of being circular, potentially highlighting incorrect classifications.
        - **Exclude_From_Summary_Rasters:** Indicates whether a fire was excluded from raster summary calculations due to being classified as circular.
        - **Shape_Length:** The calculated perimeter length of the polygon in meters.
        - **Shape_Area:** The calculated area of the polygon in square meters.
    - **Access:** The dataset is available in a zip format ([`GeoJSON Files.zip`](https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81) file) and is cited by Welty, J.L., and Jeffries, M.I. (2021). Combined wildland fire datasets for the United States and certain territories, 1800s-Present: U.S. Geological Survey data release[https://doi.org/10.5066/P9ZXGFY3](https://doi.org/10.5066/P9ZXGFY3). USGS-authored or produced data and information are considered to be in the U.S. Public Domain. This dataset is not copyrighted material, hence, when using information from USGS information products, publications, or websites, we need to provide proper credit. Credit can be provided by including a citation. For the ones not in the domain (this one is in the domain), [USGS policy on the use of copyrighted material](https://www.usgs.gov/about/organization/science-support/survey-manual/use-copyrighted-material-usgs-information-products). These materials are generally marked as being copyrighted. To use these copyrighted materials, we must obtain permission from the copyright holder under [copyright law](http://www.copyright.gov/). For more information, refer to [usgs.gov: copyrights-and-credits](https://www.usgs.gov/information-policies-and-instructions/copyrights-and-credits).

2. **Air Quality Index Data:** Air Quality Data was needed to evaluate the performance of the smoke estimate created. 
    - **Description:** This data was requested from the US Environmental Protection Agency (EPA) Air Quality Service (AQS) API. This is a historical API and does not provide real-time air quality data. The [documentation](https://aqs.epa.gov/aqsweb/documents/data_api.html) for the API provides definitions of the different call parameters and examples of the various calls that can be made to the API. The US EPA was created in the early 1970's. The EPA reports that they only started broad based monitoring with standardized quality assurance procedures in the 1980's. Many counties will have data starting somewhere between 1983 and 1988. However, some counties still do not have any air quality monitoring stations. The API helps resolve this by providing calls to search for monitoring stations and data using either station ids, or a county designation or a geographic bounding box. Some additional information on the Air Quality System can be found in the [EPA FAQ on the system](https://www.epa.gov/outdoor-air-quality-data/frequent-questions-about-airdata). 
    - **Columns:**
        - **date:** Date of the observed air quality measurement.
        - **site_id:** Unique identifier for the air quality monitoring site.
        - **state:** The state where the monitoring site is located.
        - **county:** The county designation for the air quality monitoring site.
        - **pollutant_type:** Type of pollutant being measured (e.g., PM2.5, Ozone).
        - **sample_duration:** Length of time the sample was taken (e.g., 24 hours).
        - **arithmetic_mean:** Average concentration of the pollutant for the specified sample duration.
        - **AQI:** Air Quality Index value calculated based on the measured pollutant concentration, indicating the overall air quality level.
        - **value_represented:** Description of what is captured by the parameter being measured.
        - **observation_count:** Total number of observations used to calculate the arithmetic mean for that day.
    - **Access:** The AQS API is publicly accessible and provides access to ambient air sample data collected by various pollution control agencies. Users are expected to be familiar with the terms of service that govern the use of the API. These [terms](https://aqs.epa.gov/aqsweb/documents/data_api.html#terms) outline acceptable usage practices and any restrictions on data access and storage. 

3. **Respiratory Disease Mortality (IHME)**: This dataset provides information on mortality rates due to various respiratory diseases in Clark County, which includes Vancouver.
    - **Description:** Contains data related to various respiratory conditions, categorized by cause and sex for years: 1980 to 2014. The dataset can be accessed from [here](https://ghdx.healthdata.org/record/ihme-data/united-states-chronic-respiratory-disease-mortality-rates-county-1980-2014) and can be further filtered to obtain Clark County, WA. Alternatively, it can be directly downloaded from [here](https://github.com/parvatijay2901/data-512-project-part-3-4/tree/main/data/input_data/healthcare_data)
    - **Columns:** 
        - **date:** Date of the observed measurement.
        - **measure_id:** Unique identifier for the health measure being reported.
        - **measure_name:** Name of the health measure.
        - **location_id:** Unique identifier for the geographic location.
        - **location_name:** Name of the location where the data was collected (e.g., "Clark County").
        - **FIPS:** Federal Information Processing Standards code, a unique identifier for geographic areas.
        - **cause_id:** Unique identifier for specific causes of respiratory disease.
        - **cause_name:** Name of the cause of death (e.g., "Chronic respiratory diseases").
        - **sex_id:** Unique identifier for sex categorization (e.g., Male, Female).
        - **sex:** The sex of individuals represented in the data (e.g., "Both", "Male", "Female").
        - **age_id:** Unique identifier for age groups in the dataset.
        - **age_name:** Description of the age group (e.g., "All Ages").
        - **year_id:** Year corresponding to the data entry (e.g., "1980").
        - **metric:** Specifies the type of metric (e.g., "Rate" or "Count").
        - **mx:** Value representing the mortality rate for the specified cause (e.g., deaths per 100,000).
        - **lower:** Lower confidence interval for the mortality rate estimate.
        - **upper:** Upper confidence interval for the mortality rate estimate.
    - **Access:** The dataset is available in a CSV format. The terms and conditions for using the data from the Institute for Health Metrics and Evaluation (IHME) are governed by the IHME FREE-OF-CHARGE [NON-COMMERCIAL USER AGREEMENT](https://www.healthdata.org/Data-tools-practices/data-practices/ihme-free-charge-non-commercial-user-agreement).​ Users are permitted to use, share, modify, or build upon the data for non-commercial purposes. For inquiries related to commercial use, it is advised to refer to the [IHME Terms and Conditions](https://www.healthdata.org/data-tools-practices/data-practices/terms-and-conditions).  For detailed information, it is recommended to consult the [IHME website](https://www.healthdata.org/data-tools-practices/data-practices/terms-and-conditions) directly.

4. **Unemployment rate (FRED):** Includes the data from the Federal Reserve Bank of St. Louis Economic Data (FRED) that covers unemployment rates and economic activity in Clark County.
    - **Description:** This dataset includes time series data on unemployment rates (years: 1990 - 2024), which can be correlated with smoke events and economic downturns. The dataset can be accessed from here: [https://fred.stlouisfed.org/series/WACLAR1URN](https://fred.stlouisfed.org/series/WACLAR1URN) or can be directly downloaded from [here](https://github.com/parvatijay2901/data-512-project-part-3-4/blob/main/data/input_data/socioeconomic_data/FRED_Unemployment_rate_Clark_County.csv).
    - **Columns:** 
        - **DATE:** Date when the measurement was recorded.
        - **WACLAR1URN:** Unemployment Rate (%)
    - **Access:** The dataset is available in a CSV format and can be used freely.​ The data is available for public access without any subscription or payment required. When using the data, proper citation of the source is encouraged. It is important to credit FRED as the source of the data. Users are mainly encouraged to use the data for non-commercial purposes. FRED data is typically released under a Creative Commons license which allows for use, sharing, modification, and adaptation as long as appropriate credit is given. For detailed terms, refer to the [FRED website](https://fredhelp.stlouisfed.org/fred/graphs/share-my-fred-graph/cite/).

5. **Poverty rate (FRED)**Includes the data from the Federal Reserve Bank of St. Louis Economic Data (FRED) that covers poverty rates (age 0-17) and economic activity in Clark County.
    - **Description:** This dataset includes time series data on poverty rates (years: 1989-2022), which can be correlated with smoke events and economic downturns. The dataset can be accessed from here: [https://fred.stlouisfed.org/series/PPU18WA53011A156NCEN](https://fred.stlouisfed.org/series/PPU18WA53011A156NCEN) or can be directly downloaded from [here](https://github.com/parvatijay2901/data-512-project-part-3-4/blob/main/data/input_data/socioeconomic_data/FRED_Poverty_Clark_County.csv).
    - **Columns:** 
        - **DATE:** Date when the measurement was recorded.
        - **PPU18WA53011A156NCEN:** Poverty Rate (%)
    - **Access:** The dataset is available in a CSV format and can be used freely.​ The data is available for public access without any subscription or payment required. When using the data, proper citation of the source is encouraged. It is important to credit FRED as the source of the data. Users are mainly encouraged to use the data for non-commercial purposes. FRED data is typically released under a Creative Commons license which allows for use, sharing, modification, and adaptation as long as appropriate credit is given. For detailed terms, refer to the [FRED website](https://fredhelp.stlouisfed.org/fred/graphs/share-my-fred-graph/cite/).

6. **Premature Death Rate (FRED):** Includes data from the Federal Reserve Bank of St. Louis Economic Data (FRED) that covers premature death rates in Clark County.
    - **Description:** This dataset includes time series data on premature death rates, which can be correlated with smoke events and economic downturns. The dataset can be accessed from here: [https://fred.stlouisfed.org/series/CDC20N2UAA053011](https://fred.stlouisfed.org/series/CDC20N2UAA053011) or can be directly downloaded from [here](https://github.com/parvatijay2901/data-512-project-part-3-4/blob/main/data/input_data/socioeconomic_data/FRED_Premature_Deaths_Clark_County.csv).
    - **Columns:** 
        - **DATE:** Date when the measurement was recorded.
        - **CDC20N2U053011:** Premature Death (per 100k)
    - **Access:** The dataset is available in a CSV format and can be used freely.​ The data is available for public access without any subscription or payment required. When using the data, proper citation of the source is encouraged. It is important to credit FRED as the source of the data. Users are mainly encouraged to use the data for non-commercial purposes. FRED data is typically released under a Creative Commons license which allows for use, sharing, modification, and adaptation as long as appropriate credit is given. For detailed terms, refer to the [FRED website](https://fredhelp.stlouisfed.org/fred/graphs/share-my-fred-graph/cite/).

## Intermediate Data

The intermediate data files can be accessed [here](https://drive.google.com/drive/folders/1ourdQkuUAiW_qeXRpL0K_y6oiG-ZwQgX?usp=share_link), specifically:

- [wildfire_dataset_with_distance.csv](https://drive.google.com/drive/folders/1ourdQkuUAiW_qeXRpL0K_y6oiG-ZwQgX?usp=share_link): All the valid 118465 wildfire instances close to Vancouver, WA are mentioned here. 
- [wildfire_dataset_with_distance_cutoff.csv](https://drive.google.com/file/d/1Mlcswoag46e3cPsug-51mddHWsc5nIOS/view?usp=sharing): All the 68394 filtered wildfire instances are mentioned here (according to the assignement specifications). 
- [wildfire_dataset_with_distance_and_smoke_estimate_by_date.csv](https://drive.google.com/file/d/1Mlcswoag46e3cPsug-51mddHWsc5nIOS/view?usp=sharing) and [wildfire_dataset_with_distance_and_smoke_estimate_by_date.csv](https://drive.google.com/file/d/1Mlcswoag46e3cPsug-51mddHWsc5nIOS/view?usp=sharing): Filtered Wildfire datasets across all the dates and grouped by year are available here.
- [aqi_data_grouped_by_date.csv](https://github.com/parvatijay2901/data-512-project-part-3-4/blob/main/data/input_data/AQI_data/aqi_data_grouped_by_date.csv) and [filtered_fire_season_aqi_data_grouped_by_year.csv](https://github.com/parvatijay2901/data-512-project-part-3-4/blob/main/data/input_data/AQI_data/filtered_fire_season_aqi_data_grouped_by_year.csv): AQI data grouped by dates and years (for the fire season) are available here.
