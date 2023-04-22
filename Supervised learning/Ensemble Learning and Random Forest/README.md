# Ensemble Learning and Random Forest

![image](https://user-images.githubusercontent.com/120424457/233774871-25bf703e-7a50-4860-951b-2f81b7578f4e.png)

This project contains description and application of ensemble learning and random forest algorithm on the palmer penguins dataset. 

## Introduction
Ensemble learning is a powerful technique in machine learning that involves combining multiple models to achieve better predictive performance than any individual model. One of the most popular and effective ensemble methods is the random forest algorithm.

Random forests are a type of ensemble learning algorithm that are well-suited for both classification and regression tasks. The algorithm builds a multitude of decision trees, each trained on a random subset of the data and using a random subset of the features. The final prediction is then made by averaging the predictions of all the individual trees.

## Generalized Algorithm: 

Let $X$ be a matrix of $n$ samples and $p$ features, where $X_{ij}$ denotes the value of the $j$-th feature for the $i$-th sample. Let $y$ be a vector of length $n$ containing the target variable. The random forest algorithm works as follows:

1. For each tree in the forest:
    
    a. Draw a bootstrap sample of size $n$ from the data, i.e., sample $n$ rows from $X$ with replacement.
    
    b. Randomly select $m$ features from the $p$ available features, where $m << p$.
    
    c. Construct a decision tree using the bootstrap sample and the selected features. At each node of the tree, split the data based on the feature that maximizes the reduction in impurity, using a criterion such as Gini impurity or entropy.
    
2. For a new input sample $x$, predict the target variable by averaging the predictions of all the trees in the forest, i.e., $\hat{y}(x) = \frac{1}{T}\sum_{i=1}^{T}f_i(x)$, where $T$ is the number of trees and $f_i(x)$ is the predicted value of the $i$-th tree for the input $x$.


## Advantages and Disadvantages

### Advantages

- Random forests are able to capture complex non-linear relationships between features in the data, making them well-suited for a wide range of tasks, including classification and regression.
- They are robust to noise and overfitting, thanks to the random sampling and feature selection used in the algorithm.
- Random forests can handle both categorical and continuous data, as well as missing values.
- They are relatively fast to train and can handle large datasets with high dimensionality.
- Random forests are able to provide estimates of feature importance, which can be useful in identifying the most relevant features for the task at hand.

### Disadvantages
- Random forests can be computationally expensive, particularly when the number of trees or the size of the data is large.
- They can be difficult to interpret, as the model consists of a large number of decision trees that are combined in a non-linear way.
- The accuracy of the model can be sensitive to the choice of hyperparameters, such as the number of trees, the depth of the trees, and the size of the random subsets used in the algorithm.
- Random forests may not perform as well as other models on datasets with highly correlated features or sparse data.


## Dataset
The Penguins Dataset contains size measurements for three penguin species observed on three islands in the Palmer Archipelago, Antarctica. These data were collected from 2007 - 2009 by Dr. Kristen Gorman's team. It consists of 344 rows and 7 columns. The three different species of penguins are Chinstrap, Adélie, and Gentoo penguins. Download link is: [palmer penguine dataset](https://www.kaggle.com/datasets/parulpandey/palmer-archipelago-antarctica-penguin-data).
* species
* island
* bill_length(mm)
* bill_depth(mm)
* flipper_length(mm)
* body_mass(g)
* sex
