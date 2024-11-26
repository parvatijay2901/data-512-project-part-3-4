# Part 3 & 4 - Project Repository and Presentation
## Tackling wildfire smoke in **Vancouver, WA**

## Project Goal
​The primary goal of this project is to assess and understand the public health and economic impacts of wildfire smoke in Vancouver, WA, particularly in the context of increasing wildfire frequency and intensity due to climate change.​ By employing a human-centered data science approach, the project aims to illuminate how wildfire smoke exposure affects the respiratory health of the community, while also examining its broader socio-economic implications, including unemployment, poverty, and premature death rates.

**To achieve this goal, the project will:**
- **Investigate the Health Impacts:** Analyze the correlation between wildfire smoke exposure and respiratory diseases, focusing on mortality rates from chronic respiratory conditions. This involves examining historical health data and identifying trends related to air quality fluctuations over time.
- **Evaluate Economic Consequences:** Assess how wildfire smoke impacts economic stability by exploring relationships between smoke exposure and socio-economic indicators, such as the unemployment rate and poverty levels. The analysis will help identify populations at higher risk for adverse economic outcomes due to environmental factors.
- **Develop Predictive Models:** Utilize statistical and predictive modeling techniques, specifically the ARIMA model, to forecast the future trends of smoke exposure and their potential impacts on health and economy. The forecasts will enable proactive measures for public health planning and resource allocation to mitigate harmful effects.
- **Provide Actionable Insights:** Generate findings that can inform local policymakers, city officials, and public health practitioners about the urgent need for interventions and policies to combat the effects of wildfire smoke. The study seeks to support community resilience by providing recommendations for monitoring air quality, enhancing healthcare services, and promoting public awareness campaigns.

Ultimately, the project aspires to contribute to a deeper understanding of the complex relationships between environmental hazards, health outcomes, and economic conditions, thereby enhancing the capacity of Vancouver to respond effectively to the growing challenges posed by wildfires.

This project follows to the best practices for open scientific research as mentioned in chapters "Assessing Reproducibility" and "The Basic Reproducible Workflow Template" of ["The Practice of Reproducible Research: Case Studies and Lessons from the Data-Intensive Sciences"](https://www.ucpress.edu/books/the-practice-of-reproducible-research/paper) publication, ensuring transparency and reproducibility throughout the process.

## Licenses

### Datasets used
For more information about the datasets, including licensing details, please refer to the accompanying [README.md](https://github.com/parvatijay2901/data-512-project-part-3-4/blob/main/data/README.md).

### Repository
The repository is licensed under the MIT License, and it permits users to freely use, modify, and distribute the code, provided that the original copyright notice and permission notice are included in all copies or substantial portions of the software.

This project includes a few snippets of code developed by Dr. David W. McDonald for use in the DATA 512 course at the University of Washington's MS in Data Science program. These snippets are shared under the [Creative Commons CC-BY license](https://creativecommons.org/). Revision 1.1 - August 16, 2024, which permits reuse and distribution with proper attribution.

## Workflow and File Paths

The code was executed on MacBook Pro. Before running this project, ensure that the required mentioned at the top of each of the scripts are installed. Additionally, please create the necessary folders and adjust the file paths as required for your environment.

This project is divided into multiple parts, and the details for each can be accessed through:

- **Part 1 (Initial data exploration, acquisition, and setup):** This part (can be accessed [here](https://github.com/parvatijay2901/data-512-project-part1)) involves analyzing the impact of wildfires on Vancouver, WA, over the past 60 years, with a focus on estimating the effects of wildfire smoke on public health and air quality. The objective is to estimate the annual smoke impact based on wildfire occurrences, visualize historical wildfire trends, and build a predictive model for future smoke impacts. Key tasks include acquiring historical wildfire data, calculating the distance between fire perimeters and Vancouver, obtaining air quality index (AQI) data, and performing initial analysis. The section also involves creating visualizations to represent wildfire occurrences, acreage burned, and smoke estimates.
- **Part 2 (Extension Plan):** This part (can be accessed [here](https://github.com/parvatijay2901/data-512-project-part2)) builds on the common analysis from Part 1 and focuses on developing a human-centered data science question to inform local governance about the impacts of smoke on the community. The goal is to explore various effects of smoke, particularly on health and economic issues in Vancouver, WA, caused by wildfires. In this repository, the extension plan is laid out to achieve this goal. The Jupyter notebook ([`src/step05_extension_plan_data_acquisition.ipynb`](https://github.com/parvatijay2901/data-512-project-part-3-4/blob/main/src/step05_extension_plan_data_acquisition.ipynb)) is used for data acquisition and initial processing. Key datasets include poverty rates, premature death rates, unemployment rates, and respiratory disease mortality rates in Clark County, WA. These datasets are processed and visualized to better understand the community's vulnerability to wildfire smoke.
- **Part 3 (Project Presentation):** This part focuses on effectively communicating the course project findings through a [PechaKucha-style presentation](https://en.wikipedia.org/wiki/PechaKucha). The deck consists of 10 slides, each advancing automatically every 20 seconds. Here is the link to the [presentation deck](https://github.com/parvatijay2901/data-512-project-part-3-4/blob/main/doc/presentation_deck.pdf).
- **Part 4 (Project Repository):** This part focuses on creating a fully documented repository for the course project (which is this repository!). This repository includes codes, a written report detailing all results of the assigned city (including Part 1 and your Part 2 extension), data descriptions, links to sources, and documentation for any models used. 

For more comprehensive details regarding the **datasets, including input data, intermediate files, and licensing information**, please refer to the separate Datasets [README](https://github.com/parvatijay2901/data-512-project-part-3-4/blob/main/data/README.md). 

Additionally, instructions on **how to run the code** and other setup-related information are provided in a different [README](https://github.com/parvatijay2901/data-512-project-part-3-4/blob/main/src/README.md).

The **final project report**, findings, and results can also be accessed [here](https://github.com/parvatijay2901/data-512-project-part-3-4/blob/main/doc/main_project_report.pdf). 

You can refer to the [methodology_and_results.pdf]((https://github.com/parvatijay2901/data-512-project-part-3-4/blob/main/doc/methodology_and_results.pdf)) document for a comprehensive **understanding of the results**.

## Known Issues and Special Considerations
- **Data Quality and Limitations:**
    - **Incomplete Data Capture:** The datasets utilized may not encompass all relevant wildfires. ​Reporting inconsistencies and gaps in historical records, especially for smaller or remote fires, may lead to an underrepresentation of the true smoke impact in the area, compromising the accuracy of the analysis.​
    - **Simplicity of Smoke Estimates:** The smoke estimates generated rely on simplified assumptions about fire size, type, and distance from Vancouver. These estimates do not incorporate critical variables influencing smoke distribution, such as wind direction, atmospheric conditions, fire duration, and topographical features, which could lead to inaccuracies in smoke impact assessments.
- **Modeling Assumptions:**
    - **Impact of Assumptions:** The assumptions made regarding fire type and size significantly affect smoke estimates. Although fire types vary in their emissions and smoke impact, the reliance on weighted values may oversimplify these effects, neglecting important differences in burn behavior and resulting emissions under varied environmental conditions.
    - **Stationarity Requirement of ARIMA:** The ARIMA model employed for forecasting necessitates that the input time series data be stationary. Although the data was differenced to achieve stationarity, this process may inadvertently remove underlying trends, potentially leading to forecasting inaccuracies over extended time horizons.
- **Temporal and Spatial Considerations:**
    - **Ignoring Seasonal Variations:** The analysis does not account for temporal factors, such as seasonal variations in wildfire occurrence and the associated weather patterns that may influence air quality and smoke dispersion. The historical timeframe analyzed might not accurately predict future trends, especially in light of changing climate patterns.
    - **Limited Spatial Scope:** While the study primarily focuses on Vancouver, WA, it is essential to consider that wildfires occurring in distant regions can also impact local air quality, albeit to a lesser extent. The model does not adequately address the cumulative effects of multiple wildfires beyond a cutoff distance of 650 miles, which could lead to an underestimation of the broader air quality issues.
- **Correlation with AQI:**
    - **Weak Correlation Observed:** The weak Spearman correlation between smoke estimates and AQI values suggests that there may be other significant factors influencing air quality. This indicates that smoke exposure alone may not fully explain fluctuations in AQI, emphasizing the need for a multifactorial approach in analyzing air quality.
- **Forecasting Limitations:**
    - **Long-Term Projections Uncertainty:** Projections extending 25 years into the future involve significant uncertainties. Variable factors such as land use change, fire management practices, climate policy, and evolving wildfire behavior as a response to climate change can substantially affect future smoke estimates, thus complicating long-term forecasting accuracy.

## Research Practices 

The project was guided by human-centered principles that emphasized accountability, transparency, and the relevance of data to community needs. Following the best practices outlined in “The Practice of Reproducible Research,” I structured the repository with a clear hierarchical organization, creating distinct directories for [`src/`](https://github.com/parvatijay2901/data-512-project-part-3-4/tree/main/src), [`data/`](https://github.com/parvatijay2901/data-512-project-part-3-4/tree/main/data), and [`doc/`](https://github.com/parvatijay2901/data-512-project-part-3-4/tree/main/doc). This setup enhanced accessibility and clarity, allowing users to easily navigate through scripts and identify dependencies clearly listed at the top of each script. I automated the workflow using Jupyter notebooks, facilitating seamless re-execution of analyses, while avoiding hard-coded paths to ensure adaptability across different environments. This README file provides explicit instructions on how to run the project and understand its objectives.

Reflecting on the application of human-centered data science principles, I prioritized the lived experiences of community members affected by environmental factors. The analysis included an assessment of the direct health consequences of smoke exposure. I explicitly considered the geographic proximity of wildfires to these communities, which highlighted areas at greater risk, particularly in neighborhoods of Vancouver, WA. Such a focus ensured that my recommendations, including the establishment of clean air shelters, were relevant and actionable, directly addressing the specific needs of those impacted.

I also included socioeconomic indicators alongside health metrics to present a comprehensive view, reflecting the complex interactions between health and economic conditions. By integrating data on unemployment rates, poverty levels, and respiratory disease mortality, I underscored the importance of economic resilience in public health interventions and aimed to promote equity in health outcomes. Throughout the project, I adhered to best practices for open scientific research, ensuring transparency and trust by documenting data sources and methodologies. 

## Additional Notes
ChatGPT was used in this assignment as a grammar and vocabulary checker, as well as to rephrase content that I wrote myself.