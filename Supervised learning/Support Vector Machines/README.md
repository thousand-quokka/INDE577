# Support Vector Machines (SVM)
![image](https://user-images.githubusercontent.com/120424457/233806683-b46e19c4-10af-4e3d-b838-90ba58df02d2.png)

## Introduction
Support Vector Machines (SVM) is a popular and powerful machine learning algorithm used for classification, regression, and outlier detection. It was first introduced in the 1990s by Vladimir Vapnik and his colleagues, and has since become one of the most widely used algorithms in the field of machine learning.

SVM is a supervised learning algorithm, which means that it learns to classify data based on labeled examples. It works by constructing a hyperplane in a high-dimensional space that maximally separates the different classes. In the case of a binary classification problem, the hyperplane is used to divide the data into two regions, one for each class.

## Generalized Algorithm: 

Support Vector Machines (SVM) is a supervised learning algorithm that seeks to find a hyperplane which best separates two classes in a dataset. The hyperplane is represented by the equation:

$$w^Tx - b = 0$$

where $w$ is a weight vector, $x$ is the input vector, and $b$ is the bias.

The SVM algorithm seeks to maximize the margin between the two classes, which is the distance between the hyperplane and the closest point from each class. The margin can be expressed as:

$$\frac{2}{\|w\|} $$

where $\|w\|$ is the Euclidean norm of the weight vector. Therefore, the SVM optimization problem can be formulated as:

$$\begin{align}
\text{minimize } & \frac{1}{2}\|w\|^2 \\
\text{subject to } & y_i(w^Tx_i - b) \geq 1 \text{, for } i=1,2,...,n
\end{align}$$

where $y_i$ is the class label of the $i$-th training example, and $n$ is the number of training examples. The inequality constraint ensures that each training example is on the correct side of the hyperplane.

If the data is not linearly separable, SVM can still be used by introducing slack variables $\xi_i \geq 0$ for each training example, and modifying the optimization problem to:

$$\begin{align}
\text{minimize } & \frac{1}{2}\|w\|^2 + C\sum_{i=1}^{n}\xi_i \\
\text{subject to } & y_i(w^Tx_i - b) \geq 1 - \xi_i \text{, for } i=1,2,...,n \\
& \xi_i \geq 0 \text{, for } i=1,2,...,n
\end{align}$$

where $C$ is a hyperparameter that controls the tradeoff between maximizing the margin and minimizing the sum of slack variables.

In order to handle non-linearly separable data, SVM uses kernel functions to map the input data into a higher-dimensional feature space. The most commonly used kernel functions are:

- Linear kernel: $K(x_i,x_j) = x_i^Tx_j$
- Polynomial kernel: $K(x_i,x_j) = (1 + x_i^Tx_j)^d$
- RBF (Radial Basis Function) kernel: $K(x_i,x_j) = \exp\left(-\gamma\|x_i-x_j\|^2\right)$
- Sigmoid kernel: $K(x_i,x_j) = \tanh(\alpha x_i^Tx_j + c)$

where $d$, $\gamma$, $\alpha$, and $c$ are hyperparameters that control the shape of the kernel function.

SVM is a powerful algorithm with many applications in various fields. Its mathematical formulation provides a clear understanding of how the algorithm works and how it can be used to classify different types of data.

## Advantages and Disadvantages

### Advantages

- SVM works well with high-dimensional data, where the number of features is much larger than the number of examples.
- SVM is effective in handling non-linearly separable data by using kernel functions to map the data into a higher-dimensional feature space.
- SVM is robust to outliers, as it focuses on the examples that are closest to the decision boundary (the support vectors), rather than all the examples in the dataset.
- SVM has a unique solution, which is the global minimum of the optimization problem, as long as the problem is convex and the data is linearly separable.
- SVM can be used for both classification and regression problems, by modifying the loss function and the optimization problem accordingly.


### Disadvantages

- SVM can be sensitive to the choice of kernel function and hyperparameters, which can be difficult to tune and can impact the performance of the algorithm.
- SVM is computationally expensive, especially when dealing with large datasets or non-linearly separable data, as it involves solving a quadratic programming problem.
- SVM does not provide probabilities for classification, only a hard decision boundary, which can be a limitation in some applications.
- SVM can be sensitive to the quality of the training data, and may perform poorly if the data is noisy or contains errors.
- SVM can be difficult to interpret, as the hyperplane in the high-dimensional feature space may not correspond to a clear separation of the input features.


## Dataset
Fashion MNIST is a popular dataset for image classification tasks. It consists of a collection of 70,000 grayscale images of fashion items, such as shirts, dresses, shoes, and bags. The dataset is divided into a training set of 60,000 images and a test set of 10,000 images.

Each image in the Fashion MNIST dataset is a 28x28 grayscale image, and each pixel value ranges from 0 to 255. The dataset contains 10 different classes, with each class representing a different fashion item. The classes are as follows:

* T-shirt/top
* Trouser
* Pullover
* Dress
* Coat
* Sandal
* Shirt
* Sneaker
* Bag
* Ankle boot

The Fashion MNIST dataset is often used as a benchmark dataset for testing new machine learning algorithms and computer vision models.
