# Reddit Stock Market Sentiment Analysis of "$NVDA" 


## Table of Contents
* [Project Title](#project-title)
* [Technologies](#technologies)
* [Motivation](#motivation)
* [Overview](#overview)
* [Required Libraries](#required-library)
* [Methodology](#methodology)
* [Results](#results)
* [Summary](#summary)



## Project Title
Reddit Sentiment Analysis of "$NVDA"

## Technologies
[Python](https://www.python.org/downloads/ "Download Python") 3.12.6

## Motivation
![](https://i.pinimg.com/564x/19/c1/3c/19c13c17a1765b1d3073f10e73e6419f.jpg)


## Overview 

Sentiment analysis is the process of detecting positive or negative sentiment in text. It is often employed by businesses to gauge brand reputation and understand customer perceptions. In the current scenario, we will focus on user-generated content related to NVDA (NVIDIA) stocks from the subreddit r/WallStreetBets. There are two types of content available on the web: facts and opinions. Facts are objective statements about topics that can be collected from the internet using search engines that index documents based on relevant keywords. On the other hand, opinions are user-specific statements expressing positive or negative sentiments regarding NVDA stocks. Opinions are generally harder to categorize using keywords, prompting the use of various text analysis and machine learning techniques to extract sentiments from comments. In this project, we will analyze the sentiment of comments from r/WallStreetBets posts about NVDA by calculating each tokenized word's polarity scores using the VADER (Valence Aware Dictionary for Sentiment Reasoning) model. Additionally, we will analyze the correlation between stock market movements and the sentiments expressed on Reddit.

## Required Libraries

* [PRAW](https://praw.readthedocs.io/en/stable/getting_started/installation.html): Reddit API Wrapper(PRAW)

* [VADER](https://pypi.org/project/vaderSentiment/#data): Valence Aware Dictionary for Sentiment Reasoning is a model used for text sentiment analysis that is sensitive to both polarity (positive/negative) and intensity (strength) of emotion

* [NLTK](https://www.nltk.org/install.html): Natural Language Toolkit

* [yfinance](https://pypi.org/project/yfinance/): Yahoo! Finance market data downloader

* [Matplotlib](https://matplotlib.org/): comprehensive library for creating static, animated, and interactive visualizations in Python


## Methodology

### 1. Reddit Dataset:
* [Reddit API](https://www.reddit.com/dev/api/)
  <details>
  <summary>How to set up a Python API Wrapper to obtain data</summary>
  
    ## Prerequisites
    1. To access Reddit's API, you will need to create a [Reddit account](https://www.reddit.com/register/)
    2. Client ID
    3. Client Secret
    4. User Agent

    ## Getting Access
  ![](img/create_application.png)
    1. Create an application via [App Preferences](https://www.reddit.com/prefs/apps), then select the "Are you a developer? Create another app..." at the bottom of the page.
    2. Fill out the required details: your API's **Name**, make sure to select the **'script'** option and the redirect URL with **http://localhost:8080** or **“http://www.example.com/unused/redirect/uri”** --- and click **'create app'**.
  
    ## Authentication Information
  ![](img/developed_app.png)
  iii. **Client ID('personal use script')**, **Client Secret('secret')**, and **User Agent('name')** values will be shown after creating your application-- these authentication information will be needed to create the ```praw.reddit```.
  
    ## Create a reddit connection with reddit API information


  ```python
  
  # Create praw.Reddit object with with reddit OAuth creds
  # Reddit application creds created at https://www.reddit.com/prefs/apps
  reddit = praw.Reddit(
              client_id= PRAWConfig.REDDIT_CLIENT_ID,
              client_secret= PRAWConfig.REDDIT_CLIENT_SECRET,
              user_agent= PRAWConfig.REDDIT_USER_AGENT)
   ```
  
    
  </details>
  
 * [Scrape data from Reddit using the Python Reddit API Wrapper(PRAW)](https://praw.readthedocs.io/en/latest/getting_started/authentication.html#script-application)
 
    <details>
    <summary>How to extract the comments from a Reddit subreddit post</summary>
    
      ## Create a submission object 
      ![](img/![Reddit_scrapper](https://github.com/user-attachments/assets/ed3ba9ee-23a8-4426-ae51-0fbba96c9937)
)
        (Submission ID is an assigned "ID" for a specific post on Reddit)
  
      In order to extract the comments from a subreddit post, you'll need to **create a submission object** and in this script-- we are looking for specific posts: the **top 30 "hot" popular posts in r/WallStreetBets, that was written by a Reddit user, and also mentions $NVDA.** Subreddits can be filtered in many different ways; you can also choose to display your desired number of posts by changing ```(limit=30)``` that are ["new", "hot", "top", etc.](https://praw.readthedocs.io/en/latest/code_overview/models/subreddit.html)
  

  
     
     
  
  
      
      

  
    </details>
    
 


