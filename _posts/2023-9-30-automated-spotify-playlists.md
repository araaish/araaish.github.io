---
layout: post
title: Automating spotify playlist creation
---

![playlists](/images/spotify_playlists.png)    Monthly playlists

For the last 4 years, I have been using IFTTT to connect different digital platforms for automating simple tasks. For example, I used an 'IFTTT widget' to turn on my smart bulb at sunset. Of the widgets I have tried, there's one that has been especially useful - an IFTTT widget that automatically creates monthly playlists of my liked songs on spotify.

I rely on recommendations and playlists to find new songs I like. Despite my reliance on other's playlists, I've never enjoyed categorizing songs into my own playlists. Instead, I have relied on this timeline based categorization of my songs. I get to see my music journey and connect back to the songs that highlighted a specific period of my life. Listening to these monthly playlists directly can be jarring, since you may get two songs wildly different in their genre and mood. They mainly hold value as a personal archive and a portal to relive memories through music.

IFTTT did this job of creating playlists for me very well, until the service became paid. There are some services for which I feel justified in paying a subscription. For Spotify or Netflix, I can imagine the extensive cost of feature development, maintainance, and cloud compute necessary to provide the service. However, there is a turning point at which the cost of paying for a service outweighs the cost of doing it yourself.

In this case, I achieve the same thing IFTTT did by running a Ruby script on a scheduled task on my local machine. The script queries the Spotify web API to retrieve my liked songs added after a timestamp and adds them to a new playlist.

This simple project prompted me to consider other services which I can implement myself. I think today there is an overabundance of applications that are interested in marketing a solution to a problem, rather than solving it. In my lifetime music has transformed away from something you could own to something that you access as a service. It seems that software has followed a similar path.

Considering the ubiquity of software and cloud services, it may be worthwhlie to ask myself a few questions if I'm building an application. Would I _need_ to use cloud services if I was building this just for myself? Aside from a financial incentive, is there any reason I _should not_ make it open source?

In the realm of connected services integration and automation, the difference in perspectives can be seen between software like [IFTTT](https://ifttt.com/) and [Home Assistant](https://www.home-assistant.io/)
