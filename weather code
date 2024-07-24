import requests
from dotenv import load_dotenv
import os

#loading ENV
load_dotenv()

#CONSTANTS
URL = "http://api.weatherapi.com/v1/current.json"
TOKEN = os.getenv('TOKEN')

def weather(city, lang='en'):  #aqi and lang
  """
  This function gives weather information of the given city.
  Optional parameter is language
  """
  #confi
  para = {
      'key': TOKEN,
      'q': city,
      #'aqi' : aqi
      'lang': lang
  }

  #Network Requests
  res = requests.get(URL, para)

  data = res.json()

  # Error handling
  if 'error' in data:
    print("Location not found")
    return

  #destructuring useful data
  forecast = {
      'temp_c': data['current']['temp_c'],
      'temp_f': data['current']['temp_f'],
      'condition': data['current']['condition']['text'],
      'state': data['location']['region']
  }
  print(forecast)

#help(weather)

user_location = input("Enter a location:")
user_lang = input("Enter lang code: (eg: en:English) ")
weather(user_location,user_lang)
