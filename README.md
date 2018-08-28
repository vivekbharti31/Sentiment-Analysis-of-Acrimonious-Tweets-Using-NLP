# Advanced Python for Data Science
## Team 3 - Vivek, Anshul, Mayank
## Final Project
### Sentiment Analysis of Acrimonious Tweets using NLP

We are providing a ipynb file for the code that we used for the project In addition to this we are also sending the tweetcollector.py file that contains the code that fetches the tweets from the twitter API.

The code of the ipynb (which is the file having the code for the complete analysis) can be logically divided into the following parts:

### 1. Data Loading and Data Cleaning:
This part takes care of loading the tweet data into the system and getting the data ready for feading into the NLP model.

### 2. NLP Model:
This part has the model that we ran for our sentiment analysis. We are using Spark NLTK library to break the sentences into words and tagging the words. After doing the POS tagging which stands for Part of Speach tagging on the words of a tweet we will tag different words based on the 5 dictionaries 
that we are feeding into our system.
We are having the folowing dictionaries in our system:- negative words, positive words, incremental words, decremental words and inverse words
the weights for each word in the dictionaries are as follows: negative words: -1, positive words: +1, incremental words: *2, 
decremental words: /2 and inverse words: *-1.
using the above dictionary the model calculates the sentiment score of a sentiment and we finally get the overall 
sentiment score. A positive sentiment score is taken as a positive tweet and a negative is taken as a negative tweet.

### 3. Final processing of output data and joining it with crime report data:
Here in this part we are defining some columns that we used in our analysis for example: severity_index which shows the severity of the tweet. In this part we also upload the crime report data and perform fuzzy string matching between between the output negative tweets data and crime data. Since we don't have any common IDs between the crime data and tweets data we have to perform fuzzy string matching on twitter username + location and criminal name + location. We are picking a fuzzy score above 90% as a match. We are also defining alert status which is based on the users with high and med severity tweets and who don't yet have any criminal status.

### 4. Visualizations:
In this section we for the final summaries and visualizations. we have prepared visualization using python and tableau.

This is the overall division of the code and an overall explanation of the flow of the code. We have tried to put in as much comments into our ipynb file as possible and have tried to make as self explanatory as possible.