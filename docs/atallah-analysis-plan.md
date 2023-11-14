Author: Andy Atallah

Original study:

In the original study, Kang et al. (2020) map accessibility to medical resources (beds and ventilators at hospitals) for those at risk of contracting COVID-19 (over 55 years of age) and COVID-19 patients in Chicago, Illinois. The authors overlay a hexagonal grid on the city and perform enhanced two-step floating catchment analysis to weight different areas by their travel time to the nearest hospital. For a given hospital, there are three catchment areas based upon travel time: 0-10, 10-20, and 20-30 minutes away. To calculate travel time, the authors need to load a road network which considers the speed limits for roads within the city. Accessibility is eventually calculated on the hexagon grid. For their catchment analysis, Kang et al. do not consider any hexagons which have under 50% of their area overlapping a catchment area. Some hexagons are thus dropped from the analysis which could be considered under area weighted reaggregation, whereby the hexagons would be weighted by the percentage of their area which is overlapped by the catchment areas.

Planned modifications:

- We wish to replace the entirety of the network_setting function with the osmnx_speed function when working with speed limits. We would like to make this change so that the imputed speed limit value is based on the mean speed limit of other observations of the type of road/highway instead of remaining fixed at 35 mph, as in the original study. 
- We also wish to change the workflow to involve area-weighted reaggregation with the overlap of hexagons and hospital catchment areas, for we would like to retain the polygons which have under 50% of their area overlapping a catchment area.

Plan for interpretation:

- For speed limits, we can compare a printed list of the number of edges with each speed limit.
- For both changes, we can see if the ultimate output, the accessibility map, changes
