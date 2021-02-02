##  WeRateDogs in Twitter 
### Introduction 
WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. And the numerators almost always greater than 10, because "they're good dogs Brent." These data would be gathered, then perform assessing and cleaning, finally visualizing the results and communicating the findings.

#### Data gathering:
In this project, the data was collected through different sources.  The twitter_archive_enhanced file downloaded directly contains basic tweet data (tweet_id, rating, name and dog stages) from twitter users. Additional data including retweet count and favorite count ,was obtained via  the Twitter API. Finally, the image-prediction file  was  downloaded programmatically using the Requests library and provided URL. This file provided the dog image links and the prediction results based on neural network algorithms.

#### Data assessment  
After import to jupyter notebook as pandas’ dataframe. All files are assessed visually and programmatically. The main problems are listed:\
**Quality issues**\
Erroneous data types across all three tables (eg: twitter_id, id, id_str should be str but not float)\
 Missing or inaccurate values (eg, name in table twitter_archive_enhanced  )\
Some denominators are equal 0\
Columns with no or very few values (eg, 'in_reply_to_status_id', 'in_reply_to_user_id', 'retweeted_status_id’)\
Inconsistence: Mixed lowercase and uppercase characters in dog breed name (p1,p2,p3)\
**Tidiness issues**\
For table ‘twitter_ archive_enhanced ’, four variables (doggo, floofer, pupper, puppo) should be in one column as Dog_stage\
All three tables should be combined before analysis

#### Data Cleaning
**Quality issues**\
Erroneous in data types, astype () method was employed to correct the data types\
Missing names may not be able to re-extracted or found. \
For the inaccurate rating number, if the accurate values could not be found, drop all those rows. \
Using upper or lower () method to change the dog breed name\
Drop all those columns without values\
**Tidiness issues**\
Reorganized  all four dog stages columns as one \
Using merge method to combine all three tables based on tweet_id

#### Insights 
Twitter provides a unique rating system to evaluate the popularity of WeRateDogs. According to the above data, the average of  rating is 12/10. In addition, we count the favorite and retweet times, the average count for them is 132810 and 79515 separately. 
More than that, WeRateDogs have been described by specific dog stages, such as doggo, pupper, puppo and floofer. As we can see from the bar chart, pupper is the mostly used.
One more cool thing, these dogs could be predicted by ran every image in the WeRateDogs Twitter archive through a neural network that can classify breeds of dogs. Surprisingly, the Image prediction successful rate could be more than 70%.  
 

