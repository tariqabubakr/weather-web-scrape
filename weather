import requests
import numpy as np
import pandas as pd
from bs4 import BeautifulSoup

response = requests.get("https://weather.com/weather/tenday/l/3397f813e2a7833d07c1756bf7fb0ff62a68918b04566dcd9ccb15451a0a2a64")
soup = BeautifulSoup(response.content, 'html.parser')
soup.title.string

content = soup.find_all('p')
weather = []
for tag in content[3:-3]:
    #print(tag.get_text())
    weather.append(tag.get_text())
weather = weather[0:15]
print(weather)

dates = soup.find_all("h2")
date = []
for tag in dates[2:-6]:
    #print(tag.get_text())
    date.append(tag.get_text())
print(date)

d = {'Date':date,'Weather':weather}
#d
len(weather)

df = pd.DataFrame(d)

dfprint("The weather today is: " + df['Weather'][0])
