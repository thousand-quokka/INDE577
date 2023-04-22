# Gradient Descent
![image](https://user-images.githubusercontent.com/120424457/233750588-bb19ce68-09e4-44f8-929c-c898f37dfe50.png)

## Introduction
Gradient descent is a widely used optimization algorithm that is commonly used in machine learning and deep learning applications. It is an iterative method that aims to find the minimum of a function by taking small steps in the direction of the negative gradient of the function.

The algorithm works by starting with an initial guess for the minimum of the function and then repeatedly adjusting the guess by taking small steps in the direction of the negative gradient until the function value converges to a minimum.

In this project, we apply this algorithm in linear regression manually on simulation data, also apply it on diabetes dataset using sklearn.

## Generalized Algorithm: 

Let $f(\theta)$ be a function that we want to minimize with respect to the parameters $\theta$. The gradient of the function is denoted by $\nabla f(\theta)$.

The gradient descent algorithm can be written as follows:

1. Initialize the parameters $\theta$ to some random values.
2. Repeat until convergence:
   - Calculate the gradient of the function: $\nabla f(\theta)$.
   - Update the parameters using the update rule: $\theta := \theta - \alpha \nabla f(\theta)$, where $\alpha$ is the learning rate.

The learning rate $\alpha$ determines the step size that is taken in the direction of the negative gradient. If the learning rate is too large, the algorithm may overshoot the minimum and diverge. If the learning rate is too small, the algorithm may converge too slowly.

The gradient descent algorithm is guaranteed to converge to a local minimum if the function is convex. However, if the function is non-convex, the algorithm may converge to a local minimum or a saddle point.

Overall, the gradient descent algorithm is a powerful optimization algorithm that is widely used in machine learning and deep learning applications to minimize cost functions and improve the performance of models.

## Advantages and Disadvantages

### Advantages

- Gradient descent is a widely used optimization algorithm for minimizing cost functions in machine learning and deep learning.
- It is an iterative algorithm that can converge to a local minimum of the cost function.
- The algorithm is computationally efficient and can scale to large datasets.
- Gradient descent can handle high-dimensional feature spaces and non-linear models.
- It can be modified to handle different types of cost functions and regularization techniques.

### Disadvantages

- The choice of learning rate can be critical and may require manual tuning or adaptive methods.
- The algorithm may converge slowly or get stuck in local minima or saddle points.
- It may require a large number of iterations to converge, which can be time-consuming.
- Gradient descent can be sensitive to the initialization of the parameters.
- The algorithm may not be suitable for non-convex cost functions or models with multiple local minima.


## Dataset
The diabetes dataset is a widely used benchmark dataset in machine learning and statistical analysis. It contains information on medical features of patients who have diabetes, such as age, sex, body mass index, blood pressure, and various blood serum measurements. 

The dataset was originally created by the National Institute of Diabetes and Digestive and Kidney Diseases, and is often used in research and analysis to study the relationship between medical factors and diabetes outcomes. 

The dataset contains 10 independent variables, including:

- Age: age in years
- Sex: 1 for male, 0 for female
- Body mass index (BMI): a measure of body fat based on height and weight
- Average blood pressure: average blood pressure across two visits, measured in mmHg
- S1 to S6: six blood serum measurements
- Target variable: a quantitative measure of disease progression one year after baseline, measured using the natural log of the amount of serum insulin in the blood. 

The goal of machine learning models trained on the diabetes dataset is typically to predict the progression of diabetes based on the patient's medical features.
