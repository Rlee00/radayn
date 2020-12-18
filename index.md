Tweet! Tweet! Tweet!

That's not the sound of a bird but rather a friend telling me to immediately post the joke I just told her onto my Twitter page.

In this digital age, we are able to share our thoughts and ideas into the virtual space with the click of a button from a variety of digital devices. According to a Pew Research Center study in 2018, 88% of respondents between the ages of 18 to 29 reported using some kind of social media. The number is 78% for 30- to 49-year-olds which is lower but still significant. On top of being able to interact with our friends from the real world online, we can also find new friends in the virtual space. For some people, social interactions have transcended the physical sphere to the virtual one.

> “The first rule of social media is that everything changes all the time. What won’t change is the community’s desire to network.” 
--- Kami Huyse, PR & social media strategist, entrepreneur, CEO Zoetica Media

Encouraging this phenomenon are social media platforms such as Twitter. One can easily interact with others or spread content by retweeting it, replying to a Tweet or simply mention someone. With so much influence and interaction people can have on social media, it is interesting to further explore the tendency of individuals to bond with similar others. One such similarity could be the sentiment polarity (shortened to polarity) of the user based on their tweets which can be divided into 3 broad categories - Positive, Neutral and Negative.

## Are Twitter users positive people?

Let's first look at how many people are positive, negative or neutral in terms of their tweets on Twitter.

{% include graph_polarity.html %}

It seems that so many people are positive on Twitter 🥰 ! Well, this is not shocking. The polarity of a person's tweet matters.

> “Social media is changing the way we communicate and the way we are perceived, both positively and negatively. Every time you post a photo or update your status, you are contributing to your own digital footprints and personal brand.” --- Amy Jo Martin, Founder and CEO of Digital Royalty

[Studies](https://buffer.com/resources/positivity-social-media/) have shown that positivity in social media wins in online interactions as people become less engaged when content on their feed becomes more negative. [With society being obssessed with influencers and younger people wishing to become influncers themselves](https://www.bloomberg.com/news/articles/2019-11-05/becoming-an-influencer-embraced-by-86-of-young-americans), craving for more followers and retweets to attain fame online would explain why people tweet more positively.

## How positive are positive people?

While we found that people are mainly posting positive tweets, how positive exactly are they?

{% include graph_positive_users.html %}

From this graph, we can see that the distribution of positive users skew towards low and moderate positive. This implies that positive tweets are not exactly screaming with joy and excitement 🤣 most of the time but perhaps more of a little giggle 😁 or a simple smile 🙂 .

## Do positives attract?

Would a positive person tend to follow other positive people? 

{% include graph_homophily.html %}

From what we found, users tend to follow other users of the same polarity! This means that a positive person is more likely to follow other positive people and a negative person is more likely to follow other negative people.

A closer look into a single user and his/her followees is presented below. The single user is represented as the middle node.

{% include graph_network.html %}

This network diagram allows us to visualise the 3 findings together. First, overall, there are more positive users. Next, positive users are mainly low or moderately positive. Lastly, users tend to follow others of similar polarity. As the user that we are focusing on here is positive, his/her followees are mainly positive with only 2 out of 51 followees that are of negative polarity.

## How did you do that?

To help you understand these results, here's how we gathered them.

The major tool we used in our research is tweepy (an interface to access Twitter API), NLTK (NLP tool) and TextBlob (NLP tool). Our data crawling and preprocessing can be divided into several steps:

* **Step 1:** Select all users from original dataset in the paper "Testing Propositions Derived from Twitter Studies: Generalization and Replication in Computational Social Science"  and check their last update time.
* **Step 2:** Select the users who are still active (posting tweets) in 2020 and get their recent tweets (up to 200). The information we get includes the ID of tweets, created time, retweet count, favorite count, full text and language.
* **Step 3:** Select the users who have at least 100 English tweets and label them valid users.
* **Step 4:** Get the followees list of valid users.
* **Step 5:** Get recent tweets (up to 100) of these followees. Select those who have at least 100 English tweets and their tweets.
* **Step 6:** Perform basic NLP processing on the full text of tweets for both followees and valid users. Use NLTK and TextBlob predefined sentiment analysis models to compute the polarity of each tweet.
* **Step 7:** Calculate the average polarity of each valid user and each friend. Match valid users to friends and calculate the average friends polarity of each valid user.
