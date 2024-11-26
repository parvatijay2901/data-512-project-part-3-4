# Scripts

The code was executed on MacBook Pro. Before running this project, ensure that the required mentioned at the top of each of the scripts are installed. Additionally, please create the necessary folders and adjust the file paths as required for your environment.

To ensure the proper execution of the analysis, please follow the script order outlined below:

1. [src/step01_data_acquisition_fire_data.ipynb](../src/step01_data_acquisition_fire_data.ipynb)
This notebook is the first step in the project, where we conduct a base analysis using a shared dataset while focusing on a unique city. The aim is to create an understanding of wildfire impacts tailored to local contexts. It primarily obtains access to historical data of wildfires and computes the average distance between the city assigned and the fire perimeter to obtain the smoke estimate.

2. [src/step02_create_fire_smoke_estimates.ipynb](../src/step02_create_fire_smoke_estimates.ipynb)
This notebook focuses on creating estimates of wildfire smoke based on the data acquired in the previous step. It involves processing the wildfire data to generate smoke estimates that can be used for further analysis.

3.  [src/step03_data_acquisition_aqi.ipynb](../src/step03_data_acquisition_aqi.ipynb)
This notebook is responsible for acquiring Air Quality Index (AQI) data. It includes making API requests to the EPA AQS API to obtain historical AQI data, processing the data, and preparing it for analysis.

4. [src/step04_predictive_modeling_and_smoke_analysis.ipynb](../src/step04_predictive_modeling_and_smoke_analysis.ipynb)
This notebook involves predictive modeling and analysis of wildfire smoke and AQI data. It uses the ARIMA model to forecast smoke estimates and analyzes the relationship between smoke estimates and AQI values. The notebook also visualizes fire frequency, intensity, and total acres burned.

5. [src/step05_extension_plan_data_acquisition.ipynb](../src/step05_extension_plan_data_acquisition.ipynb)
This notebook extends the analysis by acquiring additional data related to socioeconomic and health impacts. It includes data on poverty rates, premature death rates, unemployment rates, and respiratory disease mortality rates in Clark County, WA. The notebook processes and visualizes these datasets to understand the community's vulnerability to wildfire smoke.

6.  [src/step06_extension_plan_data_modeling.ipynb](../src/step06_extension_plan_data_modeling.ipynb)
This notebook builds on the extended data acquired in the previous step. It involves modeling the relationships between wildfire smoke, and socioeconomic and health indicators. The notebook aims to provide insights into the broader impacts of wildfire smoke on the community.

For more comprehensive details regarding the datasets, including input data, intermediate files, and licensing information, please refer to the separate Datasets [README](../data/README.md).

The final project report, findings, and results can also be accessed [here](../doc/main_project_report.pdf). For a more detailed explanation of the project results, refer to [this](../doc/methodology_and_results.pdf) document.