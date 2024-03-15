<h1 align="center">Welcome to Meteorology Project 👋</h1>

# Meteorology Project

In this repository, we are working on a detailed weather project with Python and API, which we will analyze later.

## Modules & API

For this project, we use modules called requests and pyowm, and we use a reliable and free source called OpenWeatherMap to get information.

```python
import requests
from pyowm import OWM

api_key = "9adced7ddff5c6dc7f031455d3dec00e"
base_url = "http://api.openweathermap.org/data/2.5/weather?"
```

## Usage
<h1 align="center"> The first method </h1>
In the first step, we create an input to receive the name of the city from the user so that the information related to that city is displayed. And then enter it in the sent address and then send to the source

```python
city_name = input("Enter city name:")

complete_url = base_url + "appid=" + api_key + "&q=" + city_name + "&units=metric"

response = requests.get(complete_url)
```

To display information from sources, they must be in json format, so we convert it to json and get the information we want from it and show it

```python
weather_data = response.json()
temperature = weather_data['main']['temp']
print(f'دما در شهر {city_name}: {temperature}°C')
```
<h1 align="center"> The second method </h1>
We create a management example with owm

```python
weather_manager = owm.weather_manager()
```
We receive and display meteorological information from the source

```python
observation = weather_manager.weather_at_place(city_name)
weather = observation.weather
pyowm_temperature = weather.temperature(unit='celsius')['temp']
print(f'دما در شهر {city_name} (با استفاده از PyOWM): {pyowm_temperature}°C')

```
## Result

This project was written by Majid Tajanjari and the Aiolearn team, and we need your support!❤️

# پروژه هواشناسی

در این پروژه، ما در حال کار بر روی یک پروژه آب و هوای دقیق با پایتون و API هستیم که بعداً آن را تجزیه و تحلیل خواهیم کرد.

## ماژول ها

برای این پروژه از ماژول هایی به نام requests و pyowm استفاده می کنیم و برای دریافت اطلاعات از یک منبع معتبر و رایگان به نام OpenWeatherMap استفاده می کنیم.

```python
import requests
from pyowm import OWM

api_key = "9adced7ddff5c6dc7f031455d3dec00e"
base_url = "http://api.openweathermap.org/data/2.5/weather?"
```

## نحوه استفاده
<h1 align="center"> روش اول </h1>

در مرحله اول یک ورودی برای دریافت نام شهر از کاربر ایجاد می کنیم تا اطلاعات مربوط به آن شهر نمایش داده شود. و سپس آن را در آدرس ارسال شده وارد کنید و سپس به منبع ارسال کنید

```python
city_name = input("Enter city name:")

complete_url = base_url + "appid=" + api_key + "&q=" + city_name + "&units=metric"

response = requests.get(complete_url)
```

برای نمایش اطلاعات از سورس ها باید با فرمت json باشند پس آن را به json تبدیل می کنیم و اطلاعات مورد نظر خود را از آن می گیریم و نشان می دهیم.

```python
weather_data = response.json()
temperature = weather_data['main']['temp']
print(f'دما در شهر {city_name}: {temperature}°C')
```
<h1 align="center"> روش دوم </h1>

یک مثال مدیریتی با owm ایجاد می کنیم

```python
weather_manager = owm.weather_manager()
```
اطلاعات هواشناسی را از منبع دریافت میکنیم و نمایش میدهیم


```python
observation = weather_manager.weather_at_place(city_name)
weather = observation.weather
pyowm_temperature = weather.temperature(unit='celsius')['temp']
print(f'دما در شهر {city_name} (با استفاده از PyOWM): {pyowm_temperature}°C')

```
## نتیجه

این پروژه توسط مجید تجن جاری و تیم Aiolearn نوشته شده است و ما به حمایت شما نیازمندیم!❤️
