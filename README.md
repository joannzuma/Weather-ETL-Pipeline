# Weather ETL Pipeline

## Project Overview
This project implements a basic ETL (Extract, Transform, Load) pipeline that retrieves real-time weather data for three Kenyan cities: Nairobi, Mombasa and Kisumu using the OpenWeather API. The pipeline extracts raw weather data, transforms it into a clean structured dataset using Pandas, stores it as a CSV file and performs basic analysis with visualizations comparing temperature, humidity and weather conditions across the three cities.

## Data Source
- **API:** OpenWeather API (https://openweathermap.org/api)
- **Endpoint used:** Current Weather Data endpoint
- **Cities covered:** Nairobi, Mombasa, Kisumu
- **Fields retrieved:** City Name, Temperature, Humidity, Weather Condition, Wind Speed, Date and Time

## ETL Process

### Extract
- Connected to the OpenWeather API using my securely stored API key (loaded via a `.env` file).
- Sent GET requests for each city using the requests library.
- Retrieved raw JSON weather data for all 3 cities.

### Transform
- Examined the nested JSON response to extract only the required fields.
- Organized the extracted fields into a Pandas DataFrame.
- Renamed columns for clarity (e.g. `temp` → `Temperature_C`, `humidity` → `Humidity_%`).
- Converted the `Date_Time` field from Unix timestamp format into a human readable datetime format.

### Load
- Saved the final cleaned dataset to a CSV file (`weather_data.csv`) using Pandas' `to_csv()` function.

## Tools Used
- Python
- Pandas
- Requests
- Matplotlib (for visualizations)
- Jupyter Notebook

## Steps Taken
1. Created a free OpenWeather account and generated an API key.
2. Stored the API key securely using a `.env` file.
3. Extracted real-time weather data for Nairobi, Mombasa and Kisumu using the OpenWeather API.
4. Cleaned and transformed the raw data into a structured Pandas DataFrame with renamed columns and correct data types.
5. Loaded the final cleaned dataset into a CSV file for future analysis.
6. Performed basic analysis and visualized findings using bar charts and a pie chart:
   - Compared temperatures across the three cities.
   - Identified the city with the highest humidity.
   - Compared weather conditions across cities.

## Key Findings
- **Mombasa** recorded the highest temperature (23.84°C), while **Nairobi** was the coolest (17.28°C).
- **Mombasa** also recorded the highest humidity (83%), showing consistency with its coastal location.
- **Nairobi** and **Kisumu** shared the same weather condition (broken clouds), while **Mombasa** experienced few clouds.