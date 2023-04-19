# K-Nearest Neighbors

This project contains description and application of KNN algorithm on the red wine dataset. We also explore how $k$ could affect the prediction accuracy.

## Introduction
The K Nearest Neighbors (KNN) algorithm is an uncomplicated method that retains all available cases and categorizes new data or cases by means of a similarity measure. It is commonly employed to classify a datapoint by examining the classification of its nearest neighbors. KNN finds its applications in a broad range of areas, such as recommendation systems, anomaly detection, and image/text classification. While KNN can be utilized for regression, its use for this purpose is not as prevalent as it is for classification.


## Generalized Algorithm: 
1. Calculate the distance between test data and each row of training dataset.
2. Sort the calculated distances in ascending order based on distance values.
3. Get top k rows from the sorted array.
4. Get the most frequent class of these rows.
5. Return the predicted class.

## Advantages and Disadvantages

### Advantages
- Easy to implement: Given the algorithm’s simplicity and accuracy, it is one of the first classifiers that a new data scientist will learn.
- Adapts easily: As new training samples are added, the algorithm adjusts to account for any new data since all training data is stored into memory.

- Few hyperparameters: KNN only requires a k value and a distance metric, which is low when compared to other machine learning algorithms.

### Disadvantages
- Does not scale well: Since KNN is a lazy algorithm, it takes up more memory and data storage compared to other classifiers. This can be costly from both a time and money perspective. More memory and storage will drive up business expenses and more data can take longer to compute. While different data structures, such as Ball-Tree, have been created to address the computational inefficiencies, a different classifier may be ideal depending on the business problem.

- Curse of dimensionality: The KNN algorithm tends to fall victim to the curse of dimensionality, which means that it doesn’t perform well with high-dimensional data inputs. This is sometimes also referred to as the peaking phenomenon, where after the algorithm attains the optimal number of features, additional features increases the amount of classification errors, especially when the sample size is smaller.

- Prone to overfitting: Due to the “curse of dimensionality”, KNN is also more prone to overfitting. While feature selection and dimensionality reduction techniques are leveraged to prevent this from occurring, the value of k can also impact the model’s behavior. Lower values of k can overfit the data, whereas higher values of k tend to “smooth out” the prediction values since it is averaging the values over a greater area, or neighborhood. However, if the value of k is too high, then it can underfit the data. 


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

