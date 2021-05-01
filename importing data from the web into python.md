# Importing Data From The Web Into Python

Throughout your journey as a Data Scientist, you will find yourself regularly dealing with data. Sometimes, these data are readily available, while other times, you have to source for and gather the data yourself.

Your data can be gathered from various sources, but more often than not, you would get these data from the web.

Now imagine you found a website that has this gigantic enormous data that you find very useful. Unfortunately, there is no way you can download the contents on this website onto your device for analysis.

Manually collating the data from the website would cost you a great amount of time. Fortunately, you can seamlessly import these data using some Python packages.

## Importing data using urlretrieve

1. Import the function `urlretrieve` from the `urllib.request` subpackage.
                from urllib.request import urlretrieve
2. Assign the url of the website to a variable - ‘url’ is used as example here.
                ```
                url = 'https://google.com'
                ```
3. Use the function `urlretrieve` to save this file locally. Pass two arguments to the function - the url of the website (which has been assigned to the variable ‘url’) and the name you wish to save the file as.
                ```urlretrieve(url, 'file.txt')```
4. The data is now saved as a file on your device, which you can manage and wrangle as you wish.



## Importing data using urlopen and Request

To fully understand how this works, you need to have a basic understanding of HTTP requests. But worry not, even if you do not understand requests, you can follow the steps below and import data from the web.

1. Import the functions `urlopen` and `Request` from the subpackage `urllib.request`.
                ```from urllib.request import urlopen, Request```
2. Specify the url.
                ```url = 'https://google.com'```
3. Package the request by calling `Request` on the url.
                ```request = Request(url)```
4. Send the request and catch the response.
                ```response = urlopen(request)```
5. The response gotten from your request is an object. To extract the content of the html, call the read method on the response object.
                ```response = response.read()```
6. You can then print, wrangle and manage the content of the webpage.
                ```print(response)```


## Importing Data With requests

Then here comes the almighty `requests` package. It is an easier and more recommended way of performing the same import performed with `urllib` above.

1. Import the request package.
                ```import requests```
2. Specify the url.
                ```url = 'https://google.com'```
3. Call requests' get method on the url. This packages the request, sends it and catches the response. All with one command. Pretty cool, right?
                ```request = requests.get(url)```
4. The response is an HTTP object. To access the contents of the response, call the text attribute on the object.
                ```print(request.text)```


> Note that there are several other actions you could take with the packages used above, like interacting with an API. However, for the context of this article, we are only concerned with using them for importing data from a webpage.

Woohoo! You can now easily import data from the web with Python.
The data imported however are HTML contents, with html tags, and other html attributes. They are therefore not quite ready for use or analysis.

To make them ready for use, you have to format them using a package called BeautifulSoup. This will be discussed in a follow-up article.

Till then, keep importing data with these packages and doing wonders with Python.