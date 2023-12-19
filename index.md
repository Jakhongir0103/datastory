---
layout: page
title: Journey to Tech World
subtitle: A Numbers-Backed Analysis to Rock Your YouTube Tech Channel
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/path.png
share-img: /assets/img/path.jpg
use-site-title: true
---

If you're interested in creating your own YouTube channel in the field of tech product reviews or are curious about how these channels gain attraction and evolve over time, you've made the right choice by clicking this link!

In this blog post, the Datasquad will cover everything you need to know about YouTube tech channels, from the types and range of products to review, to the timing of the release of videos, and even how to write your video titles to gain the most attraction!

All this is done through a very thorough analysis of the YouNiverse dataset, Large-Scale Channel, and Video Metadata from English-Speaking YouTube.

We conducted our analysis by first putting together hypotheses of how a successful tech channel operates, then we (dis)proved each of the hypotheses so that after reading this post, you go out with general guidelines that will help you in your YouTube journey.

## The Blog is Structured in the Following Way:

### Characteristics of a Successful Tech Channel:
1. What should be the duration of your videos?
2. What should be the upload frequency?
3. What is the right range of products to review?
4. Which types of tech products attract more attention?

### How to Attract Views with Your Video Titles:
1. Does the sentiment of the title have an impact on the views of the video?
2. General guidelines for a good video title

### Making the Most of Product Release Dates:
1. Do product release events even matter to YouTubers?
2. What are the topics discussed pre/during/post release?


`tyr dynamic plots`
#### with iframe

<!-- save the html file with:
fig.update_layout(width=700, height=500) -->
<iframe src="assets/plot/output_plot.html" width="750px" height="530px" frameborder="0" position="relative">Plot</iframe>

# The rest of the blog

### Making the Most of Product Release Dates:
1. Do product release events even matter to YouTubers?
We look at the influence of a release event on the success of a channel that talks about it. Does talking about the release of a tech product boost the number of its views and subscribers? What is the effect of publishing a video about a specific product during the period of its release on the growth of the channel? To this end, we focus on 3 items: iPhone x, iPhone 7, and Galaxy s9. We split the tech channels into 2 categories: one that does talk about the release (the “treat channels”)  and one that doesn’t ( the “control channels”). We compare the trends of the channel’s growth over one year ( 6 months before and after the release). Moreover, for each item, when considering the channels that talk about its release, we divide these channels into 3 groups: channels that have between 1 and 10 videos that talk about it, others with a number between 11 and 50, and a last one with the channels that contain more than 50 videos.

Before doing the comparison between 2 groups, we first want to balance these groups on the number of subscribers, frequency of uploading a video, and the ratio of tech review videos, because these features (especially the number of subscribers and tech video ratio) might be a confounder of the growth of the channel.

After doing the balancing, we observed that only the groups with less than 10 videos and the ones with more than 10 but less than 50 were relevant four our analysis as the number of channels with a higher number of videos was too small. So, we focused on these 2 groups only.
###plots

The green line corresponds to the release date whereas the 2 red lines define our  “window of interest “ ( 6 months before/after the event).

iPhone x :

As for iPhone X, we see that the channels that have produced a video about it during the 6 months of its release have seen some increase in the growth of the channel (ratio of new subs/view to the total subs/view), while for the other channels, they did not have any dramatic change in their trend. We see this difference in the increase of the trend more clearly especially for the channels that have produced between 1-50 videos, because the number of other channels is too few that we cannot see any increase that clearly (even though we see that it increased on the date of release).

So, let's focus mostly on the channels in Groups 1 and 2:

iPhone 7 : 

We see an interesting trend in Group 2 of iPhone 7, namely the trend is increasing for both channels. Let's dig deeper into this. We wanted to see what the videos were mostly about.

Apparently, during this time we had many videos about other tech by Xiaomi and Samsung as well. Indeed, below we list the release dates of other phones by Samsung and Xiaomi, of which the release date overlaps with the period we are interested in: 

| Phone Name | Release Date | |-------------------------------|-------------------| | Redmi Note 4G | June 15, 2016 | | Redmi Note 4X | August 29, 2016 | | Redmi Note 3 Pro Prime | October 17, 2016 | | Redmi Note 3 | February 10, 2016 | | Xiaomi Redmi 3S Prime | October 17, 2016 | | Xiaomi Redmi 3S | June 16, 2016 | | Xiaomi Redmi 4 | August 24, 2016 | | Xiaomi Mi 5s | September 22, 2016| | Xiaomi Mi 5s Plus | September 22, 2016| | Xiaomi Redmi Note 4 Plus | August 29, 2016 | | Samsung Galaxy A5 (2016) | June 17, 2016 | | Samsung Galaxy J5 (2016) | June 22, 2016 | | Samsung Galaxy J7 (2016) | June 22, 2016 | | Samsung Galaxy Grand Prime Plus| July 27, 2016 | | Samsung Galaxy C5 Pro | August 20, 2016 | | Samsung Galaxy J7 Nxt | October 21, 2016 | | Samsung Galaxy C7 Pro | November 8, 2016 | | Samsung Galaxy A7 (2016) | November 13, 2016 |

Galaxy s9 :

Let us now try other groups as well. For example, 2nd Group of Galaxy s9:

Indeed we again see a similar result for this group as well, namely, these are the products (other than Galaxy s9) that were released by Samsung and Xiaomi during the period of our analysis:

Phone Name	Release Date
Redmi Note 5A	December 22, 2017
Redmi Note 5A Prime	January 24, 2018
Redmi Note 5	February 14, 2018
Redmi Note 5 Pro	March 15, 2018
Redmi 6 Pro	April 20, 2018
Redmi 6A	May 22, 2018
Redmi S2	May 25, 2018
Xiaomi Mi 8	May 29, 2018
Xiaomi Mi 8 Pro	May 29, 2018
Samsung Galaxy J7 Nxt	March 29, 2018
Samsung Galaxy A8 (2018)	April 20, 2018
Samsung Galaxy J6+	May 30, 2018
Samsung Galaxy J4+	May 30, 2018
Samsung Galaxy A8+ (2018)	May 31, 2018

General  conclusion:

From all the observations above, our conclusion can be that when focusing on a particular item, we can have one of the 2 following scenarios : 

- either there is a clear gain for the treat channels in terms of the number of views and subscribers such that the orange curve is above the blue one inside the window between the 2 red lines whereas it is generally below it outside.
- either no gain appears. In this case, after doing some more investigations, it seems that this could be explained by the fact that the release of the considered item overlaps with other items' releases, which the control channels talk about, in such a way that the gains of treat channels are still "inferior" to the one of the control ones (the effect of the release of the considered item is "hidden" by the release of other items, released at the same time).

Moreover, increasing the number of videos on a channel that talks about the release is not a good way to make it succeed. The channel does better have to talk about it in a small number of videos.
