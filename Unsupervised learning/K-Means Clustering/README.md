# K-Means Clustering

![image](https://user-images.githubusercontent.com/120424457/233810907-d9cb74ad-3685-4888-aefe-7f35d3030883.png)

This project contains description and application of k-means clustering algorithm on the palmer penguins dataset. 

## Introduction

K-means clustering is a popular unsupervised machine learning algorithm used for clustering data points into groups based on their similarity. The algorithm works by iteratively assigning data points to the nearest cluster centroid and then updating the centroids based on the new assignments. The process continues until the centroids converge and the cluster assignments remain constant.

The number of clusters k is a hyperparameter that needs to be specified by the user. The algorithm attempts to partition the data into k clusters, with each cluster characterized by its centroid or center. The goal of the algorithm is to minimize the sum of squared distances between the data points and their assigned cluster centroids.

## Generalized Algorithm: 

Given a dataset $X = \{x_1, x_2, ..., x_n\}$ of $n$ data points in a $d$-dimensional feature space, k-means clustering aims to partition the data into $k$ clusters, where $k$ is a user-specified parameter.

Let $C = \{c_1, c_2, ..., c_k\}$ be the set of $k$ centroids that represent the centers of the clusters. The goal of k-means clustering is to find the optimal set of centroids that minimizes the sum of squared distances between the data points and their assigned centroids, which can be expressed as:

$$\min_{C} \sum_{i=1}^{n} \min_{c_j \in C} \|x_i - c_j\|^2 $$

where $\|x_i - c_j\|^2$ is the squared Euclidean distance between data point $x_i$ and centroid $c_j$.

The k-means clustering algorithm consists of the following steps:

1. Initialization: Randomly select $k$ data points as the initial centroids $c_1, c_2, ..., c_k$.

2. Assignment: Assign each data point to the nearest centroid based on the Euclidean distance:

$$y_i = \arg\min_{j=1}^{k} \|x_i - c_j\|^2 $$

where $y_i$ is the index of the nearest centroid for data point $x_i$.

3. Update: Update each centroid $c_j$ to be the mean of the data points assigned to it:

$$c_j = \frac{1}{|S_j|} \sum_{x_i \in S_j} x_i $$

where $S_j$ is the set of data points assigned to centroid $c_j$.

4. Repeat: Repeat steps 2 and 3 until the centroids converge and the cluster assignments remain constant.

The final output of the algorithm is a set of $k$ clusters, where each cluster contains the data points assigned to its corresponding centroid.


## Advantages and Disadvantages

### Advantages

- Easy to implement and computationally efficient, making it suitable for large datasets with many features.
- Can handle different types of data, including continuous, categorical, and binary variables.
- Provides a clear separation of the data into distinct clusters, which can be useful for identifying patterns and relationships.
- Can be applied to a wide range of problems, including data mining, image processing, and market segmentation.

### Disadvantages

- The number of clusters k must be specified by the user, which can be challenging when the optimal number of clusters is unknown.
- K-means clustering is sensitive to the initial placement of the centroids, which can lead to suboptimal solutions. Running the algorithm multiple times with different initializations can help mitigate this issue.
-  Assumes that the clusters have a spherical shape and are equally sized, which may not always be the case in real-world data.
-  Does not handle outliers well and can assign them to a cluster, which may result in a distorted view of the data.


## Dataset
The Penguins Dataset contains size measurements for three penguin species observed on three islands in the Palmer Archipelago, Antarctica. These data were collected from 2007 - 2009 by Dr. Kristen Gorman's team. It consists of 344 rows and 7 columns. The three different species of penguins are Chinstrap, Adélie, and Gentoo penguins. Download link is: [palmer penguine dataset](https://www.kaggle.com/datasets/parulpandey/palmer-archipelago-antarctica-penguin-data).
* species
* island
* bill_length(mm)
* bill_depth(mm)
* flipper_length(mm)
* body_mass(g)
* sex
