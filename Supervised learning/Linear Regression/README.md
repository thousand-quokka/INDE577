# Linear Regression
![image](https://user-images.githubusercontent.com/120424457/233192936-f4989578-8e9e-436a-94b5-68628405b660.png)

This project contains description and application of linear regression algorithm on the red wine dataset. 

## Introduction
A linear regression model describes the relationship between a dependent variable, $y$, and one or more independent variables, $X$. The dependent variable is also called the response variable. Independent variables are also called explanatory or predictor variables. Continuous predictor variables are also called covariates, and categorical predictor variables are also called factors. The matrix $X$ of observations on predictor variables is usually called the design matrix. Three major uses for regression analysis are (1) determining the strength of predictors, (2) forecasting an effect, and (3) trend forecasting.


## Generalized Algorithm: 
A multiple linear regression model is
$$y_i=\beta_0+\beta_1 X_{i 1}+\beta_2 X_{i 2}+\cdots+\beta_p X_{i p}+\varepsilon_i, \quad i=1, \cdots, n,$$
where
- $n$ is the number of observations.
- $y_i$ is the $i$ th response.
- $\beta_k$ is the $k$ th coefficient, where $\beta_0$ is the constant term in the model. Sometimes, design matrices might include information about the constant term. However, fit lm or stepwiselm by default includes a constant term in the model, so you must not enter a column of $1 \mathrm{~s}$ into your design matrix $X$.
- $X_{i j}$ is the $i$ th observation on the $j$ th predictor variable, $j=1, \ldots, p$.
- $\varepsilon_i$ is the $i$ th noise term, that is, random error.
If a model includes only one predictor variable $(p=1)$, then the model is called a simple linear regression model.
In general, a linear regression model can be a model of the form

$$y_i=\beta_0+\sum_{k=1}^K \beta_k f_k\left(X_{i 1}, X_{i 2}, \cdots, X_{i p}\right)+\varepsilon_i, \quad i=1, \cdots, n,$$


## Advantages and Disadvantages

### Advantages
- Simple implementation
Linear Regression is a very simple algorithm that can be implemented very easily to give satisfactory results.Furthermore, these models can be trained easily and efficiently even on systems with relatively low computational power when compared to other complex algorithms.Linear regression has a considerably lower time complexity when compared to some of the other machine learning algorithms.The mathematical equations of Linear regression are also fairly easy to understand and interpret.Hence Linear regression is very easy to master.

- Performance on linearly seperable datasets
Linear regression fits linearly seperable datasets almost perfectly and is often used to find the nature of the relationship between variables.

- Overfitting can be reduced by regularization
Overfitting is a situation that arises when a machine learning model fits a dataset very closely and hence captures the noisy data as well.This negatively impacts the performance of model and reduces its accuracy on the test set.
Regularization is a technique that can be easily implemented and is capable of effectively reducing the complexity of a function so as to reduce the risk of overfitting.

### Disadvantages
- Prone to underfitting
Underfitting : A sitiuation that arises when a machine learning model fails to capture the data properly.This typically occurs when the hypothesis function cannot fit the data well.

- Sensitive to outliers
Outliers of a data set are anomalies or extreme values that deviate from the other data points of the distribution.Data outliers can damage the performance of a machine learning model drastically and can often lead to models with low accuracy.

- Linear Regression assumes that the data is independent
Very often the inputs aren't independent of each other and hence any multicollinearity must be removed before applying linear regression.

## Dataset
The red wine dataset contains 1599 samples,12 columns. Download link is: [red wine dataset](https://archive.ics.uci.edu/ml/datasets/wine+quality).
* fixed acidity
* volatile acidity
* citric acid
* residual sugar
* chlorides
* free sulfur dioxide
* total sulfur dioxide
* density
* pH
* sulphates
* alcohol
* quality

