# bike-images-from-bikewale
# Assuming you've already imported the necessary libraries (requests and BeautifulSoup)
import requests
from bs4 import BeautifulSoup

url = "https://www.bikewale.com/royalenfield-bikes/"
response = requests.get(url)
soup = BeautifulSoup(response.content, 'html.parser')
image_wrappers = soup.find_all('div', class_='imageWrapper')

# Initialize an empty list to store image URLs
img1 = ['https://imgd.aeplcdn.com/227x128/n/cw/ec/49656/continental-gt-right-side-view-12.png?isig=0&q=80']
img2 = ['https://imgd.aeplcdn.com/310x174/n/cw/ec/115871/mt-15-right-side-view-3.png?isig=0&q=80']
img3 = ['https://imgd.aeplcdn.com/310x174/n/cw/ec/124013/hunter-350-right-side-view-5.png?isig=0&q=80']
img4 = ['https://imgd.aeplcdn.com/310x174/n/cw/ec/103183/raider-125-right-side-view-20.png?isig=0&q=80']
img5 = ['https://imgd.aeplcdn.com/310x174/n/cw/ec/49444/ntorq-125-right-side-view-11.png?isig=0&q=80']

for wrapper in image_wrappers:
    img_src = wrapper.img['src']
    img1.append(img_src)

for i, img_url in enumerate(img1 + img2 + img3 + img4 + img5, start=1):
    print(f"Image {i} URL: {img_url}")




