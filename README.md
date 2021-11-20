# AutomatticDataAnalysis

![Tableau](https://user-images.githubusercontent.com/74743265/142716941-465bacdb-2a4a-4aa9-a01d-b21ec6dfab72.png)

Data format:

    This jupyter notebook contains an analysis on the public blog post. There are about 1.8 million total posts in this data set. All of these data are publicly available on the web. The data has the following format:

    { “blog_id”: id identifying the blog

    “post_id”: id identifying the post on that blog

    “lang”: the language code for the post (this is a combination of the user setting and our  language detection algorithm

    “url”: url to the post (but without ‘http(s)://’)

    “date_gmt”: date and time that the post was published
    (as set by the user). example: “2010-01-30 14:48:55"

    “title”: text title of the post

    “content”: text of the post with all html stripped out

    “author”: authors displayed name

    “author_login”: authors login username

    “author_id”: user id of the author

    “liker_ids”: array of user ids for people who have liked this post

    “like_count”: number of likes for this post

    “commenter_ids”: array of user ids for people who have commented on this post

    “comment_count”: number of comments on this post
    }

Sample data:


  {
    'comment_count': 0,
    'content': "The Snap! Jamaal Jackson tore knee ligaments in their win over the Denver Broncos. Making his first NFL start at center will be Nick Cole. Cole filled in at center against the Broncos, but McNabb fumbled two snaps, and three offensive linemen were penalized for false starts. While you can&#39;t blame all the false starts on the new center, it certainly doesn&#39;t make things easier for the linemen. \xa0 The good news is that Brian Westbrook is back after missing 5 games. His performance last week against the Broncos was promising, he had 9 carries for a total of 32 yards. In his last game against Dallas, Westbrook carried the ball 13 times for 50 yards rushing. \xa0 Does it matter that Michael Vick may not be available to play? Probably not, but we&#39;d certainly like to see him out on the field for a few key plays.\xa0If McNabb gets hurt, Kevin Kolb\xa0who proved himself against the Chiefs\xa0can help the Eagles soar to victory. \xa0 Bring out your big guns Dallas, we&#39;re flying into town with victory on our minds!  Posted via email   from Jason's posterous  ",
    'author': 'jasontromm',
    'title': 'Biggest Challenge for the Eagles This Week?',
    'like_count': 0,
    'author_login': 'jasontromm', '
    blog_id': 753,
    'date_gmt': '2009-12-31 16:27:39',
    'author_id': 762,
    'post_id': 969,
    'lang': 'en',
    'url': 'jasontromm.wordpress.com/2009/12/31/biggest-challenge-for-the-eagles-this-week'
  }

# Tableau visualization can be found [here](https://public.tableau.com/app/profile/himani.gadve/viz/Automattic_userengagmentanalysis/Summary)

# What are the median and the mean numbers of likes per post in this data sample?

By comparing the mean and median of likes count per post for the first 5 post, median value looks to be zero and mean value looks like 1 to 6 likes per post in first five post.

# Visualize the total daily count of likes vs total daily comments for this data sample

  To better understand the Daily count of likes vs comments, we need to first understand the timeseries data for all the years which can be possible by dividing analysis in 3 phases;

  1. Yearly Trends
  2. Monthly Trends
  3. Daily Trends based on the cohort filtering

## Yearly trend Analysis
### Findings:

  The yearly trend shows that likes count started growing from 2005 and increased drastically over the year with increase in 984k % change compare to 2005. Furthermore, for Comments started growing from 2002 and increased exponentially over the years.
  It is evident that like counts are maximum for the year 2013, 2014, 2015

## Monthly trend Analysis
### Findings:
  It shows the spike in the comments counts for the last 3 months of the year end such as September, October, November, December

## Daily trend Analysis
### Findings:
  It looks like a sudden spike in the daily like counts in the end of 2014

# How to determine which authors are the most “popular”? What additional data would you need?

  First step to check if there are any null authors present in the analysis and understand the total cohort size

  In order to understand the popularity of any author first steps need to do is that to aggregate data based on the below given key dimension:

  - Count of Post_id - To understand how many post author has done
  - Count of blog_id - To understand how many blogs author has publishes
  - Sum of total comment count - Provides good measure of popularity as reader has shown interest in the authors post and commented on it
  - Sum of total likes count - provides insights on liking or unliking of the posts

## Top 10 authors based on the Number of posts
  - Found out that author "Eli Nathanael" has made 42760 posts which is 2.3% of total posts but did not receive much engagement from users after looking at the number of comments and likes
  - Second highest post has been made by author FLYNN with post 42760 which accounts for 1.2% of total and received good support and engagement from users in terms of the number of comments and likes

## Popularity based on the Engagement metrics:
  To understand further the popularity of the author we need to look at 2 key metrics which are total comments made on the post which shows engagement from users and other important metric is total likes received which shows the

*Likes:* Liking a post is easy. Liking takes only one click. when someone likes your post, you don’t have the opportunity to engage back.

*Comments:* This allows a user to type a response to the post.

  As with likes, the more comments a post receives, the more people will see the post. However, comments have more weight than likes in social media algorithms, so five comments are worth more than five likes. Comments are great because they give the opportunity for you to continue the conversation. When a user comments, you can like their comment and reply to it. When you comment on other pages, you stand out from the crowded likes list and many pages will reply to you.

*Derived Metric:*

  - Total Comments received
  - Average comments per post: This shows the average number of comments done on a post

### Findings

  After looking at total data for total comment per post found out that author *tonyedwards* have made 162 posts in his total duration on the app and *eceived 132k comments* which means *received highest ~816 comments per post* but did not recieve any likes which is interesting. There can be multiple reasons and to understand better we need to check yearly comments data to see if likes feature was available at that time

## Popularity based on Likes
*Derived Metric:*

  - Total likes received
  - Total likes per post: This shows the average number of likes received on a post

### Findings

  After looking at total data for Average likes per post found out that author *Nicole Marie* has made only 1 post in his total duration on the app and *received 241 likes* which means *received highest ~241 likes per post* and also recieved 78 comments shows that high engagement from users on that one post.

## Popularity based on Yearly trend

### Findings
  After looking at total data for Average comments count per post found out that author *Tonyedwards* has more than *120000 comments counts* in his total duration on the app. Seconds highest comments counts receiver is *Ron DuBour* who received around *60000 comments counts* which can be interpreted as high engagement from these two authors.

# What additional data would you need?

  - The key missing feature in this data is the actual comments given by users. it would have helped use to perform sentimental analysis to understand the emotions and liking for each post.

## User acquisition Funnel analysis

  - *First post/Blog date or Author signup date:* signup or first post date would have helped us to create retention analyis to understand the health of the user acquision funnel
  - Missing details about users and their signup to first comment/like dates or flag

## Demographic data

  - Missing demographic data like age, gender, education would have helped use to better segment data into multiple funnels
  - Author type: eg, poet, Novelist, writer, Lyricist, screen writer, play write
  - Post/Blog type: eg.music, sport, reviews, news, updates

# Unique insight you can provide us about the data?

## Key Metrics yearly trend analysis:
  - Total Active authors per year
  - Total Posts per year
  - Total Comments received
  - Average comments per post per year: This shows the average number of comments done on a post
  - Total Likes received
  - Average likes per post per year : This shows the average number of comments done on a post

## Insights:

  - Yearly Active Authors + New user Analysis: The data shows that active Author counts doubled every year with growth rate of ~200% starting from 2007 and reached till ~450% in year 2011 and 2012 and reached to highest in 2014 which was 619470
  - User Engagement: Key metrics to measure engagement is number comments and likes on the post and allows users to interact with Authors which keeps platform alive. So, decided to measure engagement using to 2 key metrics as follows:
  - Average comments per post in a year & avg like per post in a year: It shows that starting from 2010 comments per post count increased drastically with avg. count of ~300 comments per posts

### Findings:
  1. Total yearly author count: Total yearly author count is highest in the year 2014
  2. Total yearly blog count: Total yearly blog count is highest in the year 2014
  Total yearly comment count: Total yearly comment count is highest in the year 2014
  3. Total yearly likes count: Total yearly author count is highest in the year 2014 and there were no likes on the post prior to 2011
  Average comment per post: Average comment per post has been significantly high since 2006. With highest comment counts in year 2011 and 2012
  Average likes per post: Average likes per post has been huge since 2013 to 2015. Likes has become stifer on the post since 2010

# Tools used to obtain these results and why I choosed them?

## Tool used for this analysis are as follows:
  Json Gzip - to unzip file from json to csv import os import json import gzip

  from urllib.request import urlopen

## Dataframe and Series
  import pandas as pd import numpy as np from datetime import datetime, timedelta, date from datetime import *

  import matplotlib.pyplot as plt import seaborn as sns import plotly.express as px import matplotlib

  import warnings warnings.filterwarnings('ignore')

  import warnings warnings.filterwarnings("ignore", category=DeprecationWarning)

  plt.style.use('fivethirtyeight') %matplotlib inline
