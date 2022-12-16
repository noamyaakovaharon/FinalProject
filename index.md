## Noam Aharon's Final Project for Command Line GIS 651

# Intersection of Industrial Facilities, Flood Hazards, and Social Vulnerability in Hillsborough County, Florida 

Industrial and commercial facilities that manage hazardous materials can become a source of toxic pollution and contamination during flooding events. Flood waters can overwhelm a facility's capacity to properly store its materials, resulting in a discharge of harmful chemicals and wastes into surrounding communities. The threat of a toxic release further exacerbates the more apparent issues that occur from large flooding events (such as power outages, critical infrastructure damage, and loss of life). Vulnerable communities in flood-prone areas situated near industrial and commercial facilities face the greatest risks associated with flood-driven toxic releases. 

Residents of Hillsborough County, in Western Florida, have been hit hard this past year by a series of hurricanes and tropical storms resulting in widescale flooding. After the storms subsided, it was discovered that much of the flood water was contaminated with a slew of toxic chemicals and materials coming from wastewater treatment plants, oil tankers, and manufacturing facilities. In order to improve the prepardness and resiliency of communities in regard to flood-driven toxic releasese, this project aims to identify facilities of concern (facilities that can discharge hazardous materials during a flood), and determine the level of threat the facilities poses to surrounding communities. The threat that a facility poses will be determined by its proximity to socially vulnerable communities (defined by the CDC's SVI) and high-risk flood zones (defined by FEMA). City planners and legislators can use this information to reinforce certain facilities of concern, and more importantly, place measures in the most at-risk areas to prevent toxic releases from becoming a humanitarian disaster. 

I will first introduce the datasets used in this project and describe the methdologies used to clean and manipulate the datasets for analysis. Static maps will be displayed throughout the data/methodology description as well as the "results/analysis" section. Lastly, I will present an interactive webmap which shows the relationship between facilities of concern and the various hazard zones identified for the analysis. While it is recommended to read through the earlier sections on this site to understand the context of the webmap, you may jump to the webmap by clicking HERE. 


<details><summary>Data Description and Methodology</summary>
<p>

1. <a href="https://www.atsdr.cdc.gov/placeandhealth/svi/interactive_map.html"> Social Vulnerability Index by Census Tract </a> - CDC, 2020. 
  
**Data Description** 
  
*What is Social Vulnerability?*
  
"Every community must prepare for and respond to hazardous events, whether a natural disaster like a tornado
or a disease outbreak, or an anthropogenic event such as a harmful chemical spill. The degree to which a
community exhibits certain social conditions, including high poverty, low percentage of vehicle access, or
crowded households, may affect that community’s ability to prevent human suffering and financial loss in the
event of disaster. These factors describe a community’s social vulnerability."

*What is CDC Social Vulnerability Index?*
  
"SVI indicates the relative vulnerability of every U.S. Census tract. SVI ranks the tracts on 15 social factors, including unemployment,
minority status, and disability, and further groups them into four related themes. Thus, each tract receives a
ranking for each Census variable and for each of the four themes, as well as an overall ranking." The scale goes from 0 to 1 (low to high social vulnerability).
 
The SVI can help determine a community's level of prepardness and resiliency to deal with a human or natural disaster. For the purposes of this analysis, I am interested in identifying the most socially vulnerable communities in Hillsborough County, Florida, to see if they are situated near facilities of concern. According to the CDC's interactive SVI map, census tracts with an overall SVI ranking of .75 and above are are considered to be areas with high social vulnerability. Census tracts with .75 SVI or higher will become one of the two hazard zones or areas that will be defined for the analysis. These hazard zones/areas are places where the harmful effects of toxic releases from facilities of concern will be exacerbated. 

**Data Cleaning and Methodology**

I downloaded a csv file of all census tracts in Florida attached to SVI data. The SVI data includes all the variables that go in to calculatiing the overall SVI ranking. Since I'm only interested in the overall SVI, I dropped most of the columns from the csv. I then filtered the dataset to Hillsborough County and joined the dataset to another dataset that includes the geometries of the census tracts in Hillsborough County. Census tracts that were located in the water were dropped from the geometry. Below is a choropleth map displaying the SVI values for every census tract in Hillsborough County. The dark blue census tracts (SVI of .75 and above) is identified as one of the two hazard layers that will be used to conduct the analysis.    

![Overall SVI](/OverallSVI.png) 
  
  2. [National Flood Hazard Layer](https://msc.fema.gov/portal/advanceSearch#searchresultsanchor) - FEMA, 2022
  
**Data Description** 
  
The National Flood Hazard Layer (NFHL_12057C) from the FEMA Flood Map Service Center is a shapefile that displays the different flood insurance zones defined by FEMA for the entire country. Flood zones are defined by how their varying levels of flood risk. High risk zones are areas where there is a 1% chance of annual flooding and a 26% chance of flooding during a 30-year period. Moderate to low risk zones are areas where the risk of flooding is reduced but not completley removed. Flood insurance is not required in these zones. Click [here](https://www.fema.gov/blog/fema-flood-maps-and-zones-explained) for a more detailed explanation of the zones. All flood zones in Hillsborough County that start with the letter "A" and "V" will be considered a high-risk flood zone and will be considered the second overall hazard zone/area used for the analysis. Below is a map displaying the different flood zones in Hillsborough county. The "X" flood zone is considered low-risk and will therefore be dropped later on to create a layer that only includes high-risk zones.
  

</p>
</details>
