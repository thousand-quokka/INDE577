# Principal Component Analysis (PCA)

![image](https://user-images.githubusercontent.com/120424457/233861322-e5a6002c-6eb6-447c-b011-983e1eefe326.png)


This project contains description and application of principal component analysis (PCA) algorithm on the breast cancer dataset.

## Introduction

Principal Component Analysis (PCA) is a widely used technique for reducing the dimensionality of a dataset while retaining as much information as possible. It is particularly useful for datasets with many variables, as it can help identify the most important variables that explain the majority of the variation in the data.

The goal of PCA is to find a new set of variables (called principal components) that are linear combinations of the original variables and explain as much of the variability in the data as possible. These principal components are ranked by the amount of variance they explain, so the first principal component explains the most variance, the second principal component explains the second most variance, and so on.

## Generalized Algorithm: 

Given a dataset $X$ of $n$ samples and $m$ features, the goal of PCA is to find a set of $k$ new features $Y_1, Y_2, \dots, Y_k$ that capture the most important information in the data. These new features are linear combinations of the original features, where $Y_i = a_{i1}X_1 + a_{i2}X_2 + \dots + a_{im}X_m$ for $i = 1, 2, \dots, k$.

To determine the coefficients $a_{ij}$, we want to find the eigenvectors of the covariance matrix $C$ of the original dataset. The covariance matrix is defined as:

$$C = \frac{1}{n-1}(X - \bar{X})^T(X - \bar{X})$$

where $\bar{X}$ is the mean vector of the dataset. The eigenvectors of $C$ correspond to the principal components, and the eigenvalues correspond to the amount of variance explained by each component.

We can use the SVD method to compute the eigenvectors and eigenvalues of $C$. Let $U\Sigma V^T$ be the SVD of $C$, where $U$ is a $m \times m$ matrix of orthonormal eigenvectors, $\Sigma$ is a diagonal matrix of eigenvalues, and $V$ is a $n \times m$ matrix. The $i$-th principal component is given by the $i$-th column of $U$, and the amount of variance explained by each component is given by the corresponding diagonal element of $\Sigma^2$.

To perform dimensionality reduction, we can select the top $k$ principal components that explain the most variance and project the original dataset onto these components. The projected dataset $X'$ is given by:

$$X' = XV_k$$

where $V_k$ is the matrix consisting of the top $k$ eigenvectors of $C$. This results in a new dataset $X'$ of $n$ samples and $k$ features.

In summary, PCA involves the following steps:

1. Standardize the dataset by subtracting the mean and dividing by the standard deviation of each feature.
2. Compute the covariance matrix $C$ of the standardized dataset.
3. Compute the eigenvectors and eigenvalues of $C$ using the SVD method.
4. Select the top $k$ eigenvectors based on the amount of variance they explain.
5. Project the original dataset onto the selected eigenvectors to obtain a new dataset of reduced dimensionality.


## Advantages and Disadvantages

### Advantages

- Dimensionality reduction: PCA can be used to reduce the dimensionality of a dataset while retaining as much information as possible. This can help speed up machine learning algorithms and make them more accurate, particularly when dealing with high-dimensional data.
- Information retention: PCA attempts to retain the most important information in the dataset, as measured by the amount of variance explained by each principal component. This can help identify the most important variables that explain the majority of the variation in the data.
- Improved data visualization: PCA can be used to visualize high-dimensional data in lower dimensions. For example, we can use the first two principal components to create a 2D scatter plot that helps us understand the structure of the data.
- Noise reduction: PCA can help remove noise from a dataset by ignoring the components that explain the least amount of variance.


### Disadvantages

- Interpretation can be difficult: The principal components in PCA are linear combinations of the original features, which can make it difficult to interpret the meaning of each component. This can make it challenging to explain the results to non-technical stakeholders.
- Information loss: PCA involves reducing the dimensionality of the data, which inevitably leads to some loss of information. The amount of information lost depends on the number of principal components retained.
- Computational complexity: PCA involves computing the eigenvectors and eigenvalues of the covariance matrix, which can be computationally expensive for large datasets. This can make PCA unsuitable for real-time applications or datasets with a large number of features.
- Assumes linear relationships: PCA assumes that the relationship between the features is linear, which may not be true for all datasets. If the relationships are non-linear, other dimensionality reduction techniques may be more appropriate.

## Dataset
The Breast Cancer Wisconsin (Diagnostic) Dataset is a widely used dataset for classification tasks in machine learning. It is included in the Scikit-learn library and can be easily loaded using the library's built-in functions. The dataset was created by Dr. William H. Wolberg, physician at the University of Wisconsin Hospital at Madison, and contains measurements of fine needle aspirates (FNA) of breast masses from 569 patients. The goal of the dataset is to classify the breast masses as either malignant or benign based on various features extracted from the FNA images.

The dataset contains 30 features, including mean, standard error, and worst (largest) values for the following ten characteristics of each cell nucleus:

* Radius
* Texture
* Perimeter
* Area
* Smoothness
* Compactness
* Concavity
* Concave points
* Symmetry
* Fractal dimension

Each feature is represented as a floating-point number, and there are no missing values in the dataset.

The target variable is a binary variable indicating whether the breast mass is malignant or benign, represented as 0 and 1 respectively. There are 212 cases of malignant masses and 357 cases of benign masses in the dataset.

