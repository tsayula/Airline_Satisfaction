# Airline_Satisfaction
By: Edgar Gonzalez & Lera Tsayukova

![pexels-alex-pham-950225](https://user-images.githubusercontent.com/75099138/123377428-13269280-d55a-11eb-8637-427595f244da.jpg)


Phase 3 Project

# Summary
This project examines airline satisfaction data, in order gain insight about what factors determine overall customer satisfaction. 
This repo is broken into several parts. The EDA notebook outlines the data exploration process; it examines the raw data set, engineers new features, and goes through the cyle of creating a series of models and testing the data using those models.  The Prediction Notebook utilizes the findings and features from the EDA notebook in order to create predictions for a holdout data set of airline data to see how accurately the best model can predict airline satisfaction on unseen data.

### A) About the Data:

Our Dataset came from Kaggle, although the airline source chose to remain anonymous. There were approximately 130,000 observations in the dataset, with 23 feature columns and 1 binary target column.

### B) Our Business Problem:

-To understand which features have the greatest impact on overall customer satisfaction

-Inferential : Understand relationship between X- features & Y- target.
After evaluating our dataset we concluded that our business problem, was more inferential and less predictive. 

In other words, we want to understand how customer satisfaction is influenced by various factors such as age, leg room, gender, inflight service etc. 

We care less about accurately predicting how satisfied a person will be according to their experiences, and care more about what factors affect that experience.

This is due in large part to the level of influence that the airline has over most of these factors. While age, gender, and flight length are factors which are static variables, airlines can in part always do more to improve certain metrics such as seat comfort, boarding experience, check-in etc, and thus attract more customers, increasing sales revenue. Thus leading us to an inferential model as opposed to a predictive one.​

### C)Who would care: 

-Boardmembers

-Stakeholders

-Competitors (other Airlines)



## I. Data Prep and EDA Useful findings 

### Data Preparation and EDA Steps

1) Prep the data by: 

  -Dropping unnecessary columns
  -Checking for null/missing values
  -Imputing those values 

2) Exploratory Data Analysis (EDA): 
  
  -Binning Continuous Features
  -Age, Flight Length
  -Dummying Categorical Data
  
 

##### Target Variable
Target: Binary Variable: "satisfied" "dissatisfied/neutral"
-How its measured
  -Satisfied- 1, 
  -Dissatisfied/Neutral- 0
-Breakdown:
44%  of Respondents Satisfied 
56%  of Respondents Dissatisfied/Neutral
![bathrooms scatterjoin]


#### Our Models: 
Ulimately because our problem was inferential, decided to stick with models which were less black box . We opted to run Logistic Regression, a decision tree, and simple Random Forest Classifier, and then a RFC using Grid Search. 

-We ran over 300 models, with our evaluation metric as accuracy and precision as our evaluation metrics.   

<img width="397" alt="Screen Shot 2021-06-24 at 2 53 32 PM" src="https://user-images.githubusercontent.com/75099138/123440315-a387c600-d5a0-11eb-9aac-30dd394b5df8.png">


#### I. Baseline Model: Dummy Model 
![dummy_cm](https://user-images.githubusercontent.com/75099138/123441609-0cbc0900-d5a2-11eb-8420-17b1935e3096.png)
-The metric you see here is a confusion matrix for our baseline model- our dummy classifier. This model predicted the majority class – Dissatisfied – every time.
-This baseline model offered us a consistent metric to determine improvement in our scores moving forward.

#### II. Logistic Regression, Decision Tree Classifier, Random Forest

After running all of our models, we were able to determine the ones which performed best according to their respective accuracy scores, between the training data and the testing data. The testing data scores were especially informative as they informed us which models were overfitting, and how well would they ultimately predict on unseen data.
<img width="397" alt="Screen Shot 2021-06-24 at 2 53 32 PM" src="https://user-images.githubusercontent.com/75099138/123442184-9cfa4e00-d5a2-11eb-8b30-356009533e28.png">

-After running a Logistic Regression Model, a Decision Tree Classifier, and a Random Forest model, we determined that our Decision Tree Model was doing a little too well, with the conclusion that it was overfitting. Thus, we chose the Random Forest model using parameters from our Grid Search. 

- Below is a confusion matrix which shows the performance of our best model. 
- ![cm_2](https://user-images.githubusercontent.com/75099138/123444296-be5c3980-d5a4-11eb-87cb-cd3920e8b4d3.png)


## III. Evaluating Feature Importance using RFC
![Feature_importance](https://user-images.githubusercontent.com/75099138/123444330-c7e5a180-d5a4-11eb-9f00-cbc47f2e6385.png)



A) Online Boarding
Here we take a closer look at online boarding experience. This category was rated in the survery from 1-5, and very readily we can see a strong correlation between this feature and average customer satisfaction. Less than 20% of customers who rated online boarding as poor were satisfied overall, while those who rated online boarding as a 5 were on average over 80% satisfied. 
![Online_boarding](https://user-images.githubusercontent.com/75099138/123444360-cddb8280-d5a4-11eb-941f-796ca9420577.png)

B) Inflight Wifi, Inflight Entertainment
This category was rated in the survery from 1-5, and very readily we can see another strong relationship between this feature and average customer satisfaction. Those customer who were on average more satisfied rated wifi and entertainment rated these features as 4 or 5. With the inverse being true.

![Inflight_wifi_service](https://user-images.githubusercontent.com/75099138/123444376-d469fa00-d5a4-11eb-8887-1c13c94178cb.png)
![Inflight_entertainment](https://user-images.githubusercontent.com/75099138/123444392-d8961780-d5a4-11eb-877b-63090d084a6d.png)


C)Type of Travel
Here we see a large imbalance between Travel Class and average satisfaction which is shown on the left hand side. This is more intuitive and less suprising. 
![Type_of_travel](https://user-images.githubusercontent.com/75099138/123444414-dd5acb80-d5a4-11eb-89a6-719d36ddf78c.png)



## IV. Conclusions/Recommendations
-Focus on Online Booking 

- Strive to provide/ boost Inflight Wifi

- Improve availability of Inflight Entertainment

We have created a fairly precise classification model with over 90% accuracy in predicting customer satisfaction, for airlines to identify critical chokepoints to raise passenger satisfaction. We recommend that airlines should focus primarily to improve Online Boarding. Throughout our models this have proven to be a critical factor for customers. Futhermore we recommend improving on inflight amenities, with special emphasis on  Inflight Wi-Fi Service experience. While implementing  inflight entertainment still proves to have difficulties, with improved or free access to wi-fi, airlines can ensure that more economy class customers can enjoy the service. In this way, while not every passeneger can afford to fly business class, it can ensure a more satisfactory customer experience. 




 
### Repository 
-READ.me

-data

-visuals

-Project Notebook.ipynb

-Airline_Satisfaction.pdf
