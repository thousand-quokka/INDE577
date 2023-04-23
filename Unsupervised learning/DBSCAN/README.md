# Density-Based Spatial Clustering of Applications with Noise (DBSCAN)

![image](https://user-images.githubusercontent.com/120424457/233853938-c4b03b0b-88be-4725-a06a-1d93aa89a7ca.png)

This project contains description and application of Density-Based Spatial Clustering of Applications with Noise (DBSCAN) algorithm on the palmer penguins dataset.

## Introduction
DBSCAN (Density-Based Spatial Clustering of Applications with Noise) is a popular clustering algorithm that groups together data points that are close to each other in a high-density region and separates out points in low-density regions as noise.

The algorithm works by defining a neighborhood around each data point, based on a specified radius (epsilon). Points that fall within this radius are considered part of the same cluster, and the algorithm recursively expands the cluster by checking the density of the neighboring points. Points that do not belong to any cluster are considered noise.

## Generalized Algorithm: 

Given a dataset with $n$ points $\mathbf{x}_1, \mathbf{x}_2, \dots, \mathbf{x}_n$, DBSCAN partitions the points into clusters based on their density. The algorithm takes two parameters: $\epsilon$, the radius of the neighborhood around each point, and $m$, the minimum number of points required to form a dense region.

The algorithm works as follows:

1. For each point $\mathbf{x}_i$, the set of points within a distance $\epsilon$ of $\mathbf{x}_i$ is defined as the neighborhood $N(\mathbf{x}_i)$:

$$ N(\mathbf{x}_i) = {\mathbf{x}_j \in D \; | \; dist(\mathbf{x}_i, \mathbf{x}_j) \leq \epsilon } $$

where $D$ is the dataset and $dist(\cdot, \cdot)$ is the distance function.

2. For each point $\mathbf{x}_i$, if the size of its neighborhood $|N(\mathbf{x}_i)| \geq m$, then $\mathbf{x}_i$ is considered a core point. 

3. For each core point, a new cluster is created, consisting of the core point itself and all points within its neighborhood. Points that are not core points but fall within the neighborhood of a core point are assigned to the same cluster as the core point.

4. Points that do not belong to any cluster are considered noise.

## Advantages and Disadvantages

### Advantages

- DBSCAN is able to identify clusters of arbitrary shape and size, making it well-suited for datasets with varying density and non-linearly separable clusters.
- The algorithm is not sensitive to the initial choice of cluster centers and can handle clusters of different densities.
- DBSCAN does not require a priori knowledge of the number of clusters, which can be useful for datasets with unknown or changing cluster structures.
- The algorithm is able to identify noise points that do not belong to any cluster.

### Disadvantages

- DBSCAN can be computationally expensive for large datasets, particularly when the dimensionality of the data is high. 
- The performance of DBSCAN can be sensitive to the choice of parameters, such as the radius parameter $\epsilon$ and the minimum number of points required to form a cluster.
- The algorithm may not be suitable for datasets with uniform density, since it may generate a large number of small clusters in such cases.
- DBSCAN is not suitable for datasets with widely varying densities, as the choice of $\epsilon$ may not be appropriate for all clusters.


## Dataset
The Penguins Dataset contains size measurements for three penguin species observed on three islands in the Palmer Archipelago, Antarctica. These data were collected from 2007 - 2009 by Dr. Kristen Gorman's team. It consists of 344 rows and 7 columns. The three different species of penguins are Chinstrap, Adélie, and Gentoo penguins. Download link is: [palmer penguine dataset](https://www.kaggle.com/datasets/parulpandey/palmer-archipelago-antarctica-penguin-data).
* species
* island
* bill_length(mm)
* bill_depth(mm)
* flipper_length(mm)
* body_mass(g)
* sex
