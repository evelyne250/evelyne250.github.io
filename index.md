## Welcome to My Blog

## Twitter Mining & Web Scraping

Twitter is an American microblogging and social networking service on which users post and interact with messages known as "tweets". Registered users can post, like, and retweet tweets, but unregistered users can only read them as defined by Wikipedia.
Twitter allows us to get developer access which can allow us to do data analysis using Twitter api. To be able to extract data from the twitter api you should first create a developer account on the Twitter apps site, Then log in after that you will need to create an app so as to be able to get the consumer key, consumer secret, access key and access secret which will help you in Authentication.


### Installation

To use Tweepy you should first install it using pip and import other necessary modules:


```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

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
From This code We first install tweepy and import modules, Then we authenticate using the credentials obtained from the Twitter developer account.
Write a function of getting tweets for Twitter handles by first authenticating your key and calling the api Then Extract data from the api.



[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/evelyne250/evelyne250.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
