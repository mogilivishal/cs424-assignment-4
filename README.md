# CS424: Visualization and Visual Analytics - Assignment - 4
# Chicago Traffic Tracker Dataset

## Clear description of the dataset
The Chicago Traffic Tracker dataset is a comprehensive collection of historical estimated congestion data for over 1,000 traffic segments in Chicago, starting from around March 2018 to present .
This dataset is a significant resource for understanding traffic conditions in the city's arterial streets and consists of a vast amount of data with 275 million rows and 22 columns of attributes.
The congestion estimates are usually generated every 10 minutes by continuously monitoring and analyzing GPS traces received from Chicago Transit Authority (CTA) buses.

It offers a wide range of details, including segment length, estimated traffic speed, street names, traffic flow direction, and several other parameters. These are helpful for a wide range of applications, including traffic management, urban planning, transportation research, and public transit optimization. It also provides congestion estimations at both the segment and regional levels. Researchers, municipal planners, traffic engineers, and transportation businesses can use the information to acquire understanding of Chicago's traffic patterns and make data-driven choices to enhance traffic flow and urban mobility.

**a. Columns in the Dataset:**
The dataset contains 22 columns:

1. **TIME**: Represents date and time.
2. **SEGMENT_ID**: A unique identifier for each traffic segment.
3. **SPEED**: Estimated traffic speed in miles per hour.
4. **STREET**: Street name of the traffic segment.
5. **DIRECTION**: Traffic flow direction for the segment.
6. **FROM_STREET**: Start street for the segment in the direction of traffic flow.
7. **TO_STREET**: End street for the segment in the direction of traffic flow.
8. **LENGTH**: Length of the segment in miles.
9. **STREET_HEADING**: The position of the segment in the address grid.
10. **COMMENTS**: Plain text comments.
11. **BUS_COUNT**: Number of buses providing a GPS feed used to estimate congestion.
12. **MESSAGE_COUNT**: Number of GPS probes received (or used) for estimating the speed for that segment.
13. **HOUR**: Hour of the day.
14. **DAY_OF_WEEK**: Day of the week (Sunday = 1).
15. **MONTH**: Month of the year.
16. **RECORD_ID**: A unique identifier for each record in the dataset.
17. **START_LATITUDE**: Latitude of the start of the segment.
18. **START_LONGITUDE**: Longitude of the start of the segment.
19. **END_LATITUDE**: Latitude of the end of the segment.
20. **END_LONGITUDE**: Longitude of the end of the segment.
21. **START_LOCATION**: Location of the start of the segment.
22. **END_LOCATION**: Location of the end of the segment.

**b. Spatial or Temporal Component:**
- **Spatial Component**: The dataset also includes information related to the streets (STREET, DIRECTION, FROM_STREET, TO_STREET) and geographical coordinates (latitude and longitude) for the start and end points of the segments. This gives us information about a spatial component related to the location of traffic segments in the city.

- **Temporal Component**: The dataset contains temporal information, including date and time (TIME), hour of the day (HOUR), day of the week (DAY_OF_WEEK), and month (MONTH). These temporal components gives us information about a time series aspect to the data.

**c. Categorical and Numerical Columns:**
- **Categorical Columns**: Columns with categorical data include STREET, DIRECTION, FROM_STREET, TO_STREET, STREET_HEADING, COMMENTS, and START_LOCATION/END_LOCATION.
- **Numerical Columns**: Columns with numerical data include SEGMENT_ID, SPEED, LENGTH, BUS_COUNT, MESSAGE_COUNT, HOUR, DAY_OF_WEEK, MONTH, START_LATITUDE, START_LONGITUDE, END_LATITUDE, and END_LONGITUDE.

**d. Specific Focus for Multiple Categories:**
Based on our visualizations we're specifically focusing on categories like HOUR, DAY_OF_WEEK, SPEED, STREET, BUS_COUNT, DIRECTION, LENGTH, MONTH, SEGMENT_ID and LENGTH.

**e. Spatial and Temporal Coverage:**
- **Spatial Coverage**: The data represents traffic segments in Chicago, and the spatial coverage extends to the entire city.
- **Temporal Coverage**: The dataset starts from March 2018 to present. It covers traffic congestion data for multiple years.

**f. Percentage of Missing Values:**
The total percentage of missing values in the dataset is 87.87%

The dataset is an important resource for understanding traffic congestion in Chicago and can help in data-driven decision-making for traffic management and urban planning.

This dataset has records for both Traffic Segments and Traffic Regions. Traffic Segments provide observed speeds for specific segments of streets, while Traffic Regions offer average traffic conditions for larger areas of the city with similar traffic patterns. Traffic congestion can vary widely due to factors like intersections, traffic signals, transit movements, alternative routes, and crashes, leading to fluctuations in speed on individual arterial segments. This dataset for us acts as an important tool for monitoring and managing traffic in Chicago's arterial streets.

## Domain questions

#### 1. How does congestion vary by time of day and day of the week?
This question would help us understand the daily and weekly traffic patterns in Chicago. Visualizing the average traffic speed (attribute: SPEED) by hour of the day (attribute: HOUR) and day of the week (attribute: DAY_OF_WEEK) could reveal peak congestion times and highlight differences between weekdays and weekends.

#### 2. Which arterial streets experience the worst congestion?
By visualizing the congestion levels on different arterial streets (attribute: STREET), we can identify which streets consistently have the highest congestion rates. This information can be valuable for city planners and commuters seeking alternative routes.

#### 3. What is the impact of bus count on congestion?
Investigating the relationship between the number of buses providing GPS data (attribute: BUS_COUNT) and congestion levels (attribute: SPEED) through visualization can help determine if there's a correlation. It could shed light on how public transit affects traffic flow.

#### 4. What role does the weather play in congestion during Winters and Summers? Are there any trends in different months?
Exploring congestion patterns during Winters and Summers (attribute: MONTH) can reveal any seasonal variations in traffic. Visualizations can show weather conditions, impact congestion levels (attribute: STREET), helping with traffic management and event planning.

#### 5. Are there specific traffic segments that consistently experience high or low congestion? 
Heatmaps based on historical congestion data can pinpoint segments with persistent traffic problems, which can be crucial for identifying areas requiring road network improvements (attributes: SEGMENT_ID, SPEED).

#### 6. What is the relationship between segment length (attribute: LENGTH) and traffic congestion? 
By visualizing congestion levels against the length of traffic segments, it's possible to determine if there is a correlation between the physical length of a road segment and the likelihood of congestion. This can inform decisions about road design, lane expansions, or traffic signal optimization for specific segment types based on their lengths.

#### 7. How did the COVID-19 affect the traffic patterns in the city of Chicago?
By Visualizing traffic patterns in the years 2019-2020 and 2021-2022. We can determine the traffic congestion levels across different areas of Chicago. We can use a Choropleth map that displays traffic patterns across different areas of Chicago. (attributes: TIME, STREET, SPEED).


## Data Transformations, Encodings, Interactions, and Initial Findings for Visualizations

### Single View Visualizations

#### 1. Line Chart

<img width="630" alt="1" src="https://github.com/user-attachments/assets/bc0bd862-c052-41cc-b322-ce72d9926bce">


- **Data Transformation**: Grouping and averaging speeds for each hour.
- **Encodings**: 
  - X-Axis: HOUR (Ordinal)
  - Y-Axis: Average SPEED (Quantitative)
- **Initial Findings**: Reveals daily traffic speed trends, potentially showing peak and off-peak hours.

#### 2. Bar Chart

<img width="630" alt="2" src="https://github.com/user-attachments/assets/e864257a-8d83-4db7-99d9-758717fffcac">


- **Data Transformation**: Sorting streets by average speed to identify the top 10 congested.
- **Encodings**: 
  - X-Axis: Average SPEED (Quantitative)
  - Y-Axis: STREET (Nominal)
- **Initial Findings**: Highlights the most congested streets, useful for identifying traffic hotspots.

#### 3. Bubble Chart

<img width="630" alt="3" src="https://github.com/user-attachments/assets/ee83d618-dc5e-49a3-8de9-b36cb805e50c">


- **Data Transformation**: Correlating bus count with average speed and segment length.
- **Encodings**: 
  - X-Axis: BUS_COUNT (Quantitative)
  - Y-Axis: Average SPEED (Quantitative)
  - Bubble Size: LENGTH (Quantitative)
- **Initial Findings**: Shows the relationship between public transport frequency, traffic speed, and road segment length.

#### 4. Box Plot

<img width="630" alt="4" src="https://github.com/user-attachments/assets/0a9767d1-d0c0-4487-ae6c-43fcf6390923">


- **Data Transformation**: Grouping speeds by month to observe variations.
- **Encodings**: 
  - X-Axis: MONTH (Categorical)
  - Y-Axis: SPEED (Quantitative)
  - Color: MONTH (Quantitative)
- **Initial Findings**: Identifies seasonal traffic patterns and anomalies in speed data.

#### 5. Scatter Plot

<img width="630" alt="5" src="https://github.com/user-attachments/assets/13891854-633a-4ff6-83f4-04848061c90e">


- **Data Transformation**: Plotting segment length against speed to identify correlations.
- **Encodings**: 
  - X-Axis: LENGTH (Quantitative)
  - Y-Axis: SPEED (Quantitative)
- **Initial Findings**: Indicates potential relationships between road segment length and traffic speed.

#### 6. Heatmap

<img width="630" alt="6" src="https://github.com/user-attachments/assets/c076373f-d147-42f9-a2b0-cf2a0ef6311f">


- **Data Transformation**: Grouping congestion levels by time and day.
- **Encodings**: 
  - X-Axis: DAY_OF_WEEK (Ordinal)
  - Y-Axis: HOUR (Ordinal)
  - Color: Congestion level (Quantitative)
- **Initial Findings**: Reveals congestion patterns across different times and days, useful for identifying rush hours.

### Linked View Visualizations

#### 1. Interactive Street Speed Visualization

<img width="725" alt="l1" src="https://github.com/user-attachments/assets/c078ef82-c194-4423-a4ed-0f0fbc0a2087">


- **Encodings**: 
  - X-Axis: STREET (Nominal)
  - Y-Axis: Average Speed (SPEED) (Quantitative)
  - Color: Interactive selection
  - Opacity: Interactive response to hover
- **Interaction involved**: Tooltip and selection mechanisms for exploring individual streets.
- **Data Transformation**: Facilitates comparison of average speed across different streets.
- **Initial Findings**: Provides insights into street-specific speed patterns and helps identify streets with unusual traffic behavior.

#### 2. Linked Line Chart and Bubble Chart

<img width="725" alt="l2" src="https://github.com/user-attachments/assets/329117db-a983-422d-b773-95f5e9146c1d">


- **Encodings**: 
  - **Line Chart**: 
    - X-Axis: HOUR (Ordinal)
    - Y-Axis: Average Speed (SPEED) (Quantitative)
    - Color: STREET (Nominal, with a distinct color for each street)
    - Opacity: Interactive response to hovering
  - **Bubble Chart**: 
    - X-Axis: STREET (Nominal)
    - Y-Axis: BUS_COUNT (Quantitative)
    - Bubble Size: Corresponding to data point value
    - Color: STREET (Nominal, matching line chart color scheme)
    - Opacity: Interactive response to hovering
- **Interaction involved**: Hovering changes opacity to emphasize selected streets.
- **Data Transformation**: Allows users to compare bus count and speed over hours for different streets.
- **Initial Findings**: Offers insights into how bus frequency and traffic speed vary over time and across streets.

#### 3. Linked Scatter Plot and Histogram

<img width="541" alt="l3" src="https://github.com/user-attachments/assets/b7c50bad-aa74-42e6-9c00-6f60dd7b970e">


- **Encodings**: 
  - **Scatter Plot**: 
    - X-Axis: SPEED (Quantitative)
    - Y-Axis: BUS_COUNT (Quantitative)
    - Color: SPEED (Quantitative, color scale)
    - Size: MESSAGE_COUNT (Quantitative)
  - **Histogram**: 
    - X-Axis: SPEED Binned (Quantitative, grouped into bins)
    - Y-Axis: Count (Quantitative, number of data points in each bin)
    - Color: Steelblue (constant)
- **Interaction involved**: Selection in scatter plot filters and updates histogram.
- **Data Transformation**: Enables detailed analysis of speed distributions for specific data subsets.
- **Initial Findings**: Reveals correlations and patterns between bus count, message count, and speed.

#### 4. Linked Line Chart and Heatmap

<img width="541" alt="l4" src="https://github.com/user-attachments/assets/8dca178b-fa10-4e86-84ca-8de5867175d8">


- **Encodings**: 
  - **Line Chart**: 
    - X-Axis: TIME (Temporal)
    - Y-Axis: SPEED (Quantitative)
    - Color: STREET (Nominal, option to select multiple streets)
  - **Heatmap**: 
    - X-Axis: HOUR (Ordinal, binned)
    - Y-Axis: DAY_OF_WEEK (Ordinal)
    - Color: Average Speed (SPEED) (Quantitative, color scale)
- **Interaction involved**: Street selection in line chart dynamically updates heatmap.
- **Data Transformation**: Analyzes speed variations over time and across different street segments.
- **Initial Findings**: Highlights how speed patterns change across days and hours for selected streets.

#### 5. Linked Bar Chart and Bubble Chart

<img width="541" alt="l5" src="https://github.com/user-attachments/assets/5af9c813-e641-4791-9043-e0c1071c5386">


- **Encodings**: 
  - **Bar Chart**: 
    - X-Axis: STREET (Nominal)
    - Y-Axis: Average congestion (SPEED) (Quantitative)
    - Color: Highlights selected streets
  - **Bubble Chart**: 
    - X-Axis: Bus count (BUS_COUNT) (Quantitative)
    - Y-Axis: Congestion level (SPEED) (Quantitative)
    - Bubble Size: Segment length (LENGTH) (Quantitative)
    - Color: Segment length (LENGTH) (Quantitative, color-coded scale)
- **Interaction involved**: Selection of streets in bar chart updates bubble chart.
- **Data Transformation**: Analyzes how congestion levels correlate with bus count and segment lengths in selected streets.
- **Initial Findings**: Assists in understanding the factors contributing to congestion on specific streets.

### New Multiple Linked View Visualization

<img width="1512" alt="mlv" src="https://github.com/user-attachments/assets/d2d739ef-89b9-4063-b93e-f8288c94f43a">


This new visualization involves a combination of a bar chart and scatter plot, linked through a dropdown selector with attributes Speed, Length and Bus Count for interactive exploration of street data.

#### Data Transformations
- **Data Source**: The visualization uses a predefined data array containing attributes like SPEED, LENGTH, BUS_COUNT, etc., for various streets.
- **Dynamically binding the data**: Based on user selection from the dropdown, the data for the visualizations is dynamically bound to the selected attribute (SPEED, LENGTH, or BUS_COUNT).

#### Encodings

1. **Bar Chart**
   - X-Axis: STREET (Ordinal) - Representing different streets.
   - Y-Axis: Dynamically set based on the selected attribute (Quantitative) - Could be SPEED, LENGTH, or BUS_COUNT.
   - Color: STREET (Nominal) - Provides a visual distinction between different streets.

2. **Scatter Plot**
   - X-Axis: STREET (Ordinal) - Similar to the bar chart for consistency.
   - Y-Axis: Same as the bar chart, dynamically set based on the selected attribute.
   - Color: STREET (Nominal) - To maintain consistency with the bar chart and facilitate comparison.

#### Interactions

- **Dropdown Selection**:  We've created a HTML Dropdown element to allow the user to select an attribute to visualize (SPEED, LENGTH, BUS_COUNT). This interactivity allows the user to explore different aspects of the street data.
- **Update Function**: We've used an update function so that when a new attribute is selected, the `updateCharts` function dynamically updates both the bar chart and scatter plot to reflect the selected attribute.
- **EventListener**:  We've used the `change` event listener on the dropdown triggers the update of the visualizations upon user selection.

#### Initial Findings

- **Data exploration via dropdown options**:  We've given the ability to switch between different attributes for visualization using dropdown that offers flexibility and depth in data exploration.
- **Comparative Analysis**: The side-by-side layout of the bar chart and scatter plot with dropdown above them allows for easy comparison and analysis of the same data under different visual forms.
- **Street-Specific Trends**: This visualization setup can reveal street-specific trends and patterns for different attributes, like which streets have higher bus counts, longer lengths, or higher/lower speeds.

### Spatial Visualization

<img width="436" alt="spa" src="https://github.com/user-attachments/assets/dc824c50-cd5e-49c8-b29d-31c09a1f9d2a">


This spatial visualization is combination of choropleth map, line chart and heatmap.

- **Choropleth Map:**
  - **Encodings**: 
    - Color Fill: Represents congestion levels. The color intensity (e.g., shades of blue) indicates the level of congestion (speed) on each street segment.
    - Tooltip: Provides detailed information when hovering over a street segment. Displays street name and congestion level.
  - **Interaction involved**: Allows users to select or hover over street segments to view specific congestion data.
  - **Data Transformation**: Visualizes the geographical distribution of traffic congestion, enabling spatial analysis of traffic patterns.

- **Line Chart:**
  - **Encodings**: 
    - X-Axis: TIME (Temporal)
    - Y-Axis: Average congestion (SPEED) (Quantitative)
    - Color: Different streets are color-coded for distinction. Selected streets are highlighted, while others are displayed in a greyed out tone.
    - Tooltip: Shows detailed information (street name, time, and speed) when hovering over a line.
  - **Interaction involved**: Selection of specific streets or timeframes, with the line chart dynamically updating to reflect the selected data.
  - **Data Transformation**: Provides a temporal view of congestion levels, complementing the spatial data from the map.

- **Heatmap:**
  - **Encodings**: 
    - X-Axis: HOUR (Ordinal, binned)
    - Y-Axis: DAY_OF_WEEK (Ordinal)
    - Color: Represents average congestion speed using a color scale (e.g., viridis). The intensity of the color correlates with the level of congestion.
    - Tooltip: Offers additional information on hour, day of the week, and average congestion speed upon hovering.
  - **Interaction involved**: Dynamically updates based on selections made in the choropleth map and line chart.
  - **Data Transformation**: Showcases congestion patterns across different days and hours, providing a detailed temporal breakdown of traffic conditions.
 

## Image of All Visualizations:

![collective](https://github.com/user-attachments/assets/9afcc79d-0ea7-43aa-8553-f0091fba246d)


### Link to visualizations website hosted on GitHub Pages : https://vishalgoudmogili.github.io/ 


## Task 7: UTK

### Steps to create new visualizations using UTK (Urban Toolkit):

### 1. **Environment Setup**
   - **Install UTK**: If not already installed, set up UTK on your machine. You might need Python 3.9 or newer, and additional dependencies like CMake on macOS.
   - **Initialize Project**: Create a new directory for your project and set up a Python environment if necessary.

### 2. **Data Preprocessing and Preparation**
   - **Collection of Data**: Collect the spatial data you plan to visualize. This could include geographic features, urban infrastructure, or any other spatially-referenced datasets.
   - **Format Data**: Ensure your data is in a format compatible with UTK, likely GeoJSON, or similar spatial data formats. Preprocess your data if necessary.

### 3. **Create a UTK Project**
   - **Start UTK Services**: Use the command `utk start` in your project directory to initialize the UTK environment.
   - **Create a Data Folder**: Make a directory (e.g., `data/my_visualization`) where you will store your spatial data files.

### 4. **Define the Visualization Grammar**
   - **Create `grammar.json` File**: This file will define the structure and components of your visualization.
   - **Define Components**: Specify the elements of your dashboard, including maps, plots, and widgets.
   - **Configure Grid System**: Set up the grid to position your components on the dashboard.
   - **Map Component**: Define the settings for the map view, including camera position, knots (data bindings), and interactions.
   - **Knots**: Describe how data is loaded and linked. Each knot corresponds to a layer or aspect of your data.
   - **Plots**: If applicable, include Vega-Lite specifications for any additional plots or charts.
   - **Widgets**: Add interactive elements like toggles or search bars as needed.

### 5. **Loading and Linking Data**
   - **Define Data Layers**: Each layer of data (e.g., roads, buildings, parks) should be defined and linked to the corresponding knots in your `grammar.json`.
   - **Spatial Data Handling**: Use UTK’s functionality to manipulate and integrate spatial data as required by your visualization.

### 6. **Interactivity and Functionality**
   - **Add Interactive Elements**: If your visualization requires user interaction, define the necessary parameters and link them to your map and plots.
   - **Customize Behavior**: Adjust settings for user interactions, like zooming, panning, or selecting elements.

### 7. **Testing and Iteration**
   - **Run and Test**: Start the UTK server to view your visualization. Test it thoroughly to ensure all components are working as expected.
   - **Iterate**: Make necessary adjustments to improve the visualization, fix bugs, or add new features.

### 8. **Finalizing**
   - **Final Checks**: Do a final review of your visualization. Ensure that it meets all your requirements and functions correctly on different devices if necessary.
   - **Documentation**: Document your project, including how to use the visualization and any important information about the data or tools used.


### Error encountered while setting up UTK environment:

- While trying to install utk on macOS we were getting error related to failed building wheel for osmium, then we tried install utk of downgraded versions like 0.8.2, 0.8.3, 0.8.6, 0.8.7, but we were still facing the same error:

<img width="1512" alt="e1" src="https://github.com/user-attachments/assets/7bd7771b-156d-46a9-ada3-c01dc7a4445d">


<img width="1512" alt="e2" src="https://github.com/user-attachments/assets/058d6730-87d5-497a-a4d9-01b031963ec5">


<img width="1512" alt="e3" src="https://github.com/user-attachments/assets/aef88174-214d-460e-b5d0-f2b96a6604d3">


<img width="1512" alt="e4" src="https://github.com/user-attachments/assets/8c5ed830-dd06-47d6-9b08-c210918a7b7b">


<img width="1512" alt="e5" src="https://github.com/user-attachments/assets/97499ea3-cae0-4810-b018-9538bcb972cb">


- We then tried to install utk on windows machine and it got installed successfully but then again we were getting another error while downloading layers from OSM like below:
  

![ew](https://github.com/user-attachments/assets/43548098-76bd-447c-90db-b90e88c9eb1a)







