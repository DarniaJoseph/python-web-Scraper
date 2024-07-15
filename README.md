# python-web-Scraper
import requests
from bs4 import BeautifulSoup

def get_page_title(url):
    try:
        response = requests.get(url)
        if response.status_code == 200:
            soup = BeautifulSoup(response.content, 'html.parser')
            title = soup.title.string
            return title
        else:
            return "Error: Unable to fetch the web page."
    except Exception as e:
        return f"An error occurred: {e}"

url = input("Enter the URL of the web page: ")
title = get_page_title(url)
print(f"The title of the web page is: {title}")
