# Webscraper
Python Web Scraper using bs4

#check if you have you have all the right libraries (bs4, urllib)
help('modules')

#import libraries
from urllib.request import urlopen
from bs4 import BeautifulSoup

#input URL
quote_page = 'https://github.com/'

#Make the website into a query string
page = urlopen(quote_page)

#Store the parsed HTML in the varible 'soup'
soup = BeautifulSoup(page, 'html.parser')
print (soup)

#take out the <div>of 'name' and retreive its value 
name_box = soup.find('h1', attrs = {'class' : 'name'})

#strip() is used to remove starting and traing syntaxes 
name = name_box.text.strip()
print (name)

#retreive index price
price_box = oup.find('div', attrs = {'class' : 'price'})
price = price_box.text
print (price)
