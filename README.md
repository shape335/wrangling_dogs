# Wrangling Tweets from WeRateDogs Account
by Shan Jafri

The wrangling report and analysis report are [here](https://github.com/shape335/wrangling_dogs/blob/master/wrangling_act.ipynb) and [here](https://github.com/shape335/wrangling_dogs/blob/master/wrangle_report.ipynb)

# Introduction
In a world where data is abundent, gathering and cleaning data is necessary for any data scientist to extract valuable insights. The focus of this project is to gather data from multiple sources, assess dirty data and then clean the data. The final part of the project runs an analysis on the clean dataset. 

# Gather

In this project, data was gathered from three sources:

- The WeRateDogs twitter archive that was provided by Udacity as a csv file. 
- The image prediction file that was hosted by Udacity serves and downloaded programmatically using request libary 
- Using twitters API and python's tweepy library, any missing information from WeRateDogs twiiter archive such as retweet counts and favorite counts are gathered. The tweet IDs in the WeRateDogs Twitter archive will be use to query the Twitter API for each JSON structure tweet using Python's Tweepy library and in a file called tweet_json.txt file. Each JSON formatted tweet should be written to its own line in a text file and then read line by line into a pandas DataFrame.

# Assess
The gathered data has to be assessed for the range of the cleaning issues required. When assessing, the type of cleaning is broken into two categories, tidy and dirty data issues. Below are each data issue that need to be address.

## Quality

### Twitter_archive
- tweet_id should be a string instead of an integer
- timestamp column should be datetime data type
- 'Name' columns have incorrect names like 'a', 'such', 'None'
- rename columns 'text' = 'tweet_text', 'name' = 'dog_name', 'source' = 'source_application'
- in_reply_to_status_id/user_id, retweeted_status_id/user_id should be srings instead of float
- ratings_numerator/denominator, retweets, and favorites should be integers instead of floats

### Image_prediction
- Tweet_id should be a string instead of an integer
- Missing values from images dataset only 2075 entires
- Some tweet_ids have the same jpg_url
- Source columncan be cleaned

### json dataframe
- remove any duplicate tweet_id's

## Tidiness
- Merge all data tables together
- Dog description in columns instead of rows
- Too many columns in image prediciton could condense
- Only interested in unique ratings, no retweets
- Drop unnecessary columns and NaN rows
- retweeted_status_id/user_id should be dropped

Cleaning tidy data issues first is often the best way to start. When structral data issues are solved, cleaning quality data issues become simpler.

# Conclusion

Data wrangling skills are fundmental to anyone working with data. Nearly 80% of a data scientist time is spent wrangling data. If data wrangling is properly done, tons of time can be saved during analysis.

The wrangling report and analysis report are [here](https://github.com/shape335/wrangling_dogs/blob/master/wrangling_act.ipynb) and [here](https://github.com/shape335/wrangling_dogs/blob/master/wrangle_report.ipynb)
