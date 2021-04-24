# **Bitcoin daily Price Movement predication Using Twitter Sentiment Analysis**

\_By Faridoon Farahi\_

# **Problem Statement**

This project is aimed at predicting the daily increase or decrease in the price of bitcoin using Twitter sentiment analysis.

# **Overview**

For this project I will be looking at the tweets of the 70 most influential in the world of cryptocurrencies and see how their tweets and sentiment towards Bitcoin affects the price of Bitcoin. While there are many cryptocurrencies present today, including the likes of Ethereum and Ripple, Bitcoin is chosen for this project. While it can be argued that there are many reasons why Bitcoin should be chosen and many why it should not be chosen, there are few key facts that influenced my decision. For starters, Bitcoin is arguably the most popular cryptocurrency to date which is evident by its nickname &quot;The King of Cryptos&quot;. Bitcoin became popular when people started looking towards it as a digital asset rather than a digital currency as started investing in it as such. This led to Bitcoin being extremely popular. However, this also contributed to Bitcoin&#39;s volatile nature, which is another reason for choosing Bitcoin as the cryptocurrency for this project. Another huge factor for choosing Bitcoin is the availability of historical Bitcoin price data.

**File Structure**

├── README.md

├── data/

├── Presentation/

└── final\_capstone.ipynb

The `data/` directory is where the `csv` files are stored after being collected.


# **Executive Summary**

Bitcoin is a decentralized digital currency which was first introduced in 2008 by an unknown person who goes by the alias of Satoshi Nakamoto. To predict the price of Bitcoin, online tools and platforms are used. One such tool is Twitter, a social media tool that allows people to post &quot;tweets&quot; which are short messages. By using Twitter people can express their opinions and sentiments about various objects, including Bitcoin. Due to this reason, Twitter is chosen as sentiment analysis platform. The project uses the tweets of the 70 most influential people in the world of cryptocurrencies for analysis to try to predict the price of Bitcoin based on their sentiment. Lexicon based approach is used for sentiment analysis which uses a dictionary of words, where each word has a semantic score. To calculate the sentiment scores, VaderSentiment, a python library is used. VaderSentiment has its own dictionary of words, however since these words are assigned sentiment scores based on no specific context, thus the dictionary is useless to for this project. Instead, a unique dictionary of words with semantic scores dedicated to Bitcoin is developed and used. The formula used for scoring is (close price – open price)/|max|. This dictionary is then passed to VaderSentiment to calculate the sentiment scores of each tweet. VaderSentiment assigns each word a score in the range of -4 to 4. The sentiment score of tweets is a sum of all the score of all the words in a sentence and then is normalized to range of -1 to by using the formula x/√((x^2+α) where α=15. Moving average is also used as features in addition to the sentiment. K Nearest Neighbor, Logistic Regression Multi-Layer Perceptron Classifier and Support Vector Machine Classifier are the algorithms chosen for this project based on their ability to deal with overfitting and performing well on data without noise and of these three, MLP performed the best with accuracy result of 96%.


# **Challenges**

Using social media for sentiment analysis has its own problems and challenges. One of the challenges is the ambiguity of language. The ambiguity can rise due several factors, for example it can be quite challenging and sometimes difficult to figure out the object that is being talked about. For example, a tweet has the text &quot;It will rise&quot;. While the tweet mentions something will rise, there is an ambiguity with the subject of the text. The context is unclear as the text could be referring to increase in temperature or could simple be referring to a balloon rising in the air after it is let go. It could be talking about the price of a stock (which stock?) or could be talking about a revolution. Similarly, it could be talking about the price of Bitcoin, or could be talking about the inflation in a country. Thus, the ambiguity of language is a challenge and could be difficult to deal with.


# **Tweet Gathering**

Itsamishra&#39;s web scrapping python script is used as a base script for downloading the recent scripts for the top 70 most influential people in the world of cryptocurrency. The script downloads ~3240 most recent tweets for all the individuals and stores the data in a comma separated file, or a csv file. The csv file allows to store data in tabular form, making it easier to read and interpret the data. The script is written to download the most recent ~3240 tweets for every person on the list of top 70 influential people in the world of cryptocurrency and create a csv file for each person containing the tweets, time each tweet is created, and a unique id column is added to each file.

Certain changes needed to be made to the script. To use Twitter API to download tweets, own unique access and consumer keys are needed. Using twitter account, request token needs to be generated with unique access and consumer keys which are then used to get the script running. Second, the script is written so that there are blanks spaces between 2 rows in the csv file. This is not a problem in older version of python, i.e. python 2 (which the Itsamishra used), but does present a problem in newer versions of python (Python 3) while reading the files. Python 3 throws error when blank spaces being present, so each trailing blank space needs to be removed.


# **Conclusion**

From the results above we can see that incorporating time series with sentiment scores lead to significantly better results as compared to just using sentiment scores. The models were performing poorly when just the sentiment scores were used. However, with the power of feature engineering in terms of time series improved the performance of all our models. We can further look at the importance of the engineered features when they were used without sentiment scores as results were significantly better as well. However, the hybrid approach of combining sentiment scores with engineered features proves to provide the best of both worlds as it allows us to achieve even better results.

Since the goal of the project is to try to find a relationship between the Sentiment of the 70 most influential people in the world of cryptocurrencies, hence the approaches of CountVectorizer and TFidfVectorizer are not used and instead Sentiment Scores calculated using VaderSentiment are used.

Moreover, while feature engineering is used to create time series like features, it is important to note that time-series models such as Auto Regressive (AR), Auto Regressive Moving Average (ARMA) and Auto Regressive Integrated Moving Average (ARIMA) models that are widely used for time-series problems are not used and instead traditional Machine Learning models are used. This is because some people are more active on Twitter as compared to others. This, however, does not mean that the people who are more active Tweet frequently. In fact, not everyone tweets daily or very frequently. This could result in the problem where we have periods of time where there are no tweets. In such case, time-series models may not perform well since they rely on the immediate previous value(s), data for which could not be present as none of our 70 influential people tweeted in a particular time.