# Twitter Trends Analysis

###### Collection of 10K tweets on a top trending hashtag in Hyderabad
##### Notebook File - 'precog_twitter.ipynb'
##### PDF - 'Twitter_Analysis.pdf' (For most of the plots)
###### Please run the local host app to see interacrive graphs (see How to Run)
##### Tweet Data - 'tweet_data.json'
##### User data - 'user.json'

The hashtag chosen was '#INDvsAUS' as that is what was obtained during the time of coding. Some of the important tools/libraries used in the project are :-

- Tweepy
- Twint
- Dash
- Jupyter-Dash
- Plotly
- 

#### Details about the Implementation
- The top hashtag was obtained using tweepy's trends_place method and hyderabad was chosen as the location
- The hashtag is '#INDvsAUS'
- The tweets were collected and stored in a json file 'tweet_data.json'
- The tweets were stored as each tweet being a twint tweet object stored as a json object which has fields : {"id": , "conversation_id": , "created_at": , "date": =, "time": , "timezone": , "user_id": , "username": , "name":, "place": "", "tweet": , "language": , "mentions": , "urls": , "photos": , "replies_count": , "retweets_count": , "likes_count": , "hashtags":, "cashtags": , "link": , "retweet": , "quote_url": , "video": , "thumbnail":, "near": , "geo": , "source": , "user_rt_id": , "user_rt": , "retweet_id": , "reply_to": , "retweet_date": , "translate": , "trans_src": , "trans_dest": }
- The tweets were collected using twint command line = **twint -s "#INDvsAUS" --limit 11000**
- The users were also collected as tweepy user objects in a json file 'user.json' with fields : {"Name":,"Followers":,"Verified":,"Friends":,"Location":,"Tweets"}
- Both these json files were stored in dataframes and then used
- The user_words.txt file stores the collected text data of top 10 tweets tweeted by each user in his/her timeline , which were collected using tweepy's timeline method
- 'wc.png' is a plot image(wordcloud) which is loaded in the code

#### Plots/tables (run the notebook file for these)
- Number of tweets per Date of December 2020(from 8 Dec to 17 dec)
- Number of tweets distribution according to time of day(morning , afternoon , evening , night) (in heat map)
- Number of tweets according to language(pie chart)
- Sentiment analysis of the tweets - Positive/Negative/Neutral tweets , Subjectivity , Polarity (Scatter graph and Pie charts)
- Most tweeted words by users
- Number of Users in different followers range
- Number of users in different tweets per user range
- Verified/Unverified Users(Pie chart)
- Top 3 Positive/Negative tweets

#### How to run

- Start a new conda env with the necessary packages by - **conda env create -f precog.yml** (recommended)
- Or start a conda environment and install from requirements.txt by - **pip install -r requirements.txt**
-  You can also make a normal venv or pipenv an then install by **pip install -r requirements.txt**
- After any of these steps it might ask you to do some jupyter builds(for jupyter dash) so that the plots are visible on the notebook , please follow that , or do the following steps :- 
    - pip install jupyter-dash (already done in the above step)
    - jupyter lab build 
    - pip install jupyterlab "ipywidgets>=7.5  (to be able to see the plotly figures)
    - jupyter labextension install jupyterlab-plotly@4.8.2 (to be able to see the plotly figures)
- Please note that if any individual package still doesnt work then its best if you install it manually by looking at the import statements
- You can correctly install a package using /path/to/python -m pip install <package name>
- This /path/to/python can be obtained for your environment by :- 
    - import sys
    - print(sys.executable)
  

#### Note
- This script actually runs a Dash app
- This app can either be run inline(default mode) , or on a local host if you remove 'mode = 'inline'' from app.run_sever
- ### **Please visit the local host app or inline to see the interactivity of the graphs**
