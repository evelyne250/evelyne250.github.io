## Welcome to My Blog

## Twitter Mining 

Twitter is an American microblogging and social networking service on which users post and interact with messages known as "tweets". Registered users can post, like, and retweet tweets, but unregistered users can only read them as defined by Wikipedia.
Twitter allows us to get developer access which can allow us to do data analysis using Twitter api. To be able to extract data from the twitter api you should first create a developer account on the Twitter apps site, Then log in after that you will need to create an app so as to be able to get the consumer key, consumer secret, access key and access secret which will help you in Authentication.


### Installation

To use Tweepy you should first install it using pip and import other necessary modules:


```markdown

**Modules** 

`!pip install tweepy
import tweepy
from tweepy.streaming import StreamListener
from tweepy import OAuthHandler
from tweepy import Stream
import tweepy 

# Fill the X's with the credentials obtained by From The Twitter api
consumer_key = "XXXXXXXXXXXXXXXXXXXXXXXX"
consumer_secret = "XXXXXXXXXXXXX"
access_key = "XXXXXXXXXXXXXXXXXXXXXX"
access_secret = "XXXXXXXXXXXXXXXXXX"

# Function to extract tweets 
def get_tweets(username):

		## This handles Twitter authentification and the connection to Twitter Streaming API
		# Authorization to consumer key and consumer secret 
		auth = tweepy.OAuthHandler(consumer_key, consumer_secret) 

		# Authorization to user's access key and access secret 
		auth.set_access_token(access_key, access_secret) 

		# Calling api 
		api = tweepy.API(auth) 

		# tweets to be extracted 
		tweets = api.user_timeline(screen_name=username, count=20) 

		# Empty Array 
		u =[] 
		tweet = [i.text for i in tweets]
		for i in tweets: 

			# Appending tweets to the empty array u 
			u.append(i) 

		# Printing the tweets 
		print(u) 

` 
```

From This code above We first install tweepy and import modules, Then we authenticate using the credentials obtained from the Twitter developer account.
Write a function of getting tweets for Twitter handles by first authenticating your key and calling the api Then Extract data from the api.
For more details see [Twitter mining](https://github.com/10acad/QuickStart2020/blob/master/week1/notebook/twitter_challenge_solution.ipynb) For more information.

### Web Scraping

Web Scraping is extracting data from websites. All you have to do is access the html of the website. You will have to install the beautiful soup package so as to be able to scrape data from the website.

### Data extraction from the web using Python's Beautiful Soup module

```markdown

**Modules** 

`!pip install requests BeautifulSoup4 fire
from requests import get
from requests.exceptions import RequestException
from contextlib import closing
from bs4 import BeautifulSoup
import pandas as pd
import os, sys
import fire 

def simple_get(url):
    
    try:
        with closing(get(url, stream=True)) as resp:
            if is_good_response(resp):
                return resp.content
            else:
                return None

    except RequestException as e:
        log_error('Error during requests to {0} : {1}'.format(url, str(e)))
        return None


def is_good_response(resp):
    
    content_type = resp.headers['Content-Type'].lower()
    return (resp.status_code == 200 
            and content_type is not None 
            and content_type.find('html') > -1)


def log_error(e):
   
    print(e)
` 
```

To scrape data you will first install modules and packages of Beautiful soup The simple_get function Attempts to get the content at `url` by making an HTTP GET request, If the content-type of response is some kind of HTML/XML, return the
 text content, otherwise return None. is_good response function Returns True if the response seems to be HTML, False otherwise.
 and the log_error helps us to log errors, This function just prints them.
 
 For more information about web scraping check out it here : [Real Python](https://realpython.com/python-web-scraping-practical-introduction/) or
 [Datacamp](https://www.datacamp.com/community/tutorials/web-scraping-using-python)

### Author
Names : Evelyne Umuhire <br>
Email: Uevelyne44@gmail.com
