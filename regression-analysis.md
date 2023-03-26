## Regression Analysis and its techniques in Data Science
Let us understand what regression analysis means, and then understand how its techniques are used in the field of data science. 
First let us see what regression is, and understand its usage. 

### What is regression?
Regression is basically a way to estimate/extrapolate/predict values when certain values/dataset is provided. 
It is a well-known statistical learning method that helps infer the relationship between a dependent variable and an independent variable. This dependent variable is also known as the response variable/outcome, and the independent variable (or variables) are also known as predictors/explanatory variables/covariates. The independent variable is known as predictor or explanatory variable since it helps predict the dependent value, it explains why a certain value was predicted. 

Image credit: https://towardsdatascience.com/introduction-to-regression-analysis-9151d8ac14b3

In general, regression tries to predict the mathematical relation f() to explain the dependant variable in terms of the independent variable, i.e 
Dependant variable = f(independent variable)


Here, the dependent and independent variable is taken as an ordered pair (dependent variable, independent variable) which is a collection of observed data. 
When certain values are provided, and it is required to find/estimate the further set of values, regression can be used to find these values. It helps in finding trends and patterns in the data. 
There are different kinds of regression, such as linear regression that uses a single variable (known as univariate regression), linear regression that uses multiple variables (multivariate regression), logistic regression, ridge regression, lasso regression, non-linear regression and so on. 
Let us take an example to understand regression: 
Suppose we have been given certain dimensions of houses and their respective prices, and the task is to find the price of a house with a specific set of dimensions. This can be done using regression, wherein the dimensions and respective values are used, and extrapolated to find the price of the house with s specific dimension. 

### Introduction
#### What is regression analysis?
Regression analysis is a vital tool to model and analyse the given dataset. The given data is fit to a curve or a line (on a graph) so that the difference between the distances from data point to the curve/line is minimal. 
Let us take one more example to understand regression:
Suppose we are required to predict the prices of cars depending on factors such as its model, the type of engine, the number of miles it has run, the condition, and the colour. 
When we are asked to use regression to find the price, we can safely ignore the ‘colour’ factor since it doesn’t intensively affect the resale price of a car. Important factors that need to be considered are the model, the engine type, and the number of miles it has run. This means, there are three factors that influence the price of the car. 
Suppose we already have a list of cars, with values for the above mentioned factors, and the resale price, and we need to estimate/predict the price of another car (given the important factors), it can be done by using the list of cars as a reference. 


Note:
In real life problems, there will be far more data (number of rows) if we are to predict data with a high percentage of accuracy. 

Now, the goal is to find the resale price of a car (Baleno which was purchased 1 year ago, which is manual and has run 7000 miles).
Since we already have the list of car along with its prices, and factors, regression helps devise an equation that can be used to estimate the value of other cars. 
Let us assume that the equation that has been devised is:
For automatic cars:
Resale_price = Actual price – (0.3 * actual price) – number of miles 


For manual cars:
Resale_price = Actual price – (0.3 * actual price) – (number of miles/2)


Note: The above equation is a random equation, whereas in reality, the equation would have been formed with a great deal of precision by considering every factor and how effective it is in deciding the resale price.  33900
This equation is actually an equation to draw a graph by plugging in different values for variables present in the equation. This line on the graph can be extrapolated to find value for other values present in the equation.

Let us see what happens when we plug in values for ‘actual price’ and ‘number of miles’, when the above equation is used:

Once we have estimated the price of a specific car, other statistics of the data can also be obtained. These statistics can be used to understand how well the estimation was made, its accuracy and precision. 
For the estimation to be considered a good one, the difference between the actual value and the estimated value needs to be minimal. 

#### Where can regression be used?
It can be used in forecasting, time series modelling, finding the causal effect relation between different variables. 
As mentioned previously, it can also be used to predict the house prices given house dimensions and other relevant factors. 
It can also be used to predict the resale prices of cars given the relevant factors such as model of the car, number of miles it has run, the type of engine, and so on. 
Different types of regression and its usage in the field of Data Science
Below is a list of commonly used regression techniques, which is used in data science. Sometimes, these regression techniques would directly yield the required results given a dataset. 
But in other situations, it may be required to use different regression techniques after intensive data pre-processing. All of this depends on the dataset in hand, and the end goal of the user. 
**Linear regression:** It will have one independent variable, and it is used with continuous data. This means the equation would be a linear equation. The graph that needs to be fit would be a straight line. 
**Logistic regression:** This technique is used with discrete data, wherein the output would be 0 or 1, true or fall, yes or no, and so on. It is used with classification problems. It uses maximum likelihood estimation (MLE) to predict the output. 
**Ridge regression:** It is used when the independent variables are highly correlated to one another, i.e they are multicollinear. The variance value would be large, hence a bias is introduced to reduce standard errors associated with prediction. 
**LASSO regression:** This is similar to ridge regression, but penalizes the additional coefficients. It improves accuracy of linear models. It means Least Absolute Shrinkage and Selection Operator.
**Polynomial regression:** The best fit is a curve here, and it is polynomial regression if and only if the power of the independent variable is more than 1. 
**ElasticNet regression:** It is a hybrid of LASSO and Ridge regression techniques. It is used when there are multiple features and they are all correlated. 

#### How can regression be implemented?
There are a host of tools that can be used to work with regression. This includes using Excel, using the R programming language, using Python and machine learning techniques, by using statistics and so on. 
Regression also helps compute the R squared value, which tells how accurate the model is. The value of R squared can range from 0 to 1. Here 0 indicates that the model is extremely bad whereas 1 indicates that it is an ideal model.

### Conclusion
In this article, we understood what regression is with the help of examples. We understood regression analysis and how it can be useful. We understood how it can be implemented using different techniques. We saw the different regression techniques as well as understood how it can be applied in the field of data science. 
