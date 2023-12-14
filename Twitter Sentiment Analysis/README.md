Bitcoin Daily Price Prediction Using Twitter Sentiment Analysis
By Faridoon Farahi
Problem Statement
This project aims to predict daily changes in Bitcoin's price by analyzing Twitter sentiment.

Overview
The focus is on the tweets of the top 70 influencers in cryptocurrency. The project explores how their opinions about Bitcoin on Twitter impact its price. Bitcoin is chosen for its popularity and the availability of historical data. Despite the presence of other cryptocurrencies like Ethereum and Ripple, Bitcoin's prominence as "The King of Cryptos" makes it a prime candidate for this study. Its popularity, volatile nature, and extensive data availability are key reasons for its selection.

File Structure
README.md
data/ - The 'data/' directory stores the collected CSV files.
Presentation/
final_capstone.ipynb
Executive Summary
Bitcoin, introduced in 2008 by Satoshi Nakamoto, is a decentralized digital currency. This project uses Twitter, where people share short messages called "tweets," to gauge sentiment about Bitcoin. The sentiment analysis focuses on the tweets of the 70 most influential figures in cryptocurrency. A special dictionary dedicated to Bitcoin sentiment, combined with the VaderSentiment Python library, is used to score tweets. The project employs several machine learning algorithms, with the Multi-Layer Perceptron Classifier showing the highest accuracy.

Challenges
Sentiment analysis using social media is tricky due to language ambiguity. A phrase like "It will rise" can have many interpretations, making it challenging to pinpoint its exact meaning or context.

Tweet Gathering
The project uses a modified version of Itsamishra's web scraping Python script to collect recent tweets from influential cryptocurrency figures. These tweets are stored in CSV format. Modifications to the script include accommodating Twitter API access requirements and addressing compatibility issues with Python 3.

Conclusion
Combining sentiment scores with time series data significantly improved model performance compared to using sentiment scores alone. While the project focuses on sentiment analysis and does not utilize time-series-specific models, the hybrid approach of combining sentiment with engineered features yields better results.
