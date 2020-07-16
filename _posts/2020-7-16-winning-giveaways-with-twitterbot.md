---
layout: post
title: Winning giveaways with twitterbot
---

### Inspiration

If you have a social media account, you have probably noticed a product giveaway in a sponsored add or by your favorite content creator. In the last decade, these digital media platforms have allowed for a new method for marketing and customer engagement: online giveaways.

I noticed these kind of giveaways increasing in my social media feeds, and I had one simple question – _what would make it worthwhile to enter?_

The answer is by drastically increasing your chances. One entry in a lucky draw is a waste of time when there are thousands of entries. The first idea to come to mind would be to increase your entries, but most contests require giving away information or limit your entries behind paywalls or otherwise simply to maintain the integrity of the contest.

Thus the last idea is to enter many contests. If the probability of winning one contest is low, we can increase our chances of winning _something_ by entering as many contests as possible. So I thought about using automation to enter some online contests.

### Twitter Botting

Twitter is perhaps the easiest platform for entering giveaways. There are many giveaways where the only criteria to enter is a RT (retweet) and a follow. By taking advantage of the twitter API, we can write a relatively simple Python script to periodically web scrape the twitter search results for the #giveaway tags and retweet eligible tweets.

### The Process

So I'll walk you through the steps I took from start to finish, and maybe you can try some social media bots of your own with various purposes.

#### Twitter API

Make a twitter developer account, and create a new app. You will have to fill out a form to get permission to use the API. Once you have created a web app, activate your access and consumer keys and save them.

#### Twitterscraper

Now you can start coding. Firstly, you must save your keys as global variables, since these are necessary to authorize your app to access the API.

The first step is to scrape the twitter website to find eligible giveaways. You can use BeautifulSoup to query these from the advanced search section on the Twitter website, but I found some neat Python libraries that do this for you. Twitterscraper is a great library that will query tweets and users based on whatever keywords, hashtags, and other filter you input.

#### Tweepy

Another great python library is tweepy, which simplifies the API requests for you. simple function calls can send tweets, retweet, follow, and like tweets. I used this to filter enter the giveaways that I scraped.

#### Hosting

I used Heroku to host the python script online so it could run 24/7 without supervision. Heroku is a great service that allows free hosting for web apps.

### Stealth

A major consideration for this project is to get away with entering all these giveaways while pretending to be a human. The twitter API has rate limits which prevent you from making a large amount of requests in a short time. This challenge required me to experiment with how often I entered contests and be frugal with API requests. Some other considerations include:
1. capping the number of accounts I follow using a queue
2. posting a daily tweet with randomly generated sentences
3. posting my own fake giveaways to get followers and activity on my own account
4. blacklisting bot spotting accounts

### Interesting Observations

After running the script for two months, I had some interesting results.

#### Efficacy

Unfortunately, I did not win a new car or five Nintendo switches. Out of a few thousand giveaways entered, I won four. While this is a discouraging result, with a larger net to cast in more contest entries, the ratio will increase.

![my first W](/images/first_win.png)


#### Fake and Worthless Giveaways

I also won some sketchy giveaways. ![possible scam](/images/scam_win)

These kinds of contests clouded the overall pool and decreased my yield of wins. In a future attempt at botting, I would use better filters to get rid of illegitimate giveaways.

#### Bot Spotters

There were many bot accounts dedicated to exposing other bots. They brought them in by pretending to host a giveaway by using popular keywords.

![bot spotters](/images/bot_spotting.png)

I blacklisted many of the accounts, but some still got through. While these were annoying, I used their technique to gain followers of my own by hosting my own fake giveaways.


#### Errors

Because of Twitter's restrictive rate limits, I had to time everything carefully, with delays between each part of the entry process. Sometimes, this would backfire. When the webscraper found 0 new giveaways, the script started posting random tweets every second.


### Conclusion

This iteration of my twitterbot did not accomplish the ultimate goal: winning a Ferrari and the briefcase from Pulp Fiction. However, this twitterbot was a good proof of concept for automated mass entry in giveaways. I also learned a lot about automation, API's and scripting from this project.

I already have ideas to improve the bot, and in the future I may try exploiting online giveaways on other platforms like Gleam.io or Instagram.

#### Ethical Questions

It is a fair argument to make that taking advantage of such contests is unfair and takes away from other people's chance of winning. But until I actually win valuable prizes, I won't think about how to balance the scales.

#### Check out my code [here](https://github.com/araaish/twitterbot)
