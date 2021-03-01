# Data-Analysis-Nanodegree-Wrangle-and-Analyse-data
## Introduction
Real-world data rarely comes clean. Using Python and its libraries, I will gather data from a variety of sources and in a variety of formats, assess its quality and tidiness, then clean it. I will document my wrangling efforts in a Jupyter Notebook, plus showcase them through analyses and visualizations using Python (and its libraries) and SQL.

## Dataset
The dataset that I will be wrangling (and analyzing and visualizing) is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs. WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. The numerators, though? Almost always greater than 10. 11/10, 12/10, 13/10, etc. Why? Because "they're good dogs Brent." WeRateDogs has over 4 million followers and has received international media coverage.

## Wrangle_report
For this dataset, I used the tweet archive data obtained from the Twitter user @dog_rates,from 2015-2017. WeRateDogs has over 4 million followers and has received international media coverage.

### Gathering data
I started by gathering three datasets from three different sources as described below.

#### The WeRateDogs Twitter archive
This data comes from a csv files that contains basic information, including user id, timestamp and retweet information that is downloaded from the project website. I used pd.read_csv to extract this data.

#### The image prediction tsv file
This data comes from a tsv files that predicts the dogs breed using a neural network. This tsv file was extracted using url from the Udacity server using request.gets(url)

### Accessing data
By visualizing the datasets in general and sampling some data in depth, I checked the quality and tidiness of the datasets. Quality issues: completeness, validity, accuracy, consistency 

#### Access data from tweeter API
For this data, I accessed and stored each tweet's retweet count and favorite information to tweet_json. To access the information, I setup tweepy to authenticate with Twitter credentials using tweepy.OAuthHandler and created the api to connect to twitter with my account.

### Cleaning data
Looking through the issues that were identified, I rearrange the issue by the time required to solve. For example, I first changed the datatype of tweet id so I can merge the three datasets. After merging the three datasets, I can avoid some repetitive work, such as gettting rid of unwanted columns and removing replicates. Then I combined columns with same type of information and also added in some data for later analysis. I also make a different copy for some step so that I can easily retrieve some data if any mistakes were made in a intermediate step.

Change all id to str object
Get rid of columns that won't be used for analysis
Change all time column to datetime object
Since some tweets did not have images ( and has NaN values for expanded_urls ), should remove those data.
There are some numbers that doesn't make senses (out of range) for the denominators and numerators.
There are decimal numbers in the rating, which are wrongly interpreted and need to be changed manually
There are duplicated images in the image prediction (and there are images that are not dogs)
There are repetitive columns (such as id and id_str, in_reply_to_status_id and in_reply_to_status_id_str )
Tidiness issues:

For twitter archive: the 4 stage columns (dogger, floofer, pupper and puppo) can be reduced to one columns
There are columns that shows none, instead of NaN. Should be make consistent.
For image prediction, combine the confidence columns.
Should merge all three datasets by tweet id.


In conclustion, during this process, I learnt several tools for data wrangling. Also, I familarize myself with many sources of help, such as Udacity, stackoverflow and github.
