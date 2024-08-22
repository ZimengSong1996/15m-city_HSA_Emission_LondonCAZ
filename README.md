# 15m-city_HSA_Emission_LondonCAZ

`Theme:` Quantifying 15-Minute City Spatial Structure: Exploring Its Influence on Transport Emissions in London's CAZ

`Statement:` this is a study of personal MSc dissertation in UCL, CASA. All contents are generate by authoer. Here we share the coding of calculating HSA and other data process and analysis. Please contact with author if you wish use the outcome for publishing purpose. Thanks.

`Abstract:` Global cities play a significant role in contributing to greenhouse gas emissions, with urban transportation serving as a primary source. Reducing transport emissions is crucial for achieving sustainable development goals. The "15-minute city" model is proved to be an effective method to reduce urban transport emissions, which seeks to transform urban areas into polycentric structures by enhancing local accessibility and modifying urban spatial patterns, thereby reducing reliance on private vehicles. However, the lack of comprehensive quantitative methods to measure the 15-minute city level hinders dynamic assessment and test the effect of reducing emissions.
To bridge this gap, we introduce a "human-scale accessibility" (HSA) indicator that evaluates the spatial efficiency of the 15-minute city concept at the street level from the perspective of spatial structure. By utilizing data from street-view images, points of interest (POIs), and spatial road networks, we focus on London's Central Activities Zone (CAZ) to examine the relationships between HSA and transmission-related socioeconomic factors, including transport emissions, car ownership, green commuting, health, and deprivation. Global and local regression models are employed to quantify these associations.
Our findings suggest that although the 15-minute city concept may not directly reduce transport emissions, it promotes the adoption of environmentally friendly travel modes. These results challenge the assumption that the 15-minute city concept is effective in lowering transport emissions. This research provides valuable insights for urban planning and policy, highlighting the complex nature of metropolitan transport emissions and supporting efforts to reduce carbon footprints in urban areas. This study presents the first quantitative examination of the relationship between the level of 15-minute city and local transport emissions. It also emphasizes the need for further research to develop comprehensive strategies for mitigating urban transportation emissions.


`Data Source`:
1. POI & Road network: https://download.geofabrik.de/europe/united-kingdom/england/greater-london.html
2. London CAZ boundary: https://data.london.gov.uk/dataset/central-activities-zone-boundary-london-plan-consultation-2009
3. LSOA boundaries (2021): https://geoportal.statistics.gov.uk/datasets/2bbaef5230694f3abae4f9145a3a9800/explore?location=51.476531%2C-0.128942%2C12.10
4. CAZ street-view images/google street-view images (API required, here is guidance page): https://developers.google.com/maps/documentation/streetview/overview
5. Place Pulse 2.0 dataset (street-view images and perceived socres for training): https://centerforcollectivelearning.org/urbanperception
6. Transport emissions: https://data.london.gov.uk/dataset/london-atmospheric-emissions-inventory--laei--2019
7. Socio-Green indicators (TS045 Car or van availability, TS061 Method of travel to work, TS037 General health, TS011 Households by deprivation dimensions): https://www.nomisweb.co.uk/sources/census_2021_bulk


The main coding file please see `15-min-city_HSA_LondonCAZ.ipynb`.
   
`Content`:

1. Perceived Streetscape quality Analysis: Built predictive model

   1.1 Process training data: Place Pulse 2.0-the imagery and perceived socre in 6 dimensions

   1.2 Imagery semantic segmentation for training imagery (Place-Pulse-2.0) and google street images of CAZ

   1.3 Building LGBoost, XGBoost and Random Forest Resgression Model \n

   1.4 Predict Perceived Quality Score in London CAZ
   
2. Processing POI
   
3. Calculate Human-Scale Accessibility (HSA)
   
   3.1 The original plan: Calculate HSA by network distance and the average perceived quality along the way on streets to POIs
   
   3.2 The Circuity factor plan: Calculate HSA by Circuity factor and the average perceived quality of streets' catchment
   
4. Regression Analysis: GLM & GWR
   
   4.1 regression analysis with transport emission
   
   4.2 Regression analysis with Socio-Green indicators



`Note`: Due to file size limit, there are 2 encode and decode files for semantic segmentation not include in the repository. Please download the files from https://liveuclac-my.sharepoint.com/my?csf=1&web=1&e=b2tkG1&CID=aba7d972%2D6d64%2D44cf%2D9d74%2D7453c052b1ae&id=%2Fpersonal%2Fucfnonb%5Fucl%5Fac%5Fuk%2FDocuments%2FAssignment%5FFinal%2Fimage%5Fdownload%5Fsegmentation%2Fsemantic%5Fsegmentation%2Fckpt%2Fade20k%2Dresnet50dilated%2Dppm%5Fdeepsup&FolderCTID=0x01200010AEA58D266F26459F8E01DF813DBA8C . Then put the files under image_download_segmentation/semantic_segmentation/ckpt/ade20k-resnet50dilated-ppm_deepsup/
