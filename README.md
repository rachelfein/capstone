# New Orleans Airbnb Analysis
 
### Exploratory Data Analysis and Machine Learning Predictive Model
---
**Author:** Rachel Fein
 
This analysis was completed for Sarah Alter, a private investor, for the purpose of helping Ms. Alter gain a better understanding of New Orlean’s short term rental market as she prepares to invest. Ms. Alter’s goal is to use this analysis and predictive model as a metric to help her decide what property would be the best for her investment. This analysis aims to use exploratory data analysis (EDA) as well as develop a predictive model for the nightly rate of short term rental properties.

Machine learning was used to develop a predictive model for nightly rate. The analysis showed that there is enough good data to develop a well performing predictive model that correctly predicts the nightly rate within $2.02. Having a well performing predictive model will prove helpful when comparing properties to buy and help determine not only the price point per night one should expect but also intuitively help decide what price point the property should be around to reach the return on investment (ROI) that works for you. 

The exploratory data analysis goal is to assist in making general observations about New Orleans' short term rental market, that can aid in gaining a better understanding of the features of well performing rentals, such as neighborhood, property type, number of bedrooms, and room type. Getting a better grip on the characteristics of the New Orleans market can help narrow down search criteria and properties. Through EDA the neighborhoods that had the most airbnbs and which neighborhoods had the most expensive rentals were able to be pinpointed. EDA also gave insight on which neighborhoods are the most booked, which is a critically important characteristic when picking where to invest.   
 
## Business Problem
---
This analysis was completed for Sarah Alter, a private investor, who is interested in expanding her vacation rental portfolio to New Orleans, LA. Alter is new to the New Orleans vacation rental market and wants to use this analysis as a guide as she starts her search for a new property. To help Alter reach her goal, exploratory data analysis is used to get an overview of the market. This analysis also provides a predictive model for nightly price. A predictive model will help Alter reach her goal by giving her a metric to compare properties currently on the market based on the property’s features. While EDA gives Alter a general understanding of what features seem to stick out in well performing rentals and neighborhoods. 
 
## Data
---
The dataset in this analysis comes from [Kaggle](https://www.kaggle.com/datasets/ruthgn/new-orleans-airbnb-listings-and-reviews), however it is noted by the Kaggle User who uploaded the dataset that they pulled the data originally from [Inside Airbnb](http://insideairbnb.com/new-orleans/). The dataset was compiled on November 7, 2021 and all time oriented variables in this dataset are based around that date. The dataset contains 6,028 Airbnb listings in the city of New Orleans. 
Only features that pertained to the business problem were used in this analysis. As well as a few additional features were removed when the analysis showed specific features were too highly correlated with each other. A detailed description of each feature can be found in [Exploratory Data Analysis notebook](./Exploratory_Data_Analysis.ipynb). The predictive model used 12 continuous features and 8 categorical features. After encoding the 8 categorical features there was a new total of 122 categorical columns, for a total of 12 continuous features and 122 categorical columns.
The dataset originally started with 6,028 Airbnb listings, after data cleaning and preprocessing 5,298 listings remained. During eda it was found some listings had to be removed after noting the data seemed to be illogical or the listing had too much missing important data. The dataset also contains extreme outliers in many of the continuous features. Outliers were removed before building the predictive model. Further explanation for removing specific listings can be found in the Data Cleaning section of the [Exploratory Data Analysis notebook](./Exploratory_Data_Analysis.ipynb).
 
## Methods
---
During data preprocessing, outliers were removed, categorical data was encoded, skewed columns were transformed, and the data was standardized. Outliers were removed using the IQR method. Categorical data was encoded using OneHotEncoder and OrdinalEncoder both from feature_engine. Skewed columns were transformed using the Box-Cox method in PowerTransformer from Sklearn. The data was standardized using StandardScaler from sklearn. 
 
Data modeling was performed in the [Model Notebook](./Model.ipynb). A baseline model was created and future models were compared to the baseline model to determine if the model’s performance was being improved. The main performance metric used to evaluate the success of the model was the Root Mean Square Error. The Mean Absolute Error and Mean Square Error were also viewed for each model to help gain a better understanding of its performance. Multiple different types of models were run and GridsearchCV was used to attempt to improve the models. Feature selection was implemented on the two best performing models (Linear Regression and Random Forest). Feature selection methods implemented were ANOVA, Lasso, and using only features of top importance determined by the coefficients. 
 
 
 
## Results
---
The goal of this analysis was to gain information about the New Orleans short term rental market using exploratory data analysis and develop a machine learning price predictive model that Ms. Alter could be used as an aid while searching for an investment property.

The exploratory Data Analysis (EDA) proved to find general relationships among the data to get a grasp on the New Orleans short term rental market. Some highlights from EDA are shown below:

<div>
<img src="Images/heat_map_most_airbnbs.png" width=400/>
</div>

Knowing where the most densely populated areas are for airbnbs give a lead to the best neighborhoods to purchase an Airbnb. Now that the areas are known, this information can be used to further investigate why investors continually choose these neighborhoods. 

<div>
<img src="Images/heat_map_cost_most.png" width=400/>
</div>

Knowing where the highest priced Airbnbs is also important as the highest priced can mean higher profits. 

<div>
<img src="Images/availability_both.png" width=400/>
</div>

Having little availability at 30 days out is a good sign that the Neighbourhood is highly sought after by tourists and good business for the Airbnb owners. We look at availability since many investors believe this is the most important statistic for estimating profits. As a high rental price can mean less, if the rental is not getting booked. 

Visualizing the difference between the most common neighborhoods and the highest priced neighborhoods gives a better understanding of the overall market. We see that 'Central City', 'Lower Garden District', 'Marigny', 'Central Business District', 'Treme - Lafitte', 'French Quarter' are all neighborhoods that are both part of the highest count and highest priced neighborhoods.

<div>
<img src="Images/price_roomtype.png" width=400/>
</div>

To get a better understanding of what type of property is more valued by travelers we see which room type has the highest average price. 

<div>
<img src="Images/available_roomtype.png" width=400/>
</div>

Less availability is better, we see here this visual suggests that renting out an Entire home has a better chance of being booked more.
 
 
The final model had a RMSE of $2.02 which is the root square error of the entire model's error. The RMSE helps us understand how spread out the data is around the line of best fit by using the difference between the observed values and the predicted values. The final model had an MAE of 1.45. The MAE is a metric that gives us the absolute difference between actual and predicted values. The final model went through feature selection. Feature selection can help improve a model because it can reduce overfitting and remove possible redundant features, which helps remove noise that can harm and distract the data. As well, feature selection in this analysis removed mostly categorical features but kept most of the continuous features. Having a dataset not being overwhelmed by categorical features and very few continuous features shows beneficial for many predictive machine learning models.
 
<div>
<img src="Images/model_results.png" width=400/>
</div>
 
## Recommendations & Conclusion
—
 
The machine learning analysis showed that there is enough good data to develop a predictive model that correctly predicts the nightly rate within $2.02. Having a well performing predictive model will prove helpful when comparing properties to buy and help you determine not only the price point you should expect to rent a property at but also help you decide what your purchase price for a property should be around to get the ROI that works for you. 
 
The business problem was to gain a general understanding of the New Orleans, LA short term rental market and make a predictive model for the nightly price of an Airbnb in New Orleans. This analysis was completed for Sarah Alter, a private investor, who is interested in expanding her vacation rental portfolio to New Orleans. This analysis is to be used as a guide as Alter starts her search for a new property. To help Alter reach her goal, exploratory data analysis is used to get an overview of the market. This analysis also provides a price predicting model. A predictive model would be informative when applied to current properties on the market to help Alter get a grasp on what nightly rates she can expect based on specific features of the property. 
 
The final model was a Random Forest model. In summary this analysis showed:
- The final model had an RMSE of $2.02 on the test set.
- The final model had a MAE of 1.45 on the test set.
- The Exploratory Data Analysis shows to be informative in getting an general understanding of the New Orleans' Short term rental market to aid Alter in her property search. Such as which neighborhoods have the highest priced airbnbs and the lowest availability.
 
#### Next steps:
 
Adding more continuous & relevant variables. New Orleans is a large city and even within each neighborhood price data can vary. Reflecting on what makes a Short Term Rental attractive to tourists and adding those features into the model can help get even a better representation of the New Orleans market. Such features which might be interesting to add is distance to the airport and top tourist attractions. More features can be added to this model using API to source this data from places such as Google Earth.

Take into consideration seasonality. This dataset is based around November 7, 2021. However, it is not noted whether it is the main season for New Orleans or not. Importing data from Inside Airbnb for different times of the year might show different price predictions and endup changing your expected ROI.  

Use what was gathered from EDA to further investigate specific neighborhoods. EDA showed which neighborhoods had the most Airbnbs. Researching those neighborhoods might show that they have benefits that other neighborhoods don't, such as less restrictions or qualifications placed on them by the city or county. 