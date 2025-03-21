# GIS_Data_Science
## Assignment: GIS Data Science for Climate in Nepal
### Objective:
- The purpose of this assignment is to apply my knowledge and practical skills in GIS Data Science to analyze climate data for Nepal. Using Python, I will perform tasks such as reading datasets, creating visualizations, and conducting exploratory data analysis (EDA). Through this assignment, I aim to demonstrate my ability to process spatial and climate data, identify trends, and derive insights that can help address climate-related challenges in Nepal. This will also help me strengthen my understanding of how GIS and data science tools can be used to analyze and interpret real-world environmental data.

### Setting up environment and running python scripts
#### Editor: VSCode
#### Python version: python 3.10.11
#### Libraries used: pandas, geopandas, matplotlib, seaborn, rasterio, rasterstats
#### Instruction to set up virtual environment:
>- Make sure to be in the right direcotry.
>- Press "Ctrl+Shift+P" on the VSCode editor or go on search and type ">python interpreter".
>- From the dropdown select python interpreter > Create Virutal Environment > select Venv # Creates a '.venv' virtual environment in the current workspace.
>- Choose the python version and its ready to go.
#### Setting up python environment
>- Open the terminal and make sure to be inside the right directory.
>- Type "pip install pandas, geopandas, matplotlib, seaborn, rasterio, rasterstats" or "pip install -r requirements.txt" and hit "Enter" to install all the required libraries required for this project. Wait for all the dependencies to be installed before starting the project.
>- Create a main.ipynb file to start the project.

#### Data Information for analysis:
>- The data for the analysis of this assigment is downloaded from https://github.com/Desmondonam/Nepal_Climate_change. and copyed in folder "data".
>- The data folder contains the two folders "nepal_climate_data" and "Shape_Data".
>- The nepal_climate_data folder contains geospatial data information (like nepal_glaciers, nepal_admin_regions and nepal_rivers) and raster data (such as nepal_precipitation and nepal_temperature). These data are provided for the year 2020 and 2050 BS.
>- The Shape_Data folder contains map of nepal in which can be used accessed using local_units.shp file.

#### Short Information on Libraries
>- Pandas: Tabular data manipulation and analysis.
>- GeoPandas: Geospatial vector data analysis and visualization.
>- Matplotlib: Basic and custom visualizations.
>- Seaborn: Advanced statistical visualizations.
>- Rasterio: Reading, writing, and processing raster data.
>- Rasterstats: Summarizing raster data based on vector geometries.
These libraries form the backbone of GIS Data Science workflows, enabling efficient data analysis, visualization, and interpretation of climate and geospatial data.

### Code for analysis:
>- Codes for  Exploratory Data Analysis (EDA) is provided in main.ipynb. Each GeoSpatial data file and raster data file is analyzed separately and their findings, insights, implications and summary is provided seperately in main.ipynb file. However, the instruction ask us to provide in the documentation file, I will write down the details of each analysis seperately here and provide the final conclusion.

### Data preprocessing:
>- Datas were checked for any null values but found none. So, preprocessing/cleaning of data was not necessary. However, raster data were added to the nepal_map geodataframe for better visualization using rasterstats library.

### Findings on raw data:
>- Upon reading and analyzing the data it is found that geometry for nepal_admin_region, nepal_glacier and nepal_river were all randomized and were not the acutal coordiate points.

--------------------------------------------
### Analysis of nepal_admin_regions.gpkg
--------------------------------------------
##### Findings:
>The finding are provieded below:
>>###### Climate Vunerability Index:
>>>The data provides the climate vunerability indices for 7 provinces of Nepal ranging from 0 to 1 for year 2020 and 2050, where higher values indicates the greater vulnerability to climate change impacts.
>>###### Descriptive Statistics:
>>>###### Mean: 
>>>>* Year 2020: The average climate vulnerability index is approximately 0.473
>>>>* Year 2025: The average climate vulnerability index is approximately 0.651
>>>###### Standard Deviation:
>>>>* Year 2020: The standard deviation is about 0.135, indicating variability in vulnerability across provinces.
>>>>* Year 2025: The standard deviation is about 0.185, suggesting an increase in variablity in climate vulnerability from year 2020 to 2050.
>>>###### Minimum and Maximum:
>>>>* Year 2020: The minimum climate vulnerability index is 0.323 in Sudurpashchim province while the maximum vulnerability is 0.680 in Province 2.
>>>>* Year 2050: The minimum climate vulnerability index is 0.408 in Sudurpashchim Province and the maximum is 0.939 in Province 2, where it is seen that there has been a significant increase in climate vulnerability from year 2020 to 2050.
##### Insights:
>1) Increasing Climate Vulnerability: There is a clear trend of increasing climate vulnerability from year 20202 to 2050 across all provinces. This suggests that the impacts of climate change has worsen over time.
>2) Province 2: This province has the highest climate vulnerabilty indices for year 2020 to 2050, indicating it is the most susceptible to climate change impacts.
>3) Sudurpashchim: Despite having the lowest current vulerabiltiy indices, this province susciptibility to climate vulnerability is relatively high.
>4) Variablity: The standard deviation for 2050 is higher than for 2020, indicating that the differences in climate vulnerability between provinces has increased over time.
##### Implications:
>1) Policy Prioritization: Provinces with higher climate vulnerability indices like Province 2, should be prioritized for climate adaptation and mitigation efforts.
>2) Long-Term Planning: The projected increases in vulnerability highlight the need for long-term planning and investment in climate change adaptation strategies.
##### Summary:
>The data and EDA analysis collectively reveal a concerning trend of increasing climate vulnerability across provinces in Nepal from 2020 to 2050. Province 2 stands out as particularly vulnerable since 2020 to 2050, while Sudupashchim is has also a significant rise in vulerability though this is the least vunerable to climate change in comparision to other provinces. The increasing variability indices in all provinces suggests that the impacts of climate change has been felt unevenly across provinces, necessitating targeted and tailored responses. Policymakers should prioritize provinces with higher climate vulnerability indices and invest in building resilience to migitate the adverse effects of climate chage in coming years.


--------------------------------------------
### Analysis of nepal_glaciers.gpkg
--------------------------------------------
#### Findings & Insights:
>###### 1) Increasing Glacier Retreat Over Time
>>* The histograms show that glacier retreat is increasing significantly from 2020 to 2050.
>>* In 2050, the distribution of retreat values shifts higher, indicating more severe glacier loss.
>###### 2) Greater Variability in Future Glacier Retreat
>>* The boxplot highlights that the spread of glacier retreat values in 2050 is wider compared to 2020.
>>* This suggests that while some glaciers may retreat gradually, others may experience extreme melting.
>###### 3) Strong Positive Correlation Between Glacier Retreat in 2020 and 2050
>>* The scatter plot shows a clear upward trend, meaning glaciers that retreated more in 2020 have retreated even more in 2050.
>>* The correlation heatmap confirms a strong relationship, suggesting that current melting trends will continue and worsen.
>###### 4) Geographic Variability in Glacier Retreat
>>* The spatial plot highlights specific regions with higher glacier retreat percentages, indicating that some areas are more vulnerable than others.
>>* These areas may be experiencing higher temperatures or changes in precipitation patterns.

##### Implications

>###### 1) Water Scarcity Risks 
>>* Many rivers depend on glacier melt for freshwater. If glaciers continue retreating at this rate, water shortages could occur, especially in downstream regions.
>###### 2) Increased Flood Risks & Glacial Lake Outbursts 
>>* Faster glacier retreat can form unstable glacial lakes, increasing the risk of flooding and natural disasters.
>###### 3) Impacts on Biodiversity & Ecosystems 
>>* Wildlife and plant species dependent on glacial water may face habitat loss.
>###### 4) Climate Change Acceleration 
>>* The loss of glaciers reduces Earth's reflectivity (albedo effect), causing further warming.
>###### 5) Need for Policy Action & Climate Mitigation 
>>* Governments and researchers must implement conservation strategies and monitor glaciers continuously.

##### Summary
> The analysis highlights a significant and accelerating trend of glacier retreat from 2020 to 2050.The data suggests that glacier loss will impact water availability, increase flood risks, and contribute to climate change. Spatial trends indicate that some regions will be more affected than others, necessitating targeted intervention. Without mitigation efforts, glacial loss will continue to accelerate, threatening ecosystems and human settlements.


--------------------------------------------
### Analysis of nepal_rivers.gpkg
--------------------------------------------
##### Findings
>###### Flow Reduction:
>>- All rivers show a reduction in flow from 2020 to 2050.
>>- The rivers with the highest reduction percentages are Karnali and Mahakali (12.5%).
>###### Flow Values:
>>- Koshi has the highest flow in both 2020 and 2050.
>>- Mahakali has the lowest flow in both years.
>###### Geographical Distribution:
>>- The rivers are located in different regions, with Koshi being the easternmost and Mahakali being the westernmost.

##### Insights
>- The flow reduction could be due to various factors such as climate change, water usage, or changes in land use.
>- The geographical distribution of the rivers suggests that the reduction might be influenced by regional differences in climate and human activities.

##### Implications
>- Water Management: The reduction in flow could impact water availability for agriculture, drinking water, and industrial use.
>- Environmental Impact: Lower flows might affect aquatic ecosystems and biodiversity.
>- Policy and Planning: This data could inform water management policies and planning for future infrastructure projects.

##### Summary
>- The EDA reveals that all rivers in the dataset experience a reduction in flow from 2020 to 2050, with Karnali and Mahakali showing the highest reduction percentages. The geographical distribution of the rivers suggests regional differences in flow reduction. These findings have significant implications for water management, environmental impact, and policy planning. Further investigation into the causes of flow reduction is recommended.


-----------------------------------------------------------------------------
### Analysis of nepal_precipitation_2020.tif vs nepal_precipitation_2050.tif
-----------------------------------------------------------------------------
##### Findings:
>- ###### Mean Precipitaion: 
>>-Analysis of mean precipitation data reveals that the eastern region of Nepal historically experiences higher precipitation levels compared to the western region. However, a significant decline in precipitation is projected in the eastern part of the country from 2020 to 2050.
>- ###### Max Precipitation: 
>>- By 2050, maximum precipitation levels have increased across Nepal, particularly in the Himalayan and Terai regions. This indicates a likelihood of more intense rainfall events and extreme weather occurrences nationwide.
>- ######Min Precipitation: 
>>- Regions with historically low minimum precipitation in 2020 have experienced an increase in minimum precipitation by 2050. Conversely, areas that previously recorded higher-than-average minimum precipitation bobserved a decrease in precipitation. This suggests a shift in precipitation distribution patterns over time.

##### Insights:
>- ###### Regional Variability in Precipitation: 
>>- The eastern part of Nepal historically receives higher precipitation compared to the western region. However, this trend is shifting, with a significant drop in mean precipitation in the eastern part from 2020 to 2050.
>- ###### Increased Extreme Precipitation Events: 
>>- Maximum precipitation is projected to increase across Nepal by 2050, particularly in the Himalayas and Terai regions. This suggests a rise in extreme weather events, such as heavy rainfall and flooding.
>- ###### Shifts in Minimum Precipitation: 
>>- Areas that previously had low minimum precipitation in 2020 are likely to experience an increase by 2050, while regions with historically higher minimum precipitation may see a decrease. This indicates a potential redistribution of rainfall patterns.

##### Implications:
>- ######Water Resource Management:
>>- The decline in mean precipitation in the eastern region could lead to water scarcity, affecting agriculture, hydropower, and daily water supply. Policymakers and planners need to focus on sustainable water management strategies.
>- ######Disaster Preparedness: 
>>- The increase in maximum precipitation, especially in the Himalayas and Terai, raises the risk of flooding, landslides, and other natural disasters. Enhanced disaster preparedness and infrastructure resilience will be critical.
>- ###### Agricultural Adaptation: 
>>- Changes in minimum precipitation patterns may impact crop yields and farming practices. Farmers may need to adapt by shifting to drought-resistant crops or altering planting schedules.
>- ###### Ecological Impact: 
>>- Shifts in precipitation patterns could affect ecosystems, particularly in regions with decreasing rainfall. Biodiversity conservation efforts may need to account for these changes.

##### Summary:
The precipitation trends in Nepal from 2020 to 2050 indicate significant changes, with a notable drop in mean precipitation in the eastern region and an increase in maximum precipitation across the country, particularly in the Himalayas and Terai. Minimum precipitation is also expected to shift, with increases in historically dry areas and decreases in regions with higher baseline precipitation. These changes have far-reaching implications for water resource management, disaster preparedness, agriculture, and ecological conservation. Proactive measures will be essential to mitigate the impacts and adapt to the evolving climate scenario.


-----------------------------------------------------------------------------
### Analysis of nepal_temperature_2020.tif vs nepal_temperature_2050.tif
-----------------------------------------------------------------------------
##### Findings:
>- ###### Mean Temperature: 
>>- A gradual but consistent increase in mean temperature has been observed nationwide from 2020 to 2050. This indicates a long-term warming trend across Nepal.
>- ###### Maximum Temperature: 
>>- While there has been a slight increase in maximum temperature over the same period, no significant rise has been recorded. This suggests that extreme daytime temperatures have remained relatively stable from 2020 to 2050.
>- ###### Minimum Temperature: 
>>- A slight yet statistically significant increase in minimum temperature has been observed across regions from 2020 to 2050. This points to a trend of warmer nights and cooler seasons over time.

##### Insights:
>- ###### Long-Term Warming Trend: 
>>- The increase in mean temperature reflects a gradual warming trend in Nepal, consistent with global climate change patterns observed over the past century.
>- ###### Stable Daytime Extremes: 
>>- The lack of significant change in maximum temperatures indicates that extreme daytime heat events have not intensified dramatically over the study period.
>- ###### Rising Nighttime Temperatures: 
>>- The significant increase in minimum temperatures suggests a shift toward warmer nights, which could have cascading effects on ecosystems, human health, and agricultural practices.

##### Implications:
>- ##### Ecosystems and Biodiversity: 
>>- Warmer nights and overall rising temperatures could disrupt ecosystems, particularly in high-altitude regions, leading to shifts in species distribution and biodiversity loss.
>- ###### Agricultural Productivity: 
>>- The increase in minimum temperatures may affect crop growth cycles, particularly for temperature-sensitive crops. Farmers may need to adopt adaptive practices, such as altering planting schedules or using heat-resistant varieties.
>- ###### Human Health: 
>>- Warmer nights could exacerbate heat stress, particularly in urban areas, increasing the risk of heat-related illnesses. Public health systems must prepare for these challenges.
>- ###### Water Resources: 
>>- While maximum temperatures have not risen significantly, the overall warming trend could contribute to glacial retreat in the Himalayas, impacting long-term water availability for rivers and streams.
>- ###### Energy Demand: 
>>- Rising mean temperatures may lead to increased demand for cooling, placing additional pressure on energy infrastructure and resources.

##### Summary:
>- The temperature data from 2020 to 2050 reveals a gradual increase in mean temperature across Nepal, with a significant rise in minimum temperatures and a slight but stable increase in maximum temperatures. These trends suggest a long-term warming pattern, particularly characterized by warmer nights. The implications of these changes are far-reaching, affecting ecosystems, agriculture, human health, water resources, and energy demand. Addressing these challenges will require proactive climate adaptation strategies, sustainable resource management, and enhanced preparedness to mitigate the impacts of a warming climate. As Nepal moves further into the 21st century (2081 BS/2024 AD), these historical trends provide valuable insights for future planning and policy-making.






# The Overall/Final Summary/Conclusion from the above analysis is provided below:


=====================================================================
## Final Summary: Climate Change Impacts in Nepal (2020 to 2050 BS)
=====================================================================
>- The analysis of climate data from 2020 to 2050 BS reveals significant and concerning trends across Nepal, highlighting the country's vulnerability to climate change. These trends encompass temperature changes, precipitation shifts, glacier retreat, river flow reductions, and regional climate vulnerability. Below is a consolidated summary of the findings, insights, implications, and comprehensive conclusions:

=================
# Key Findings:
=================
----------------------------
>- ### Temperature Trends:
----------------------------
>>* Mean Temperature: A gradual but consistent increase in mean temperature has been observed nationwide, indicating a long-term warming trend.
>>* Maximum Temperature: No significant rise in extreme daytime temperatures, suggesting stable heat extremes.
>>* Minimum Temperature: A significant increase in nighttime temperatures, leading to warmer nights and cooler seasons.

--------------------------------
>- ### Precipitation Patterns:
--------------------------------
>>* Mean Precipitation: A significant decline in mean precipitation in the eastern region, historically the wettest part of Nepal.
>>* Maximum Precipitation: An increase in extreme rainfall events, particularly in the Himalayas and Terai regions.
>>* Minimum Precipitation: A redistribution of rainfall, with historically dry areas experiencing increased precipitation and wetter areas seeing declines.

------------------------
>- ### Glacier Retreat:
------------------------
>>* Accelerated glacier retreat from 2020 to 2050, with greater variability in melting rates.
>>* Strong correlation between 2020 and 2050 retreat, indicating that current trends will worsen.
>>* Geographic variability, with some regions experiencing more severe retreat than others.

-----------------------------
>- ### River Flow Reduction:
-----------------------------
>>* All major rivers, including Karnali, Mahakali, and Koshi, show reduced flow from 2020 to 2050.
>>* Karnali and Mahakali rivers experienced the highest reduction (12.5%), while Koshi maintained the highest flow overall.

------------------------------
>- ### Climate Vulnerability:
------------------------------
>>* Increasing climate vulnerability across all provinces, with Province 2 being the most vulnerable.
>>* Sudurpashchim, while the least vulnerable, still shows a significant rise in vulnerability.
>>* Greater variability in vulnerability indices, indicating uneven impacts across regions.

============
# Insights:
============
---------------------------------------------
>- ### Warming Trends and Ecological Shifts:
---------------------------------------------
>>* Rising mean and minimum temperatures are disrupting ecosystems, particularly in high-altitude regions, and affecting biodiversity.
>>* Warmer nights are impacting agricultural cycles and increasing heat stress in urban areas.

-------------------------------------
>- ### Precipitation Redistribution:
-------------------------------------
>>* The eastern region, traditionally the wettest, is experiencing a decline in precipitation, while extreme rainfall events are increasing nationwide.
>>* Shifts in minimum precipitation are altering water availability and agricultural practices.

----------------------------------------------
>- ### Glacier and Water Resource Challenges:
----------------------------------------------
>>* Accelerated glacier retreat poses significant threats to freshwater availability, heightens flood risks, and exacerbates climate change by reducing reflectivity.
>>* Reduced river flows are impacting water availability for agriculture, drinking water, and ecosystems.

-------------------------------
>- ### Regional Vulnerability:
-------------------------------
>>* Province 2 remains the most vulnerable to climate change, necessitating targeted interventions.
>>* Increasing variability in vulnerability indices highlights the need for region-specific adaptation strategies.

================
# Implications:
================
----------------------------------
>- ### Water Resource Management:
----------------------------------
>>* Declining precipitation and glacier retreat will exacerbate water scarcity, particularly in the eastern and downstream regions.
>>* Sustainable water management strategies are critical to ensure water availability for agriculture, hydropower, and domestic use.

------------------------------
>- ### Disaster Preparedness:
------------------------------
>>* Increased extreme rainfall events and glacial lake outbursts raise the risk of flooding and landslides, requiring enhanced disaster preparedness and resilient infrastructure.

-------------------------------
>- ### Agricultural Adaptation:
-------------------------------
>>* Farmers must adapt to changing precipitation patterns and warmer nights by adopting drought-resistant crops, altering planting schedules, and improving irrigation practices.

------------------------------------
>- ### Biodiversity and Ecosystems:
------------------------------------
>>* Conservation efforts must address habitat loss and species migration caused by rising temperatures and shifting precipitation patterns.

----------------------------
>- ### Policy and Planning:
----------------------------
>>* Policymakers must prioritize climate adaptation and mitigation efforts, particularly in highly vulnerable regions like Province 2.
>>* Long-term planning is essential to address the uneven impacts of climate change across provinces.

===============
# Conclusion:
===============
> The data from 2020 to 2050 BS paints a concerning picture of Nepal's climate change. Rising temperatures, shifting precipitation patterns, accelerated glacier retreat, and reduced river flows are already impacting ecosystems, water resources, agriculture, and human health. The increasing variability in climate vulnerability across provinces underscores the need for targeted and region-specific adaptation strategies.

> As Nepal moves further into the 21st century (2081 BS), these historical trends provide critical insights for future planning. As we have already expericed the impact of trend of this climate change from 2050 t0 2080. Proactive measures, including sustainable water management, disaster preparedness, agricultural adaptation, and biodiversity conservation, will be essential to mitigate the adverse effects of climate change. Policymakers, researchers, and communities must work together to build resilience and ensure a sustainable future for Nepal in the face of a rapidly changing climate.



==================
# THANK YOU!
==================