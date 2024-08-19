# 15m-city_HSA_Emission_LondonCAZ

`Theme:` Quantifying 15-Minute City Spatial Structure: Exploring Its Influence on Transport Emissions in London's CAZ

`Statement:` this is a study of personal MSc dissertation in UCL, CASA. All contents are generate by authoer. Here we share the coding of calculating HSA and other data process and analysis. Please contact with author if you wish use the outcome for publishing purpose. Thanks.

`Abstract:` Global cities are significant contributors to greenhouse gas emissions, with urban transportation being a primary source. Addressing these emissions is crucial for sustainable development. The "15-minute city" model seeks to transform urban areas into polycentric structures, reducing reliance on private vehicles by enhancing local accessibility and transforming urban spatial structures. This study develops a "human-scale accessibility" (HSA) indicator to evaluate the spatial efficiency of the 15-minute city concept at the street level. Utilizing data from street view images, points of interest (POIs), and spatial road networks, we focus on London's Central Activities Zone (CAZ) to assess the HSA's relationship with traffic emissions, car ownership, green commuting, health, and poverty. We use global and local regressions to build models of the relationship. Our findings indicate that while the 15-minute city concept does not directly reduce traffic emissions, it promotes green travel modes, challenging the assumption that it can effectively lower transport emissions. This research provides insights for urban planning and policy, highlighting the complex origins of metropolitan traffic emissions and supporting carbon reduction initiatives.

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
   1.3 Building LGBoost, XGBoost and Random Forest Resgression Model /n
   1.4 Predict Perceived Quality Score in London CAZ
2. Processing POI
3. Calculate Human-Scale Accessibility (HSA)
   3.1 The original plan: Calculate HSA by network distance and the average perceived quality along the way on streets to POIs
   3.2 The Circuity factor plan: Calculate HSA by Circuity factor and the average perceived quality of streets' catchment
4. Regression Analysis: GLM & GWR
   4.1 regression analysis with transport emission
   4.2 Regression analysis with Socio-Green indicators
