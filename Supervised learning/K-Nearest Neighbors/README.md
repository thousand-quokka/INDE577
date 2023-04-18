## Objective
In this project, it will focus on implementing the K Nearest Neighbors algorithm on the 'red wine' data. 

## Data
In this assignment, we will explore KNN method on adataset named "Red wine". It contains 1599 samples,12 columns. Download link is: [link](https://archive.ics.uci.edu/ml/datasets/wine+quality)
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
## Packages
The following packages will be needed to run the code below:
*   matplotlib.pyplot: [documentation](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.html)
*   numpy: [documentation](https://numpy.org/devdocs/)
*   pandas: [documentation](https://pandas.pydata.org/docs/)
*   sklearn: [documentation](https://scikit-learn.org/stable/)
*   seaborn: [documentation](https://seaborn.pydata.org/)

## References
1. k-NN ( k-Nearest Neighbors) Starter Guide: https://machinelearninghd.com/k-nn-k-nearest-neighbors-starter-guide/
2. Advantages and Disadvantages of KNN Algorithm in Machine Learning: http://theprofessionalspoint.blogspot.com/2019/02/advantages-and-disadvantages-of-knn.html


{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "---\n",
    "\n",
    "## K-Nearest Neighbors (KNN) Algorithm and Applications\n",
    "#### Language: Python 3.8.8\n",
    "#### Author: Tianjian Sun\n",
    "\n",
    "---"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### Table of Contents\n",
    "\n",
    "* [Introduction](#Introduction)\n",
    "* [Algorithm](#Algorithm)\n",
    "* [Illustration](#Illustration)\n",
    "* [Advantages and Disadvantages](#Advantages_and_Disadvantages)\n",
    "    * [Advantages](#Advantages)\n",
    "    * [Disadvantages](#Disadvantages)\n",
    "* [Code of KNN classifier and regressor](#Code)\n",
    "* [Applications on data sets](#Applications)\n",
    "    * [Classification problem](#Classification)\n",
    "    * [Regression problem](#Regression)\n",
    "* [How can $k$ impact prediction result](#k)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### Introduction <a class=\"anchor\" id=\"Introduction\"></a>\n",
    "In this section we focus on a simple and straight-forward machine learning model, k-nearest neighbors (KNN). \n",
    "\n",
    "KNN is a non-parametric supervised model, and its main idea is to classify or regress by compute the k closest training examples in the data set. "
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "---\n",
    "\n",
    "### Algorithm <a class=\"anchor\" id=\"Algorithm\"></a>\n",
    "*k* is a pre-defined constant, and for\n",
    "* classification tasks.\n",
    "An unlabeled data point is classified by assigning the label which is most frequent among the *k* training samples nearest to that query point.\n",
    "\n",
    "* regression tasks.\n",
    "An unlabeled data point is predicted by averaging the values among the k training samples nearest to that query point. \n",
    "\n",
    "More formally, k-nearest-neighbor methods use those observations in the training set $T$ closest in input space to x to form $\\hat{y}$. Specifically, the k-nearest neighbor fit for $\\hat{y}$ is defined as follows:\n",
    "\n",
    "$$\\hat{y} = \\frac{1}{k} \\sum_{x_i \\in N_k(x)}{x_i}$$\n",
    "\n",
    "where $N_k(x)$ is the neighborhood of $x$ defined by the $k$ closest points $x_i$ in the training sample. Closeness implies a metric, which for the moment Euclidean distance is the most commonly-used distance. So, in words, we find the k observations with $x_i$ closest to $x$ in input space, and average their responses. \n",
    "\n",
    "For classification problems, labels are binary coded so $\\hat{y}$ is the proportion of the class of '1', and it represents a majority vote in the neighborhood. For regression problems, labels are numeric so $\\hat{y}$ is the average of neighborhoods.\n",
    "\n",
    "Euclidean distance, which is the most commonly-used distance to calculate the distance between data points, is defined as follows:\n",
    "\n",
    "$$ d(\\boldsymbol{x}_i, \\boldsymbol{x}_j) = \\sqrt{\\sum_{k=1}^{p} {(\\boldsymbol{x}_{ik}-\\boldsymbol{x}_{jk})^2}}  $$\n",
    "\n",
    "where $\\boldsymbol{x}_i$, $\\boldsymbol{x}_j$ are two $1 \\times p$ data point vectors.\n",
    "\n",
    "Notice that the neighbors are taken from known data set, it can be thought of as the training data set for the algorithm, but in fact no explicit training step is required.\n"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "---\n",
    "\n",
    "### Illustration <a class=\"anchor\" id=\"Illustration\"></a>\n",
    "\n",
    "Take a look at the two-dimension space, we can have a intuitive idea about how knn works. The following figure by Navlani ([link](https://www.datacamp.com/community/tutorials/k-nearest-neighbor-classification-scikit-learn)) clearly illustrates the algorithm of knn. \n",
    "\n",
    "Given the samples and the new data point in the sample space, distances between the new example data point and all other points are calculated and ranked ascending. Then the first $k$ samples are picked up, and a majority vote (for classification) or an average (for regression) is taken among the top $k$ samples to predict label of the new example.\n",
    "\n",
    "![knn_illu](images/knn_illu.png)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "---\n",
    "\n",
    "### Advantages and Disadvantages <a class=\"anchor\" id=\"Advantages_and_Disadvantages\"></a>\n",
    "\n",
    "#### Advantages: <a class=\"anchor\" id=\"Advantages\"></a>\n",
    "\n",
    "* No training period. As discussed before, knn does not have a training period. This kind of learning model is called lazy learner (Instance based learning), which uses sample data set directly to make real-time predictions based on some algorithms. Thus knn is faster than some other algorithms which require training period (who are called eager learners).\n",
    "\n",
    "* Supper simple. Knn is a very simple model which requires less computational resource, and it's eazy to implement. Also only two hyper-parameters, number of neighbors $k$ and distance function are required to be determined befor implying the algorithm.\n",
    "\n",
    "* No assumptions needed. Knn requires no assumption on data distribution or other properties.\n",
    "\n",
    "#### Disadvantages: <a class=\"anchor\" id=\"Disadvantages\"></a>\n",
    "\n",
    "* Poor with large dataset. Computationally expensive when calculation the distances among all samples if the number of data is huge. \n",
    "\n",
    "* Poor with high dimensions. When number of dimension is high, it's hard for knn to represent the relative space relationship between data points, as data points become supper sparse. Also scales of different dimensions can largely affect the distances between points, so feature scaling must be down before using knn. Moreover, it's also computationally expensive to calculate the distances.\n",
    "\n",
    "* Outlier, noise and missing value sensitivity. KNN is sensitive to noise and outliers in the dataset, and it cannot deal with missing values."
   ]
  }
