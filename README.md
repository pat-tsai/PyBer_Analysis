# PyBer_Analysis
## Overview of analysis:
- The purpose of this project was to utilize python, pandas, and matplotlib to create visualizations of ride-sharing data based on city types (rural, urban, suburban). By doing so, we are able to evaluate which sectors generate the most revenue and determine which areas may require more funding. Ultimately, creating graphical visualizations allows management to easily observe spending patterns based on region or time of year.

## Results

![ScreenShots]('/analysis/pyber_summary_df.png')
Based on the summary dataframe, we can clearly observe that urban areas have the most requested amount of rides, whereas rural areas have the least. However, rural areas have the highest average fare per ride, which can be attributed to having the lowest amount of total drivers (only 78). Suburban areas seem to generate the most value, having an average fare per driver of more than twice that of urban areas, which is largely due to having lower amounts of drivers available (490 total in suburban areas, 2405 in urban).

![ScreenShots]('/analysis/pyber_fare_summary.png')
Based on the multiple line graph, we can observe a lower amount of fare generated/demand for rides in early January. The amount made from weekly total fares made slowly increases, particularly in suburban and urban areas from the beginning of January to near the end of the month. In addition, we can note a consistent spike in fare fees in all 3 city types in the last couple weeks of February, which could be a result of school Spring breaks and general increased travelining/driver demand. From March to April, the trends remained relatively consistent except in the urban regions which had larger fluctuations of around $500 per week. Business also performs well after April, demonstrated by the high levels in the line graphs.

Although a quick glance at the visuals may suggest that urban areas are the biggest money-makers, it's important to note that a much deeper analysis could be performed to get a deeper understanding of the picture. For example, running the following code allows us to find how many cities are in this dataset contributing to each city type group: 
```
# finding the number of cities in each city type
urban_count = pyber_data_df[pyber_data_df['type']=='Urban']

rural_count = pyber_data_df[pyber_data_df['type']=='Rural']

suburban_count = pyber_data_df[pyber_data_df['type']=='Suburban']

# determining number of cities per city group within this dataset
urban_count.city.nunique(), rural_count.city.nunique(), suburban_count.city.nunique()

Output: (66, 18, 36)
```
From the above code, we realize that there are 66 cities in the urban group, 18 in rural, and 36 in suburban. In the time period from 1/1/2019 - 4/29/2019, there were 1,625 total urban rides, 125 rural, and 625 suburban respectively. It would be interesting to dive deeper and determine exactly how many rides were requested, thus determining how much fare amount was generated from each specific city within the city groups. In addition, finding out the average distance and time of day each ride was performed would add additional insight.

## Summary
- 1. Based on these results, I would advise the CEO to 
