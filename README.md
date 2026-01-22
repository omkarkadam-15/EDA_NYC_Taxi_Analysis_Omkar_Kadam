# EDA_NYC_Taxi_Analysis_Omkar_Kadam
This project presents an end-to-end Exploratory Data Analysis (EDA) of the New York City Yellow Taxi trip dataset, focused on uncovering travel patterns, revenue trends, passenger behavior, zone-wise activity, and operational inefficiencies. The goal is to extract actionable insights that can guide taxi fleet optimization, pricing improvements, and strategic planning.

## Project Objectives

* Clean and prepare large-scale taxi trip data.
* Perform stratified hourly sampling to ensure temporal representativeness.
* Explore patterns in trips, revenue, distances, speeds, and demand cycles.
* Conduct geospatial analysis using NYC Taxi Zone shapefiles.
* Identify high-demand zones, busy hours, slow routes, and seasonal trends.
* Provide data-driven recommendations for routing, dispatching, and pricing.

## Dataset

* Source: NYC Yellow Taxi trip records (monthly parquet files).
* Sampling Method: Stratified hourly sampling (0.008%) to generate a ~300K record dataset while preserving hour-wise and day-wise patterns.
* Geospatial Data: NYC Taxi Zones shapefile used for mapping pickup/dropoff activity.

## Data Preparation & Cleaning

### Key steps include:
* Dropping irrelevant/duplicate columns (Unnamed: 0, store_and_fwd_flag, mta_tax).
* Merging duplicate airport fee columns.
* Imputing missing values for passenger count, RatecodeID, congestion surcharge, airport fee.
* Removing invalid trip entries: negative fares, unrealistic distances, invalid payment types, and zero-distance mismatches.
* Creating new features such as trip_duration, pickup_hour, and distance tiers.

## Exploratory Data Analysis (EDA)
1. Demand Trends
* Busiest hours: 5 PM – 7 PM (peak at 6 PM).
* Weekdays show strong commuter patterns; weekends peak later.
* Highest activity months: May, October; lowest: February, August.

2. Revenue Insights

* Annual revenue (sample scaled): ~$6.67M.
* Q2 and Q4 have the highest revenue contributions.

3. Trip & Fare Relationships

* Distance and fare show strong positive correlation (0.94).
* Duration and fare have moderate correlation (0.29).
* Longer trips generally attract higher tips.

4. Geospatial Analysis

Top pickup zones:

JFK Airport,Upper East Side (North/South),Midtown Center,LaGuardia Airport.
Areas with minimal activity include Broad Channel, Stapleton, West Brighton, and other peripheral zones.

5. Passenger & Tip Behavior

* Passenger count peaks during evenings and weekends.
* Tip percentage decreases for long trips.
* Credit card payments dominate; cash trips show lower tips.

6. Surcharges & Vendor Comparison

* Congestion surcharge applied to 83% of trips.
* Vendor 2 consistently charges slightly higher fare per mile across tiers.

## Key Insights & Recommendations
### Operational Optimization
* Deploy more taxis in high-demand areas during peak hours.
* Use route-speed trends to avoid consistently slow routes.
* Reposition empty taxis toward high pickup-ratio zones.

### Demand-Based Strategy
* Weekday: Focus on business districts and residential hubs.
* Weekend nights: Allocate taxis to entertainment zones (East/West Village).
* Maintain strong coverage at JFK and LaGuardia.

### Pricing Adjustments
* Offer competitive fares during low-revenue months (July–September).
* Reassess fare-per-mile structure for different distance tiers.
* Introduce incentives that improve tip behavior, especially for cash trips.
  
## Technologies Used
* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* GeoPandas
* PySpark (optional depending on workflow)
* Jupyter Notebook
