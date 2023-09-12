# Build-a-weather-application-that-retrieves-weather-data-for-a-user-specified-location
import requests

def get_weather(city):
    api_key = "YOUR_API_KEY"
    base_url = f"http://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}"
    response = requests.get(base_url)
    data = response.json()
    weather = data['weather'][0]['description']
    temperature = data['main']['temp']
    print(f"Weather in {city}: {weather}")
    print(f"Temperature: {temperature}°C")

city = input("Enter city: ")
get_weather(city)
