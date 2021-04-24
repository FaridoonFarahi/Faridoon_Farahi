# Distinguishing Between Videogames and Boardgames Subreddits
_By Faridoon Farahi_

### Problem Statement
This project is aimed at predicting the subbredit categories for different comments belonging to categories of boardgames and videogames

For this project, I have used boardgames and videogames as subreddits. This is done not randomly but rather on purpose since I wanted to explore how the classificaiton algorithms will perform on similar data.



### File Structure
```
.
├── README.md
├── data/
├── Project_3_Presentation
└── Project_3
```

The `data/` directory is where the `csv` files are stored after being collected through the Reddit and Pushshift APIs. This is done after the process of data cleaning.


### Executive Summary
For data collection phase, 1000 latest comments for each subreddit are collected using the official reddit API. These 1000 comments for each subreddit excluded those comments which either did not include any comments or were removed or deleted.

World clouds and word frequencies are used to explore the data for each of the subreddits. The word cloud shows us frequency of the word occurance : the most occuring words with big font while showing the least occuring words in a very small font. Word frequency dictionary is created to see how many times each word appears in each of the subreddit comments.

For modeling, seven different classification algorithms are used. To do this, first the two datasets are combined into one.  Only the comments are used as features. Each comment is tokenized, stemmed and has all the stopwords removed. Then the combined dataset is split into train and test sets with 75/25 split ratio. Two different methods of vectorization are used namely CountVectorizer and TfidfVectorizer. After the train and test sets have been transformed using the vectorizers, the classifiers are fit to the data. The performance of the classifiers are evaluated on the basis of Accuracy, True Positive Rate and True Negative Rate. Classifiers used are Bernoulli Naive Bayes, Gaussian Naive Bayes, Logistic Regression, Random Forest, K-nearest neighbors classifier, Support Vector Machine and Extra Tree Classifier.

Logisitc Regression performed the best with an accuracy of 85%. I recommend using Logisitic Regression for classification of subreddit comments, epsically those belonging to `boardgames` and `videogames`