## Factor analysis
### Introduction
Factor analysis is a part of the general linear model (GLM). It is a method in which large amounts of data are collected and reduced in size to a smaller dataset. This reduction in the size of the dataset ensures that the data is manageable and easily understood by people. 
In addition to manageability and interpretability, it helps extract patterns in data as well as show the characteristics that are commonly seen in the different patterns (that are extracted). It helps create variable set for data points in the dataset that are similar. This similar set of data is also known as dimensions. 

### Assumption
An assumption while dealing with factor analysis is that, in a collection of the variables observed, there is a set of underlying variables, which is known as ‘factor’. This factor helps explain the inter-relationship between these variables. 
There should be a linear relationship between the variables in the data. 
There should be no multicollinearity between variables in the data. 
There should be true correlation between the variables and factors in the data. 
There are multiple methods to extract factors from data, but principal component analysis is one of the most frequently used methods. In Principal component analysis (PCA), maximum variance is extracted and placed in the first factor. Once this is done, the variance explained by the first set of factors is eliminated and then maximum variance is again extracted for the second factor. This goes on until the last factor in the variable set. 

Image Credit: https://www.statisticshowto.com/factor-analysis/

#### Types of factor analysis
The word ‘factor’ in factor analysis refers to the variable set which have similar patterns. They are sometimes associated with a hidden variable, which is also known as confounding variable. This hidden variable is not measured directly. The ‘factors’ tell about the variation in data which can be explained. 
There are two types of factors: 
Exploratory;
Confirmatory
Exploratory factor analysis
This deals with data that is unstructured or when the person/s dealing with the data are clueless about the structure of the data and the dimensions of the variable associated with the data. Exploratory factor analysis gives information about the optimum number of factors which may be required to represent the data. If a researcher wishes to explore patterns, it is suggested to use exploratory factor analysis. 

Image Credit: https://www.researchgate.net/figure/Conceptual-overview-of-Exploratory-Factor-Analysis_fig1_209835856

#### Confirmatory factor analysis 
This kind of analysis is used to verify the structure of the data, given the condition that the people dealing with the data are aware of its structure and dimensions of the variable associated with the data. This kind of analysis helps specify the number of factors required to perform the analysis. 
Factor analysis is a multivariate method- this means it deals with multiple variables associated with data. This is a data reduction technique wherein the basic idea is to use a smaller set of variables, which is known as ‘factors’, that is a representation of a bigger set of variables. 
It helps the researcher in understanding whether the relationship between the observed variables (aka manifest variables) and their underlying construct exists or not. 
If a researcher wishes to perform hypothesis testing, it is suggested to use exploratory factor analysis. 

### What are factors?
Factors can be understood as a construct which can’t be measured with the help of a single variable. Factor analysis is generally used with interval data, but it can be used for ordinal data as well. 

### What is ordinal data?
Ordinal data is statistical data in which variables exist in naturally occurring categories that are in a particular order. The distance between categories in ordinal data can’t be found using ordinal data itself. 
For a dataset to be ordinal data, it needs to fulfil few conditions. 
- Multiple terms in the dataset are in an ordered fashion. 
- The difference between variables in the dataset is not homogeneous/uniform. 

A group of ordinal numbers indicates ordinal data, and a group of ordinal data can be represented using an ordinal scale. 
Likert Scale is one type of ordinal data. Let us understand Likert scale with the help of an example:

Suppose we have a question that says “Please indicate how satisfied you are with this product purchase”. A Likert scale may have numbers between 0/1 to 5 or 0/1 to 10. On this scale, 0/1 indicates a lesser value and 5 or 10 indicates a higher value. 

Let us understand ordinal data with the help of another example. If we have variables stored in a specific order, say “low, medium, high” or “not happy, slightly happy, happy, very happy, extremely happy”, it is considered as ordinal data. 

### Conditions for variables in factor analysis
These variables (in factor analysis) need to be linearly associated with each other. Linear relationship or association describes a relationship that forms a straight line when two variables are plotted on a graph. It can also be represented as a mathematical equation in the form ‘y = mx + b’. 
This linear associativity can be checked by plotting scatterplots of the pairs of variables. This indicates that the variables need to be moderately correlated to each other. 
If the variables are not correlated, the number of factors will be same as the number of original variables. This means that performing factor analysis on this kind of variables would be useless. 

### How can factor analysis be performed?
Factor analysis is a complex mathematical procedure. It can be performed with the help of software applications. Before performing the analysis, it is essential to check if the data is relevant. This can be done with the help of Kaiser-Meyer-Olkin test. 
Kaiser-Meyer-Olkin test
This is also known as the KMO test, which is used to see how well the data is suited to perform factor analysis. It measures the sampling adequacy for every variable in the model. 
This statistic measures the proportion of variance among all the variables in the data. The lower the proportion, more suited the data is to perform factor analysis. 
KMO returns values between 0 and 1. 
If KMO value lies between 0.8 and 1, it means that the sampling is adequate.
If KMO value is less than 0.6 or lies between 0.5 and 0.6, it means that the sampling is not adequate. This means proper actions need to be taken. 
If KMO value is closer to 0, this indicates that the data contains large number of partial correlations in comparison to the sum of correlations. This is not suited for factor analysis. 
- Values between 0 and 0.49 are considered unacceptable.
- Values between 0.50 and 0.59 are considered not good.
- Values between 0.60 and 0.69 are considered mediocre. 
- Values between 0.70 and 0.79 are considered to be good. 
- Values between 0.80 and 0.89 are considered to be great.
- Values between 0.90 and 1.00 are considered to be absolutely fantastic.

The formula to perform KMO test is:
![formula](./formula.png)

Here, R =  which is the correlation matrix;
and U =  which is the partial covariance matrix. 
Once relevant data has been collected, factor analysis can be performed in a variety of ways. 

### Using Stata
It can be performed in Stata with the help of postestimation command- ‘estat kmo’.

### Using R
It can be performed in R using the command ‘KMO(r)’ where ‘r’ refers to the correlation matrix that needs to be analysed. 

### Using SPSS
SPSS is a statistical platform that can be used to run factor analysis. First go to Analyze -> Dimension Reduction -> Factor, and check the “KMO and Bartlett’s test of sphericity” box. 
If the measure of sampling adequacy (MSA) for single variable is needed, the ‘”anti-image” box needs to be checked. An ‘anti-image’ box shows the MSAs listed in diagonals of matrix. 
The test can also be executed by specifying KMO in the Factor Analysis command. The KMO statistic is found in the “KMO and Bartlett’s Test” table in the Factor output. 

## Conclusion
In this post, we understood about the factor analysis method, and the assumptions made before working on the method. We also saw different kinds of factor analysis, and how they can be performed on different platforms.  
