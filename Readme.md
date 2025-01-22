# Capital Bike Share Project

## Project Overview
Capital Bike is a bike-sharing initiative aimed at providing a convenient and eco-friendly transportation solution. This project focuses on analyzing historical ride data to uncover insights, trends, and patterns that can help improve service efficiency and user satisfaction.

## Data Structure
The dataset used in this project consists of hourly ride data collected from Capital Bike's operations. The key columns in the dataset include:

- **hour**: Hour of the day (0-23)
- **season**: The season in which the ride was taken (1 = Winter, 2 = Spring, 3 = Summer, 4 = Fall)
- **casual**: Number of casual (non-member) riders
- **member**: Number of registered member riders
- **total_rides**: Total number of rides (casual + member)
- **temperature_2m_(°C)**: Temperature in degrees Celsius
- **relativehumidity_2m_(%)**: Relative humidity percentage
- **windspeed_10m_(km/h)**: Wind speed in kilometers per hour
- **weathercode_(wmo_code)**: Weather condition code based on WMO standards

## Data Cleaning Process
To ensure the data's accuracy and reliability, the following data cleaning steps were performed:

1. **Handling Missing Values:**
   - Missing values in numerical columns such as `temperature_2m_(°C)`, `relativehumidity_2m_(%)`, and `windspeed_10m_(km/h)` were filled using the mean of the respective columns.
   - The `weathercode_(wmo_code)` column's missing values were replaced with the most frequent value.

2. **Data Type Conversion:**
   - Ensured that all columns had appropriate data types by converting numerical values to float/int and categorical columns to appropriate formats.

3. **Removing Duplicates:**
   - Checked for and removed any duplicate records that might have appeared in the dataset.

4. **Handling Outliers:**
   - Identified and handled extreme outliers using interquartile range (IQR) and replaced them with median values where necessary.

## Data Transformation
Several new columns were derived to enhance the analysis:

- **weather_category:** Categorized the `weathercode_(wmo_code)` column into descriptive labels such as "Clear/Cloudy", "Fog Conditions", "Rain", etc.
- **humidity_category:** Categorized humidity levels into "Low", "Moderate", "High", and "Very High" using predefined ranges.
- **windspeed_category:** Divided wind speeds into categories such as "Calm", "Light Breeze", "Moderate Breeze", etc.

## Exploratory Data Analysis (EDA)
EDA was conducted to uncover patterns and insights in the bike-sharing data. The following analyses were performed:

1. **Descriptive Statistics:**
   - Mean, median, and distribution of total rides across hours and seasons.

2. **Correlation Analysis:**
   - Examined relationships between ride counts and weather factors (temperature, humidity, wind speed).

3. **Ride Distribution Analysis:**
   - Analysis of casual vs. member ride patterns across hours and seasons.

4. **Trend Analysis:**
   - Trends over days and seasonal changes in demand.

## Data Visualization
Various visualizations were created to better understand the data:

1. **Hourly Ride Patterns:**
   - Line charts showing ride trends by hour for casual and member riders.
   ```python
   plt.figure(figsize=(10, 6))
   sns.lineplot(x='hour', y='casual', data=bike_hourly_new, label='casual', color='blue')
   sns.lineplot(x='hour', y='member', data=bike_hourly_new, label='member', color='red')
   plt.xticks(sorted(bike_hourly_new['hour'].unique()))
   plt.title('Casual and Member Rides by Hour')
   plt.xlabel('Hour')
   plt.ylabel('Total Rides')
   plt.tight_layout()
   plt.show()
   ```

2. **Seasonal Ride Patterns:**
   - Bar charts comparing casual and member rides across different seasons.
   ```python
   df_melted = bike_hourly_new.melt(id_vars=['season'], value_vars=['casual', 'member'],
                                   var_name='Rider Type', value_name='Total Rides')
   plt.figure(figsize=(10, 6))
   sns.barplot(x='season', y='Total Rides', hue='Rider Type', data=df_melted, palette=['blue', 'red'])
   plt.title('Casual and Member Rides by Season')
   plt.xlabel('Season')
   plt.ylabel('Total Rides')
   plt.tight_layout()
   plt.show()
   ```

3. **Correlation Heatmap:**
   - Heatmaps to visualize correlations between ride counts and weather parameters.
   ```python
   correlation_matrix = bike_hourly_new[['casual', 'member', 'total_rides', 'temperature_2m_(°C)', 'relativehumidity_2m_(%)', 'windspeed_10m_(km/h)']].corr()
   plt.figure(figsize=(8, 6))
   sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', fmt='.2f')
   plt.title('Correlation Matrix')
   plt.show()
   ```

## Conclusion
Through data cleaning, transformation, and analysis, key insights were derived to better understand the riding patterns of Capital Bike users. Weather conditions, seasons, and hourly trends significantly influence the number of casual and member rides.

## Future Work
Future improvements to this analysis could include:
- Incorporating external factors such as events and traffic data.
- Developing machine learning models to predict ride demand.
- Conducting user segmentation for personalized marketing.

---

This README provides an overview of the Capital Bike share project and the steps undertaken to analyze the data effectively.

