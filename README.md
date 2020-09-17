# Udacity_DataScientist_Capstone
Project done as final part to DataScience Project
## Overview
This project is part of Udacity data science final assignment.
Sparkify is a digital music service. Users uses services provided by this platform either as a free tier user with advertisements or using premium subscription paying monthly fees.
Users can upgrade, downgrade or cancle there services anytime.

We created a machine learning model which is able to predict when a user has most probability to churn.
key events explored in analysis and the ML model is based on
* Cancel
* Submit Downgrade
* Thumbs Up
* Thumbs Down
* Add Friend
* Next Song
* Help
* Error
## Data Cleaning and Exploration
The mini dataset we have contains missng/null values. So replaced nan values.
<pre>
Data columns (total 18 columns):
artist           228108 non-null object
auth             286500 non-null object
firstName        278154 non-null object
gender           278154 non-null object
itemInSession    286500 non-null int64
lastName         278154 non-null object
length           228108 non-null float64
level            286500 non-null object
location         278154 non-null object
method           286500 non-null object
page             286500 non-null object
registration     278154 non-null float64
sessionId        286500 non-null int64
song             228108 non-null object
status           286500 non-null int64
ts               286500 non-null int64
userAgent        278154 non-null object
userId           286500 non-null object
dtypes: float64(2), int64(4), object(12)
</pre>

Created columns with numaric values for predicting churn based on values of "Cancellation Confirmation" and "Downgrade".
Created values for platform of OS and browser.  
<pre>
+-------+-----------+  
|browser|user_counts|  
+-------+-----------+  
| Chrome|        117|  
|Firefox|         50|  
| Safari|         46|  
|     IE|         12|  
+-------+-----------+  

+--------+-----------+  
|platform|user_counts|  
+--------+-----------+  
| Windows|        111|  
|     Mac|         86|  
|  iPhone|         13|  
|   Linux|         12|  
|    iPad|          3|  
+--------+-----------+  
</pre>
## Feature Engineering
We worked on getting the customer behaviour and customer feature values and tried to convert it into scaler and numerical values for testing and training.


## Modelling
The ML models we build on are:
* Logistic Regression
* Random Forest Classifier
* Gradient Boosting Trees


After running each model on the test set we got below results:

### Logistic Regression
<pre>
Accuracy for Logistic Regression Model is:  0.5
F1 score for Logistic Regression model is :  0.5494505494505495
</pre>
### Random Forest Classifier
<pre>
Accuracy for Random Forest Model is:  0.6
F1 score for Random Forest Model is:  0.6333333333333333
</pre>
### Gradient Boosted Trees
<pre>
Accuracy for Gradient Boosting Tree Model is:  0.8
F1 score for Gradient Boosting Tree classifier is :  0.819047619047619
</pre>
## Results

Once we realise that Gradient Boosting Tree models was best for our use case we ran it on the train set and below was the summary we got on the feature importance:
<pre>
 	feature_importance 	columns
0 	0.145972 	count_thumbs_down
1 	0.201630 	count_thumbs_up
2 	0.044333 	count_errors
3 	0.129566 	count_help
4 	0.183375 	count_add_friend
</pre>
Considering this is only a quit mini dataset and our purpose is scaling this up to the total 12G dataset, and also we may be able to add more parameters for test and train like customer location we may have different output from each of the above model and even we may have to look for other models that may provide better results.


# Files
* README.md
* mini_sparkify_event_data.json
* Sparkify.ipynb/html

## Installation
Python 3.6
PySpark
Jupyter

## References
Pls have a look at the page on medium at :
https://medium.com/@acharyamudumbi428/dont-loose-your-user-270ffb27b04b
