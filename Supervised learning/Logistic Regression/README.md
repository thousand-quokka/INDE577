# Logistic Regression
![image](https://user-images.githubusercontent.com/120424457/233528605-794e64f3-7b19-4e71-9656-2675f8c82b68.png)
## Introduction
Logistic regression is a widely used statistical method for binary classification problems. It is a type of regression analysis that is used to predict the probability of a categorical outcome based on one or more predictor variables. In other words, it is used to model the relationship between a dependent variable (which takes on discrete values) and one or more independent variables (which can be continuous or categorical).

## Generalized Algorithm: 

Logistic regression is a statistical model that is used to analyze the relationship between a binary dependent variable and one or more independent variables. The goal of logistic regression is to estimate the probability that the dependent variable takes on the value 1 (or "success") given the values of the independent variables.

The logistic regression model uses a logistic function (also known as a sigmoid function) to transform the linear combination of the independent variables into a probability value between 0 and 1. The logistic function is defined as:

$$f(z) = \frac{1}{1 + e^{-z}}$$


where $z$ is the linear combination of the independent variables, and $e$ is the mathematical constant (approximately equal to 2.71828).

$$z = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + ... + \beta_p x_p$$ 

where $\beta_0$ is the intercept term, $\beta_i$ are the coefficients for each independent variable $x_i$, and $p$ is the number of independent variables.

The logistic function maps the linear combination of the independent variables to a probability value between 0 and 1. The probability of the dependent variable taking on the value 1 given the values of the independent variables is given by:

$$P(Y = 1|X) = f(z) = \frac{1}{1 + e^{-z}}$$

where $Y$ is the dependent variable (with values of 0 or 1), and $X$ is the matrix of independent variables.

The logistic regression model estimates the values of the coefficients $\beta_0$, $\beta_1$, $\beta_2$, ..., $\beta_p$ that maximize the likelihood of the observed data. The likelihood function is given by:

$$L(\beta_0, \beta_1, ..., \beta_p) = \prod_{i=1}^n [f(z_i)]^{y_i} [1-f(z_i)]^{1-y_i}$$

where $n$ is the number of observations, $y_i$ is the observed value of the dependent variable for the $i$th observation, and $z_i$ is the linear combination of the independent variables for the $i$th observation.

The maximum likelihood estimates of the coefficients can be obtained by solving the following equation:

$$\frac{\partial L(\beta_0, \beta_1, ..., \beta_p)}{\partial \beta_j} = 0, \ j=0, 1, ..., p$$

This equation can be solved using numerical optimization techniques such as gradient descent or Newton-Raphson.

Once the coefficients are estimated, they can be used to predict the probability of the dependent variable taking on the value 1 for new observations with known values of the independent variables. The logistic regression model can also be used to test the significance of the independent variables and to identify which variables have the strongest relationship with the dependent variable.

In summary, logistic regression is a statistical model that uses a logistic function to model the relationship between a binary dependent variable and one or more independent variables. The model estimates the coefficients that maximize the likelihood of the observed data and can be used to predict the probability of the dependent variable taking on the value 1 for new observations.

## Advantages and Disadvantages

### Advantages

- Simplicity: Logistic regression is a simple and straightforward algorithm that is easy to understand and implement. It is a linear model that can handle both linear and nonlinear relationships between the independent and dependent variables.

- Interpretability: Logistic regression provides interpretable results in the form of odds ratios and coefficients. These can be used to understand the direction and strength of the relationship between the independent variables and the dependent variable.

- Flexibility: Logistic regression can handle both binary and categorical dependent variables, making it a versatile algorithm that can be applied to a wide range of classification problems.

- Low computational cost: Logistic regression is computationally efficient and can handle large datasets without requiring significant computational resources.

- Robustness: Logistic regression is robust to outliers and missing data, and it can handle multicollinearity between independent variables.

### Disadvantages

- Linearity assumption: Logistic regression assumes that the relationship between the independent variables and the dependent variable is linear. If the relationship is nonlinear, the model may not fit the data well.

- Overfitting: Logistic regression can be prone to overfitting when the number of independent variables is large relative to the number of observations in the dataset. Regularization techniques such as L1 or L2 regularization can be used to mitigate this problem.

- Independence assumption: Logistic regression assumes that the observations are independent of each other. If the observations are not independent, the model may not be accurate.

- Imbalanced classes: When the classes are imbalanced, meaning that one class has many more observations than the other, logistic regression may not perform well. This can be addressed by using techniques such as oversampling or undersampling.

- Limited to linear decision boundaries: Logistic regression is a linear classifier, meaning it can only create linear decision boundaries. This can limit its ability to classify complex datasets with non-linear decision boundaries.

- Cannot handle missing data: Logistic regression cannot handle missing data in the dataset. Missing data must be imputed or handled in some other way before the model can be trained.

## Dataset
The Penguins Dataset contains size measurements for three penguin species observed on three islands in the Palmer Archipelago, Antarctica. These data were collected from 2007 - 2009 by Dr. Kristen Gorman's team. It consists of 344 rows and 7 columns. The three different species of penguins are Chinstrap, Adélie, and Gentoo penguins. Download link is: [palmer penguine dataset](https://www.kaggle.com/datasets/parulpandey/palmer-archipelago-antarctica-penguin-data).
* species
* island
* bill_length(mm)
* bill_depth(mm)
* flipper_length(mm)
* body_mass(g)
* sex
