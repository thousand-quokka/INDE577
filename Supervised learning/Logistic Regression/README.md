# Logistic Regression
![image](https://user-images.githubusercontent.com/120424457/233527462-800fe6c3-5626-403b-a5dc-1edf9e23a5ca.png)

## Introduction
Logistic regression is a widely used statistical method for binary classification problems. It is a type of regression analysis that is used to predict the probability of a categorical outcome based on one or more predictor variables. In other words, it is used to model the relationship between a dependent variable (which takes on discrete values) and one or more independent variables (which can be continuous or categorical).

## Generalized Algorithm: 

The logistic function is defined as:

\begin{equation}
p(x) = \frac{1}{1 + e^{-z}} 
\end{equation}

where $p(x)$ is the probability of the binary outcome, $e$ is the mathematical constant (approximately equal to 2.71828), and $z$ is the linear combination of the independent variables:

\begin{equation}
z = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + ... + \beta_p x_p
\end{equation}

where $\beta_0$ is the intercept term, $\beta_i$ are the coefficients for each independent variable $x_i$, and $p$ is the number of independent variables.

The logistic regression algorithm estimates the values of the coefficients $\beta_0$, $\beta_1$, $\beta_2$, ..., $\beta_p$ that maximize the likelihood of the observed data. This is typically done using an iterative optimization algorithm such as gradient descent or Newton-Raphson. Once the coefficients are estimated, they can be used to predict the probability of the outcome for new observations with known values of the independent variables.


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
