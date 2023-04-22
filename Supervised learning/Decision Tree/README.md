# Decision Tree
![image](https://user-images.githubusercontent.com/120424457/233768376-f5761e75-cbc8-4b35-9b4d-ee8f9c686263.png)

This project contains description and application of decision tree algorithm on the palmer penguins dataset. 

## Introduction

A decision tree is a type of supervised machine learning algorithm that is commonly used for classification and regression analysis. The algorithm uses a tree-like structure to represent decisions and their possible consequences. At each node of the tree, the algorithm selects a feature and then splits the data based on the value of that feature.

The goal of the decision tree is to create a model that can accurately predict the class or value of a target variable based on input features. The algorithm iteratively partitions the data into smaller and smaller subsets based on the values of the features, creating a tree-like structure of decision nodes and leaf nodes. Each leaf node represents a class or a value of the target variable.

## Generalized Algorithm: 

Suppose we have a dataset $\mathcal{D}$ consisting of $n$ observations, where each observation has $m$ features and a corresponding class or target variable $y$. Here are the steps for building a decision tree:

1. If a stopping criterion is met, such as reaching a maximum tree depth, having a minimum number of samples per leaf, or having all samples in a leaf belong to the same class, create a leaf node with the majority class or average value of the target variable.
2. Otherwise, select the optimal feature and threshold for splitting the data based on a splitting criterion, such as the Gini impurity or information gain.
3. Create a decision node with the selected feature and threshold, and split the data into two subsets $\mathcal{D}_\text{left}$ and $\mathcal{D}_\text{right}$ based on whether each observation's value of feature $f$ is less than or greater than $t$.
4. Recursively apply the algorithm to each subset, creating child nodes and splitting the data further until the stopping criterion is met.


### Advantages

- Easy to understand and interpret: Decision trees provide a graphical representation of the decision-making process, making it easy to understand and interpret the results.
- Handles both categorical and numerical data: The decision tree algorithm can handle both categorical and numerical data, making it versatile for a wide range of applications.
- Requires little data preparation: The decision tree algorithm can handle missing values and outliers, and does not require much data preparation compared to other machine learning algorithms.
- Non-parametric: Decision trees make no assumptions about the distribution of the data or the relationships between the features, making it a useful tool for exploratory data analysis.


### Disadvantages

- Prone to overfitting: Decision trees can easily overfit the training data, resulting in poor generalization to new data.
- Instability: Small changes to the data can lead to large changes in the resulting decision tree, making it less stable than other machine learning algorithms.
- Can be biased: The decision tree algorithm can be biased towards features with many levels or high cardinality, leading to an over-representation of those features in the resulting tree.
- Can be sensitive to the order of the features: The order in which the features are evaluated can affect the resulting tree, leading to suboptimal splits.


## Dataset
The Penguins Dataset contains size measurements for three penguin species observed on three islands in the Palmer Archipelago, Antarctica. These data were collected from 2007 - 2009 by Dr. Kristen Gorman's team. It consists of 344 rows and 7 columns. The three different species of penguins are Chinstrap, Adélie, and Gentoo penguins. Download link is: [palmer penguine dataset](https://www.kaggle.com/datasets/parulpandey/palmer-archipelago-antarctica-penguin-data).
* species
* island
* bill_length(mm)
* bill_depth(mm)
* flipper_length(mm)
* body_mass(g)
* sex
