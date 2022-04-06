# Global Suicide Map
This is a global map of country-wide suicides on a per-capita basis between the years 1985 and 2015. The map lets users toggle between different map styles and generations. Explore the interactive map [here](https://tinabeee.github.io/Global_Suicide_Map/) to use the generation toggle functions and different map styles.

# Resources
- Data: this [Kaggle dataset](https://www.kaggle.com/datasets/russellyates88/suicide-rates-overview-1985-to-2016) on global suicide rates, this [GeoJSON dataset](https://github.com/Ginden/capitals) by Github user Ginden, adapted to include suicide rates and hosted via Github Pages [here](https://tinabeee.github.io/Data/capitals2.geojson)
- Software: Jupyter Notebook, Visual Studio Code 1.60.0, D3 5.5.0, Pandas, Javascript, HTML Leaflet 1.7.1, Mapbox, Github Pages

# Summary
Initial data cleaning of the Kaggle dataset in Jupyter Notebook to remove unneeded columns for visualization:

<img width="600" alt="Screen Shot 2022-04-05 at 21 14 51" src="https://user-images.githubusercontent.com/90064437/161882209-8b55a0b1-9e48-4c77-a013-ef2a9cd6f655.png">

After null value check showed no null values, I calculated the overall average suicides per country on a per-100k population basis:

<img width="600" alt="Screen Shot 2022-04-05 at 21 16 41" src="https://user-images.githubusercontent.com/90064437/161882378-de25f7de-2370-4a87-94bc-9d5131359123.png">

I then grouped the average suicides per country and per generation:

<img width="600" alt="Screen Shot 2022-04-05 at 21 17 14" src="https://user-images.githubusercontent.com/90064437/161882443-d5620f7d-1ed7-4ff4-b5da-34d759a3dba8.png">

# Visualization
The tile layer is produced via a free Mapbox account, which provides 200,000 free tile requests. The access token, or API key, used in the code is URL-restricted, meaning it does not work on any other website.

My mapping code centers the map to evenly display all continents and creates four base layers to change the style of the map:

<img width="503" alt="Screen Shot 2022-04-05 at 21 21 12" src="https://user-images.githubusercontent.com/90064437/161882951-8c921aa9-a137-4011-8549-7390c03925e7.png">

I then add a second layer for the different generation and display the new layers as a second overlay object on the map:

<img width="396" alt="Screen Shot 2022-04-05 at 21 23 00" src="https://user-images.githubusercontent.com/90064437/161883079-5aa6d158-8aca-49cc-9a0b-dbbac81991b7.png">

Using d3, I make an API request to the GeoJSON dataset I previously uploaded via Github Pages and add style functions, including color, radius size, etc. to each bubble on the map (detailed code can be found in the repo):

<img width="614" alt="Screen Shot 2022-04-05 at 21 23 35" src="https://user-images.githubusercontent.com/90064437/161883251-e5b45704-8464-4218-a700-75d0a0d7f936.png">

I then create a popup marker for each bubble on the map to display country name and suicide rate:

<img width="650" alt="Screen Shot 2022-04-05 at 21 25 38" src="https://user-images.githubusercontent.com/90064437/161883462-aaf67a34-9951-44e6-81ce-acfb9c316a4a.png">

# Findings
It quickly becomes apparent that suicide rates are particularly high among older generations and in former countries of the Soviet Union / Eastern Europe.

GI Generation / Greatest Generation (those born between 1901 and 1927):

<img width="1300" alt="Screen Shot 2022-03-28 at 11 44 31" src="https://user-images.githubusercontent.com/90064437/161883764-7e24d590-585a-4779-b927-d9767d78db19.png">

Silent Generation (b. between 1928 and 1945):

<img width="1300" alt="Screen Shot 2022-03-28 at 11 45 50" src="https://user-images.githubusercontent.com/90064437/161883830-1a245576-12fb-4166-b1d1-54e0402981e7.png">

Boomer Generation (b. between 1946 and 1964):

<img width="1300" alt="Screen Shot 2022-03-28 at 11 46 57" src="https://user-images.githubusercontent.com/90064437/161883898-060e251c-6972-45fb-a819-025c0b1dd197.png">

Gen X (b. between 1965 and 1980):

<img width="1300" alt="Screen Shot 2022-03-28 at 11 51 36" src="https://user-images.githubusercontent.com/90064437/161883962-806df611-d419-4923-858c-0bd0e1e65cd1.png">

Millennials (b. between 1981 and 1996):

<img width="1300" alt="Screen Shot 2022-03-28 at 11 53 30" src="https://user-images.githubusercontent.com/90064437/161884016-d2f50016-ef06-46f8-9997-bb26f4c11280.png">

Gen Z (b. between 1997 and 2012):

<img width="1300" alt="Screen Shot 2022-03-28 at 11 54 57" src="https://user-images.githubusercontent.com/90064437/161884046-43baeb9d-33fe-46fc-aaa2-603e155ee8ca.png">



