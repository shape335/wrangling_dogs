# wrangling_dogs

In a world where data is abundent gathering and cleaning data is necessary for any data scientist to extract valuable insights. The focus of this project is to gather data from multiple sources, assess dirty data and then clean the data. The last step of the project is to show several insights from the clean data set.

# Gather
In this project, data was gathered from three sources:

The WeRateDogs twitter archive that was provided by Udacity as a csv file. The image prediction file that was hosted by Udacity serves and downloaded programmatically using request libary Using twitters API and python's tweepy library, any missing information from WeRateDogs twiiter archive such as retweet counts and favorite counts. The tweet IDs in the WeRateDogs Twitter archive will be use to query the Twitter API for each tweet's JSON data using Python's Tweepy library and store each tweet's entire set of JSON data in a file called tweet_json.txt file. Each tweet's JSON data should be written to its own line. Then we will read this .txt file line by line into a pandas DataFrame with (at minimum) tweet ID, retweet count, and favorite count.

# Assess
The gathered data has to be assessed for the range of the cleaning required. When assessing the gathered data, the types of cleaning is broken into two categories, tidy and dirty data issues.

# Quality
## Twitter_archive
tweet_id should be a string instead of an integer
timestamp column should be datetime data type
'Name' columns have incorrect names like 'a', 'such', 'None'
rename columns 'text' = 'tweet_text', 'name' = 'dog_name', 'source' = 'source_application'
in_reply_to_status_id/user_id, retweeted_status_id/user_id should be srings instead of float
ratings_numerator/denominator, retweets, and favorites should be integers instead of floats
Image_prediction
Tweet_id should be a string instead of an integer
Missing values from images dataset only 2075 entires
Some tweet_ids have the same jpg_url
Source columncan be cleaned

## json dataframe
remove any duplicate tweet_id's

# Tidiness
Merge all data tables together
Dog description in columns instead of rows
Too many columns in image prediciton could condense
Only interested in unique ratings, no retweets
Drop unnecessary columns and NaN rows
retweeted_status_id/user_id should be dropped
Cleaning tidy data issues first is often the best way to start. When structral data issues are solved, cleaning quality data issues become simpler.
