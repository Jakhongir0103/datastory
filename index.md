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
3. How does the review product type influence the channels' growth?

### How to Attract Views with Your Video Titles:
1. Does the sentiment of the title have an impact on the views of the video?
2. General guidelines for a good video title

### Making the Most of Product Release Dates:
1. Do product release events even matter to YouTubers?
2. What are the topics discussed pre/during/post release?



# What should be the duratio of your videos?

Have you ever wondered how the trend of a YouTube video’s length evolves through time? Does it have anything to do with the success of the video? And if we want to upload a video of what duration should it be? We try to get some insights on these questions by analyzing video durations.

In our analysis we split videos into 2 groups short to medium length videos (0-20 minutes) and medium to long videos (more than 20 minutes) as we suppose these are 2 significantly different video types.

### Videos of less than 20 minutes

The first basic thing to do is to see whether there exists a correlation between video durations and number of likes and dislikes.

**plots**

There is a relatively high positive correlation (that is decreasing across the years), but significant (p_value < 0.05) between the duration of a video and the number of likes it gets. Moreover, we see significant negative correlations in most years between # of dislikes and duration and so with longer videos the number of dislikes decreases. This can be explained by the fact that with longer videos on average, the video contains more content and so is more valuable/interesting and thus gets more likes and less dislikes.

Let's now see the trend of likes, dislikes, and duration over the years to take their evolution into consideration.

**plots**

We see from the above plots that both the number of dislikes and likes have been increasing across the years, potentially due to more users on the platform or more user engagement. We particularly note that the rate of increase of the number of likes is much higher than the one of dislikes as shown by the increasing ratio of like/dislike. This combined with the fact that the length of YouTube videos has been increasing over the years explains why we had higher correlation between duration and likes than we had with dislikes.

Let's now see how the video duration is related to user engagement. We do it by plotting the moving average of likes to dislikes ratio over the duration of a video.

**plots**

Wow!! See that huge drop around 600 seconds =10 minutes?? Is it by sheer luck?? Let’s dig deeper into this.

Our hypothesis is that the drop could be caused by an enormous number of 10min videos on YouTube that contain low quality content, as youtubers usually try to produce videos around this duration to benefit from more ads on their videos (YouTube has a video length threshold of 10 min past which youtubers get 2 ads on their videos and thus more money). Let’s try to prove this.

**plots**

First we make sure that the drop is not caused by the “moving” nature of the average. Indeed, we see that even by plotting the mean for each time interval (not 'moving') the drop is still there. Also, we notice that the number of likes decreased but the number of dislikes and number of videos stayed the same between the 10 min interval and the interval before it.

Let’s try to focus only on the 10 minute videos.

**plots**

hmm, interesting?? This looks like a power law. Could the drop be caused by outliers? Let’s  plot the median instead of the mean.

**plots**

Nope! The drop is still there.

What if we compute the sum ?

**plots**

We see from the above plot that the sum is decreasing from small duration to high duration (from the left time interval to the right time interval), but remember that the *number of videos* stayed the same for the 2 time intervals (480.2, 600] and (600, 719.8] which **explains the drop seen** when computing the mean (as we have the same denominator but a lower numerator: the like to dislike ratio is decreasing from small duration to high duration, whereas the number of videos has been decreasing from small duration to high duration **except** for the time interval of around 600 seconds = 10 minutes).

For the curious ones, further analysis on why the number of videos stayed the same for these 2 duration intervals can be found in our notebook.

### Videos of more than 20 minutes

Of course not all tech videos are less than 20 minutes, so now let's turn our attention to the videos of more than 20 minutes and apply the same analysis on them as we did above.

**plots**

The opposite effect is seen here compared to videos of less than 20 minutes. The longer the video the more dislikes it gets and the less likes it gets which makes sense as longer videos (longer than 20 minutes) tend to be boring/redundant.

**plots**

Similarly for this case, the number of dislikes and likes have been increasing across the years. However, here we see that the length of YouTube videos has been decreasing over the years, maybe hinting at the fact that youtubers noticed that longer videos bore people more and they thus went for shorter videos. Let's now see how the video duration is related to user engagement.

**plots**

Okay, we see that the ratio of likes to dislikes is fluctuating a lot for videos between 1200 seconds (20 min) and 10000 seconds (2.7 hours). Because this is a wide range, let's see how the videos spread out across this range and then break it down into smaller ranges and see what the videos are about in different smaller duration ranges.

**plots**

So now, let's see what the people are speaking about in the videos.

**plots**

As we can see from above, the videos between 20 and 60 minutes which account for (get the percentage of these videos from all long videos) of the videos, are still about the review of the tech products, but they are full and extended review video possibly broken into several parts, while the videos with duration above 1h are more from the release day live videos, that last for a couple of hours.

Putting it all together we can say that the best range for the duration of a video is between 16 min and 2.7 hours, however longer videos are usually meant for live videos from conferences. The main takeaway here is that we certainly want to avoid having really short videos in order to provide meaningful content to viewers and also avoid having really long videos so that we avoid boring them!


# What should be the upload frequency?
As these tech channels jostle for attention in a crowded online space, specially in this field of tech reviews , one critical question arises: does the frequency of video uploads significantly influence their growth? And do they have to be very regular in terms of frequency to grow?

As regularity depends highly on the status of YouTubers, whether it's their full time activity, and how wide is their community, we decided to split the YouTubers into 8 categories, each of them representing a certain range where they lie:

- _0 - 10.000_  and  _10.000 - 50.000_   Very small YouTubers that often publish videos for fun and to their very small community.
- _50.000 - 100.000_ and _100.000 - 500.000_: YouTubers that start to have sponsors , and thus some obligations to be regular as it's starting to take most of their time.
- _500.000 - 1.000.000_ and _1.000.000 - 2.500.000_: Big YouTubers that start to have a big community, even fans, they usually do YouTube for a living and they win a lot through it.
- _2.500.000 - 5.000.000_ and _more_: very few YouTubers, known worldwide and being a reference as tech channels.

Let's first see their repartitions in this pie chart:

<iframe src="assets/plot/1_2_pie.html" width="750px" height="530px" frameborder="0" position="relative">Plot</iframe>

We can remark that more than half of them are small YouTubers, that almost a fifth are mid-range YouTubers, and that only around 6% of them are famous and have more than 500k subscribers. Our question then is , do you upload more frequency when you are famous? And more specifically, is the category in which you lie impacts your regularity?

To perform this analysis, we define the __regularity__ in the following way:

$$
\text{regularity} = n \cdot \log(1 + \frac{1}{\text{std}(f)})
$$
where $\text{n}$ is the number of videos uploaded within a month for a YouTuber, and $\text{f}$ = $\frac{1}{\text{delay}}$ where $\text{delay}$ is time in days between 2 consecutive videos.


This metric evaluates not just the frequency of video uploads on tech channels but also the consistency of their posting schedule. Channels that maintain a regular interval between video uploads gain a distinct advantage, highlighting the importance of a steady content rhythm. In contrast, channels with erratic schedules-such as releasing multiple videos on a single day followed by a prolonged period of inactivity—are less favored by this metric. Thus, while the overall quantity of content remains a key factor, the regularity and predictability of uploads emerge as crucial elements in driving channel growth.

And that is what we observe in this plot:

<iframe src="assets/plot/1_2_bars_1.html" width="750px" height="530px" frameborder="0" position="relative">Plot</iframe>

The main observation that we can do in this case, is that on average, the higher the category (and thus the number of subscribers), the higher the regularity is, and confidence intervals are not overlapping anywhere except within the first two categories that represent relatively small youtubers.

Now, we want to plot the moving average regularity and channels' growth to see if we can spot some clear relation between them:

<script>
function showFrame2(frameId) {
  // Get all iframes with the regularity_all class
  var frames = document.getElementsByClassName('regularity_all');

  // Hide all iframes with the regularity_all class
  for (var i = 0; i < frames.length; i++) {
    frames[i].style.display = 'none';
  }

  // Show the selected iframe
  var frame = document.getElementById(frameId);
  frame.style.display = 'block';
}
</script>

<!-- Create the dropdown menu -->
<select onchange="showFrame2(this.value)" style="margin: 8px 0; width: 20%; margin-left: 130px; margin-right: 5px">
  <option value="id_1">0-10k</option>
  <option value="id_2">10k-50k</option>
  <option value="id_3">50k-100k</option>
  <option value="id_4">100k-500k</option>
  <option value="id_5">500k-1M</option>
  <option value="id_6">1M-2.5M</option>
  <option value="id_7">2.5M-5M</option>
  <option value="id_8" selected>5M+</option>
</select>

<!-- Create the iframes -->
<iframe class="regularity_all" src="assets/plot/1_2_regularity_lines0-10k.html" width="750px" height="530px" frameborder="0" position="relative" id="id_1" style="display: none;">0-10k</iframe>
<iframe class="regularity_all" src="assets/plot/1_2_regularity_lines10k-50k.html" width="750px" height="530px" frameborder="0" position="relative" id="id_2" style="display: none;">10k-50k</iframe>
<iframe class="regularity_all" src="assets/plot/1_2_regularity_lines50k-100k.html" width="750px" height="530px" frameborder="0" position="relative" id="id_3" style="display: none;">50k-100k</iframe>
<iframe class="regularity_all" src="assets/plot/1_2_regularity_lines100k-500k.html" width="750px" height="530px" frameborder="0" position="relative" id="id_4" style="display: none;">100k-500k</iframe>
<iframe class="regularity_all" src="assets/plot/1_2_regularity_lines500k-1M.html" width="750px" height="530px" frameborder="0" position="relative" id="id_5" style="display: none;">500k-1M</iframe>
<iframe class="regularity_all" src="assets/plot/1_2_regularity_lines1M-2.5M.html" width="750px" height="530px" frameborder="0" position="relative" id="id_6" style="display: none;">1M-2.5M</iframe>
<iframe class="regularity_all" src="assets/plot/1_2_regularity_lines2.5M-5M.html" width="750px" height="530px" frameborder="0" position="relative" id="id_7" style="display: none;">2.5M-5M</iframe>
<iframe class="regularity_all" src="assets/plot/1_2_regularity_lines5M+.html" width="750px" height="530px" frameborder="0" position="relative" id="id_8" style="display: block;">5M+ Subscribers</iframe>


Across the spectrum, a consistent trend becomes apparent: channels that maintain a steady rhythm in their posting schedules generally see a more robust growth rate. This correlation holds true for most subscriber categories, with a notable exception in the 500,000 to 1,000,000 subscriber bracket.

For youtubers that have more than 5 000 0000 subscribers, we can observe that the growth rate fluctuates a lot, as they are only few youtubers within that category so it's more volatile, but despite the fluctuations, the trend is in overall similar to that of regularity.

Beyond these observations, a seasonal rhythm pulsates through almost all categories. In the end of the years (except for YouTubers between 500k- 1M subscribers) , a noticeable uptick in posting regularity is observed. This spike intriguingly aligns with the festive frenzy of Christmas, Thanksgiving, Black Friday, and major tech releases like video games and smartphones, including the much-anticipated iPhone launches. This seasonal phenomenon hints at a broader narrative, one that we will delve into with greater detail in Section 3 of our story.

Now, let's focus more on the group 4 (500k-1M subs), that has been problematic during the previous analysis:

- We first select all the channels that have been in this range at some point of time during this period and let's check how does the subscribers growth rate evolves depending on the regularity bin.

<iframe src="assets/plot/1_2_bars_2.html" width="750px" height="530px" frameborder="0" position="relative">Plot</iframe>

From the above plot we can see that the higher regularities are more correlated with the growth rate. So now, let's seperate those channels into 2 at regularity above and below 32, and see what's happening more in detail for those two subgroups, using the same time series comparison that we have done before. 

<script>
function showFrame1(frameId) {
  // Get all iframes with the regularity_range class
  var frames = document.getElementsByClassName('regularity_range');

  // Hide all iframes with the regularity_range class
  for (var i = 0; i < frames.length; i++) {
    frames[i].style.display = 'none';
  }

  // Show the selected iframe
  var frame = document.getElementById(frameId);
  frame.style.display = 'block';
}
</script>

<!-- Create the dropdown menu -->
<select onchange="showFrame1(this.value)" style="margin: 8px 0; width: 20%; margin-left: 130px; margin-right: 5px">
  <option value="positive" selected>Above 32</option>
  <option value="negative">Below 32</option>
</select>

<!-- Create the iframes -->
<iframe class="regularity_range" src="assets/plot/1_2_regularity_lines_range_4_0.html" width="750px" height="530px" frameborder="0" position="relative" id="positive" style="display: block;">Regularity above 32</iframe>
<iframe class="regularity_range" src="assets/plot/1_2_regularity_lines_range_4_1.html" width="750px" height="530px" frameborder="0" position="relative" id="negative" style="display: none;">Regularity below 32</iframe>


From the plots above, we can observe that for channels reaching a regularity above 32, over the 3-year period we analyzed, there is a high correlation between growth rate and regularity (they closely track each other for most of the period). This suggests that for YouTubers with 500k to 1M subscribers, once they reach the regularity of above 32, they should try to sustain the pace of frequency, as slowing the frequency may result in a decrease in the growth as well, as they are closely related at that point.

Additionally, when calculating the average number of videos per month for YouTubers who achieved a regularity of 32 or more, we find that this corresponds to nearly 33 videos per month, or about one video per day.

The main conclusion for this question is that, in general, high regularity (i.e., a consistent and frequent video upload rate with low volatility) is associated with greater success and a higher growth rate. Even in some problematic categories where the correlation is generally unclear, very high regularity still correlates with a high growth rate.

However, if you are a YouTuber with 500k to 1M subscribers and have chosen to maintain high regularity to accelerate growth, it's important to note that you should sustain this pace to preserve this growth rate, as reducing the frequency will likely lead to a decreased growth rate.


# How does the review product type influence the channels' growth?


In this section, we are going to focus on the types of review products. More specifically, we want to understand what types of tech products have a higher influence to the growth of our channel, or does it even matter at all? We take the following 7 product types and see their effect:

<table style="border: 1px solid black;">
  <tr>
    <td>Laptop</td>
    <td>Phone</td>
    <td>Camera</td>
    <td>Headphone</td>
    <td>Smart Watch</td>
    <td>Tablet</td>
    <td>Desktop Setup</td>
  </tr>
</table>

Let's first see which product types are more common among the YouTubers:

<iframe src="assets/plot/1_3_timeseries.html" width="750px" height="530px" frameborder="0" position="relative">Plot</iframe>

As we can see, most channels tend to focus on phones. It just means phones are a common topic to focus on, but we still need to see (in the next sub-section) how it actually influences the channel's growth.

Now, we will answer the following sub-questions:
- What range of product types should YouTubers should review?
- Which product categories have higher influence on the channels growth?
- Which product categories attract more viewers?

### What range of product types should YouTubers should review?

Below, we analyze the effect of covering a wider range of products, on the number of subscribers, a narrow range of products. To ensure the accuracy of our analysis, and to remove the effect of any possible confounder, we have balanced these 2 groups (wide, narrow) on some metrics, namely average duration of videos per channel, and the delay in time between publishing 2 sequential videos. Having a balanced dataset, let's now see the density of these 2 groups across the number of subscribers and the total views metrics.

<script>
function showFrame3(frameId) {
  // Get all iframes with the regularity_range class
  var frames = document.getElementsByClassName('1_3_dist');

  // Hide all iframes with the regularity_range class
  for (var i = 0; i < frames.length; i++) {
    frames[i].style.display = 'none';
  }

  // Show the selected iframe
  var frame = document.getElementById(frameId);
  frame.style.display = 'block';
}
</script>

<!-- Create the dropdown menu -->
<select onchange="showFrame3(this.value)" style="margin: 8px 0; width: 20%; margin-left: 130px; margin-right: 5px">
  <option value="id_1" selected>Subscribers</option>
  <option value="id_2">Views</option>
</select>

<!-- Create the iframes -->
<iframe class="1_3_dist" src="assets/plot/1_3_distribution_susb.html" width="750px" height="530px" frameborder="0" position="relative" id="id_1" style="display: block;">Subscribers</iframe>
<iframe class="1_3_dist" src="assets/plot/1_3_distribution_views.html" width="750px" height="530px" frameborder="0" position="relative" id="id_2" style="display: none;">Views</iframe>

From the above distribution of 'narrow' and 'wide' channels, we can see that non of the 2 groups is clearly outperforming the other. We can also confirm it more statistically. In fact, when we compute the statistical difference between them we get the following results:

<table align="center">
  <tr>
    <td></td>
    <td># Subscribers</td>
    <td># Views</td>
  </tr>
  <tr>
    <td>pvalue</td>
    <td align="center">0.65</td>
    <td align="center">0.88</td>
  </tr>
</table>

Being both pvalues larger than 0.05, it further confirms that whether or not a channel focuses on a single product review, or covers a wider range of products, it does not have a direct influence on the growth of the channel, i.e. number of subscribers/views.

### Which product categores have higher influence on the channels growth?

Ok, we found out that it is all up to us whether to focus on a single product or cover a wider range. Now the question is which products combination I can go with if I choose to cover several product types. To answer this question, here, we only fitler the top channels that focus on wider range of product types and see which ones of the product categories usually go together and bring them more views. For doing that we can make use of graphs for the sake of visualization as follows:

<img src="assets/plot/1_3_network.png" width="750px" height="400px" style="display: block; margin: 0 auto;" alt="Plot">

We can read the above graph as follows:

- nodes - product categories
- nodes size - average number of views of that category
- edge color - number of channels that have uploaded both of the corresponding products

By doing that we can see that the videos about _phones_, _headphones_ and _laptops_ have stronger bond compared to the other pairs, meaning most of the successful channels tend to cover the combination of these products.

### Which product categories attract more viewers?
Now, we know the secret combination of the tech products, but does that mean these are the only 3 products that go successful? Let's find it out!

For each video uploaded, let's get the ratio of the number of views of the video to the total number of views of the channel at the time of release of the video. Then, we want to see if any one of the products have a clearly higher ratio of views compared to the others. The reason why we are diving the number of views by the total number of views of the channel at the time of the release is to remove the influence of the current popularity of the channel.

<iframe src="assets/plot/1_3_bars.html" width="750px" height="530px" frameborder="0" position="relative">Plot</iframe>

Here, we can see that no single product is totally outperforming the other. However it is worth mentioning that the _phones_ tend to attract more viewers compared to the _camera_ and _smart watches_.

In summary, we can draw the following conclusions:

There isn't a significant statistical difference in the number of subscribers and total views between channels focusing on specific tech products and those covering a broader range. This implies that the diversity of reviewed product types doesn't noticeably impact the growth of the channels.
Among the successful channels covering a wide range of tech products, the ones that attract more viewers are Phones, Desktop setup, Laptop, and Headphones, in that order of importance. Successful channels often produce videos featuring a combination of Phones, Laptop, and Headphones.



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
