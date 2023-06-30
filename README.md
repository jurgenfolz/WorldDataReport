World Data Report
This is a Power BI report repository providing a comprehensive visualization of global data. The data spans various domains including demographics, socio-economic metrics, and weather conditions, enabling deeper insights into global patterns and trends.

Report Contents
The World Data Report is designed to deliver detailed insights on the following topics:

Weather Data: The report includes weather information from cities around the world with a population exceeding 15,000. This data is gathered through a combination of API calls and web data integration.

Geographic and Demographic Metrics: The report encapsulates a variety of geographical and demographic indexes including data on population, births, deaths, life expectancy at birth, and expected years of schooling, among others.

Socio-economic Metrics: The report also analyzes various economic indicators such as GDP, GDP per capita, Gross National Income (GNI), Human Development Index (HDI), and others. The socio-economic metrics provide an understanding of the economic health and living standards in different regions.

Data Acquisition and Processing
Data for the report is sourced and processed through a combination of API calls, web data integration, and local CSV files. The data acquisition process involves retrieval, unzipping, and processing of data within Power BI using custom functions.

This repository serves as a comprehensive resource for analysts, policy-makers, and data enthusiasts who want to explore and understand global trends based on extensive data and visually appealing, insightful reports.

Please refer to the README.md file for more details about the specific data used in the report, the sources of this data, and the data processing techniques employed.

PowerQuery
#"Added API Forecast call" = Table.AddColumn(#"Kept only city col", "APicall", each Json.Document(
    Web.Contents(
        "http://api.weatherapi.com",[RelativePath="v1/forecast.json?", Query=[
                    key=#"API Key",
                    days="10",
                    aqi="no",
                    q=[name]
                    ]])))
City Data
City data, including latitude and longitude, are sourced from a .zip file that is downloaded, unzipped, and processed within Power BI using a custom function.

The URL to access the city data is http://download.geonames.org/export/dump/.

Additional Parameters
Several other parameters are used in the data processing for the report:

Countries Info Text: "http://download.geonames.org/export/dump/countryInfo.txt"
PathToCSV: Local path for storing the processed data, "C:\\Users\\nini_\\OneDrive\\Área de Trabalho\\Drive\\Repositories\\Geography_Report\\Data\\"
Contents Details
The report contains the following metrics from various sources:

Attribute	Alias	Description	Source	Link	Parameter name
Deaths	Deaths	Number of deaths over a given period. Refers to annual civil calendar years from 1 January to 31 December.	United Nations - Population Division (2022)	UN - Population Division	Deaths
Births	Births	Number of births over a given period. Refers to annual civil calendar years from 1 January to 31 December.	United Nations - Population Division (2022)	UN - Population Division	Births
Carbon intensity of electricity (gCO2/kWh)	CIE	This dataset contains yearly electricity generation, capacity, emissions, import and demand data for over 200 geographies.	BP Statistical Review of World Energy; Ember	BP Review; Ember; Ember Insights	Carbon intensity of electricity (gCO2/kWh)
<!-- The table is too long to show completely. To view it in full, go to the [link]() -->
Please refer to the Power BI report for the complete list of metrics and their sources.