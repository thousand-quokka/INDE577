# Decision Tree
![image](https://user-images.githubusercontent.com/120424457/233768376-f5761e75-cbc8-4b35-9b4d-ee8f9c686263.png)

This project contains description and application of decision tree algorithm on the palmer penguins dataset. 

## Introduction

A decision tree is a type of supervised machine learning algorithm that is commonly used for classification and regression analysis. The algorithm uses a tree-like structure to represent decisions and their possible consequences. At each node of the tree, the algorithm selects a feature and then splits the data based on the value of that feature.

The goal of the decision tree is to create a model that can accurately predict the class or value of a target variable based on input features. The algorithm iteratively partitions the data into smaller and smaller subsets based on the values of the features, creating a tree-like structure of decision nodes and leaf nodes. Each leaf node represents a class or a value of the target variable.

## Generalized Algorithm: 

Given a training dataset $\mathcal{D} = \{(x_i, y_i)\}_{i=1}^n$, where $x_i = (x_{i1}, x_{i2}, ..., x_{im})$ represents the $m$ features of the $i$-th observation and $y_i$ is its corresponding label, the decision tree algorithm works as follows:

1. Initialize a root node containing all the observations in $\mathcal{D}$.

2. For each node, select the best feature $f$ and a threshold $t$ that minimize a splitting criterion $C(\mathcal{D}, f, t)$.

3. Split the node into two child nodes $\mathcal{D}_\text{left}$ and $\mathcal{D}_\text{right}$ according to the selected feature and threshold.

4. Recursively repeat steps 2 and 3 for each child node until a stopping criterion is met, such as a maximum tree depth, minimum number of samples per leaf, or having all samples in a leaf belong to the same class.

To select the best feature and threshold at each node, we need to define a splitting criterion $C(\mathcal{D}, f, t)$ that measures the quality of the split. There are several popular splitting criteria, including:

- Gini impurity: $\text{Gini}(\mathcal{D}) = 1 - \sum_{i=1}^k p_i^2$, where $k$ is the number of classes and $p_i$ is the proportion of observations in $\mathcal{D}$ that belong to class $i$.

- Information gain: $\text{IG}(\mathcal{D}, f) = \text{H}(\mathcal{D}) - \sum_{v \in \text{values}(f)} \frac{|\mathcal{D}_v|}{|\mathcal{D}|}\text{H}(\mathcal{D}_v)$, where $\text{H}(\mathcal{D})$ is the entropy of $\mathcal{D}$ and $\mathcal{D}_v$ is the subset of observations in $\mathcal{D}$ where feature $f$ has value $v$.

- Variance reduction: $\text{VR}(\mathcal{D}, f, t) = \text{Var}(\mathcal{D}) - \sum_{i \in \{0,1\}} \frac{|\mathcal{D}_i|}{|\mathcal{D}|} \text{Var}(\mathcal{D}_i)$, where $\text{Var}(\mathcal{D})$ is the variance of the labels in $\mathcal{D}$ and $\mathcal{D}_i$ is the subset of observations in $\mathcal{D}$ where feature $f$ is less than or greater than $t$.

To find the best feature and threshold, we need to evaluate the splitting criterion for each possible feature and threshold combination and choose the one that results in the highest information gain, greatest variance reduction or lowest Gini impurity.


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
