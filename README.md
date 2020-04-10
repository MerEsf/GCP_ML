## Binary Classification, Returning Customers (BigQuery)

### Objective:

Predict and rank the probability that a visitor will make a purchase

### Data:

Google Merchandise Store ecommerce dataset 
https://support.google.com/business/community?hl=en&ctx=lithium

### Steps:

a) Query and explore the ecommerce dataset

b) Create a training and evaluation dataset to be used for batch prediction

c) Create a classification (logistic regression) model in BQML

d) Evaluate the performance of your machine learning model

e) Predict and rank the probability that a visitor will make a purchase

## Evaluation:

Minimize the False Positive Rate (predict that the user will return and purchase and they don't) and maximize the True Positive Rate (predict that the user will return and purchase and they do).

## Feature Engineering:

There are many more features in the dataset that may help the model better understand the relationship between a visitor's first session and the likelihood that they will purchase on a subsequent visit.
Add some new features and create a second machine learning model called classification_model_2:

•	How far the visitor got in the checkout process on their first visit

•	Where the visitor came from (traffic source: organic search, referring site etc..)

•	Device category (mobile, tablet, desktop)

•	Geographic information (country)

A key new feature that was added to the training dataset query is the maximum checkout progress each visitor reached in their session, which is recorded in the field hits.eCommerceAction.action_type. 

## Prediction:

The predictions are made on the last 1 month (out of 12 months) of the dataset.

The model outputs the predictions it has for those July 2017 ecommerce sessions. We can see three newly added fields:

•	predicted_will_buy_on_return_visit: whether the model thinks the visitor will buy later (1 = yes)
•	predicted_will_buy_on_return_visit_probs.label: the binary classifier for yes / no
•	predicted_will_buy_on_return_visit.prob: the confidence the model has in it's prediction (1 = 100%)

## Results
•	Of the top 6% of first-time visitors (sorted in decreasing order of predicted probability), more than 6% make a purchase in a later visit.
•	These users represent nearly 50% of all first-time visitors who make a purchase in a later visit.
•	Overall, only 0.7% of first-time visitors make a purchase in a later visit.
•	Targeting the top 6% of first-time increases marketing ROI by 9x vs targeting them all!

