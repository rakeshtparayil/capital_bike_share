# Capital Bike Share Project

## Project Overview
Capital Bike is a bike-sharing initiative aimed at providing a convenient and eco-friendly transportation solution. This project focuses on analyzing historical ride data to uncover insights, trends, and patterns that can help improve service efficiency and user satisfaction.

## Objectives
- **Convert casual riders to members** by demonstrating cost savings and benefits.
- **Encourage e-bike usage** by shifting 10% of classic bike casual users to e-bikes.
- **Promote the Angel program** to maximize free ride credits and optimize bike redistribution.

## Data Structure
The dataset used in this project consists of hourly ride data collected from Capital Bike's operations. The key columns in the dataset include:

- `hour`: Hour of the day (0-23)
- `season`: The season in which the ride was taken (1 = Winter, 2 = Spring, 3 = Summer, 4 = Fall)
- `casual`: Number of casual (non-member) riders
- `member`: Number of registered member riders
- `total_rides`: Total number of rides (casual + member)
- `temperature_2m_(°C)`: Temperature in degrees Celsius
- `relativehumidity_2m_(%)`: Relative humidity percentage
- `windspeed_10m_(km/h)`: Wind speed in kilometers per hour
- `weathercode_(wmo_code)`: Weather condition code based on WMO standards

## Data Transformation
Several new columns were derived to enhance the analysis:
- `weather_category`: Categorized the `weathercode_(wmo_code)` column into descriptive labels such as "Clear/Cloudy", "Fog Conditions", "Rain", etc.
- `humidity_category`: Categorized humidity levels into "Low", "Moderate", "High", and "Very High" using predefined ranges.
- `windspeed_category`: Divided wind speeds into categories such as "Calm", "Light Breeze", "Moderate Breeze", etc.

## Exploratory Data Analysis (EDA)
- Analyzing ride patterns for **casual vs. member users**.
- Identifying how **classic bike users can shift to e-bikes**.
- Evaluating the **cost differences** between casual and member rides.
- Understanding ride durations and user behavior.

## Problem Definition
- Casual riders pay more per ride compared to members.
- Classic bike casual riders have a potential shift to e-bikes.
- The Angel program is **underutilized**, reducing potential cost savings.

## Solution Framework
- **CRM Campaign Strategy** to push casual riders toward membership.
- **Incentives & Promotions** to encourage Angel program participation.
- **Targeted Messaging** (email, push notifications, in-app prompts).
- **A/B Testing & Performance Tracking** for effectiveness measurement.

## Implementation
- **Jupyter Notebook** for EDA and problem-solution modeling.
- **Data Visualizations** to support insights.
- **GitHub Documentation** for tracking progress and updates.

## Next Steps
1. **Segmentation & Data Sync**: Pull casual rider data & identify high-potential users.
2. **Campaign Content Development**: Design email templates, push notifications, and in-app pop-ups.
3. **A/B Testing & Tracking**: Monitor conversion rates (casual → member, Angel program engagement).
4. **Optimize & Scale**: Expand based on engagement and response rates.

This project will help drive user conversions, optimize ride efficiency, and improve overall revenue for the bike-sharing system.

