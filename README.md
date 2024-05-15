# Weather-Forecasting-System-in-Python

Weather-Forecasting-System-in-Python is a simple Python script that fetches the current weather details for a specified city using the WeatherAPI.

## Features

- Fetches the current temperature in Celsius.
- Fetches the current weather condition.
- Provides error handling for invalid city names and network issues.

## Prerequisites

- Python 3.x
- Requests library

## Installation
-Install the Requests library
```
pip install requests
```

## Example
```
import requests
import json

# Function to fetch weather data
def fetch_weather(city):
    
    api_key = 'Your api key here' # Use api key from weatherapi. If you use api key from another host, you need to do some simple modifications in this code.
        
    url = f"https://api.weatherapi.com/v1/current.json?key={api_key}&q={city}"
    response = requests.get(url)

    if response.status_code != 200:
        raise Exception(f"Error fetching data from WeatherAPI: {response.status_code} - {response.text}")

    weather_data = response.json()
    return weather_data

# Main function
def main():
    city = str(input("Enter the name of the city:\n")).strip()
    
    try:
        weather_data = fetch_weather(city)
        print(f"\nDetails of {city.capitalize()}:")
        print(f"Temperature: {weather_data['current']['temp_c']}°C")
        print(f"Weather: {weather_data['current']['condition']['text']}")
    except Exception as e:
        print(f"An error occurred: {e}")

if __name__ == "__main__":
    main()
```
## contact
Please let me know if you have any suggestions at bishalbhusansarma87787@gmail.com. Thank You.
