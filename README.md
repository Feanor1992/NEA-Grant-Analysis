# NEA-Grant-Analysis #

## Code Overview ##
1. **Importing Libraries and Loading Data**
    - ***Libraries:*** The code utilizes several libraries:
        - `pandas`: For data manipulation and cleaning.
        - `plotly.express`: For creating interactive visualizations.
        - `dash`: For building an interactive web application.
        - `dash_ag_grid`: For creating an interactive table grid.
        - `geopy`: For geocoding to convert hometown names to geographic coordinates.
    - ***Data Loading:*** The dataset is loaded from a CSV file (`Post45_NEAData_Final.csv`) into a Pandas DataFrame (`df`).
2. **Data Cleaning and Transformation**
    - ***Handling Missing Values:*** The dataset is cleaned by filling missing values:
        - `birth_year`: Filled with the median birth year.
        - `state` and `hometown`: Filled with the string 'Unknown'.
    - ***Feature Creation:***
        - A new column, `age of writer`, is created by subtracting the birth year from the year the grant was awarded.
        - The `age_group` column categorizes writers into age groups based on their age at the time of the grant.
    - ***State and Hometown Analysis:***
        - The count of grants by state is calculated and stored in `grants_by_state`.
        - The count of writers by hometown is calculated and stored in `writers_by_hometown`.
    - ***Geocoding Hometowns:*** The `geopy` library is used to add `latitude` and `longitude` data for each writer's hometown, enabling map visualization of hometowns.
    - ***University Count:*** A new feature, `university_count`, is created, indicating the number of universities each writer attended based on various columns.
3. **Exploratory Data Analysis (EDA)**
    - ***Grants by State and Hometown:***
        - The `grants_by_state` DataFrame counts the number of grants awarded by U.S. state.
        - The `writers_by_hometown` DataFrame counts the number of writers from each hometown.
    - ***Grants and Writers by Year:*** The total count of grants per year is calculated and stored in `grants_per_year`.
    - ***University Count Analysis:*** The dataset is analyzed for the relationship between the number of universities a writer attended and the number of grants awarded.
4. **Data Visualization**
    - ***Writer Age Distribution:*** A histogram visualizes the distribution of writers' ages at the time of the grant, colored by age group.
    - ***Age Group Distribution:*** A pie chart visualizes the distribution of writers across different age groups.
    - ***University Count Distribution:*** A histogram is created to show the distribution of the number of universities attended by writers.
    - ***University Count vs. Grant Count:*** A bar chart is created to visualize the relationship between the number of universities attended and the number of grants awarded.
    - ***Grants by State:*** A choropleth map visualizes the number of grants awarded by state, with colors representing grant count.
    - ***Writers by Hometown (Bar Chart):*** A bar chart shows the top 10 hometowns based on writer count.
    - ***Writers by Hometown (Map):*** A scatter map visualizes the geographical distribution of writers' hometowns.
    - ***Grants per Year:*** A line chart visualizes the trend of grant counts over time.
5. **Dashboard Creation with Dash**
    - ***Interactive Grid:** A data grid is created using `dash_ag_grid` to display the dataset interactively, allowing pagination.
    - ***Interactive Visualizations:*** Several graphs are created using `dcc.Graph`, representing the visualizations mentioned above.
    - ***App Layout:*** The Dash app layout includes the data grid and all the visualizations, enabling users to explore the data dynamically through a web-based interface.
    - ***Running the App:*** The Dash app is set to run in debug mode, serving the interactive dashboard to the user through a local web server.
