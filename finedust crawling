from bs4 import BeautifulSoup
from pprint import pprint
import requests

html = requests.get('https://search.naver.com/search.naver?query=날씨')
#pprint(html.text)

soup = BeautifulSoup(html.text, 'html.parser')

data1 = soup.find('div', {'class': 'weather_box'})

find_address = data1.find('span', {'class':'btn_select'}).text
print('Location : '+find_address)

find_currenttemp = data1.find('span',{'class': 'todaytemp'}).text
print('Temperature : '+find_currenttemp+'℃')

data2 = data1.findAll('dd')
find_dust = data2[0].find('span', {'class':'num'}).text
find_ultra_dust = data2[1].find('span', {'class':'num'}).text
find_ozone = data2[2].find('span', {'class':'num'}).text
print('Fine dust: '+find_dust)
print('ultra Fine dust: '+find_ultra_dust)
print('Ozone : '+find_ozone)
