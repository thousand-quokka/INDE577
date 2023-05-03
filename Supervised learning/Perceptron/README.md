# Perceptron
![image](https://user-images.githubusercontent.com/120424457/233535540-ade16c9c-93cc-45c7-b48e-545993f5c111.png)

## Introduction
The Perceptron algorithm is a type of supervised learning algorithm for binary classification problems, where we try to classify data into one of two categories. It is based on a simple artificial neuron called a "perceptron" that takes a set of inputs and produces a single output. The algorithm is iterative, and it works by updating the weights of the inputs to the perceptron based on the errors made in classification.

## Generalized Algorithm: 

Given a set of inputs $\mathbf{x} = [x_1, x_2, ..., x_n]^T$ and corresponding true labels $y$, we start with a set of initial weights $\mathbf{w} = [w_0, w_1, ..., w_n]^T$ and bias $b$. We denote the activation function as $\phi(z)$, where $z$ is the weighted sum of inputs and bias:

$$z = \mathbf{w} \cdot \mathbf{x} + b$$

The output of the activation function is then compared to the true label to compute the error $e$:

$$\hat{y} = \phi(z)$$
$$e = y - \hat{y}$$

The weights and bias are then updated based on the error and learning rate $\eta$:

$$w_i = w_i + \eta e x_i$$
$$b = b + \eta e$$

This process is repeated for each input in the training set until the algorithm converges, meaning that it is no longer making any errors or is making only a small number of errors. The final output of the perceptron for a new input $\mathbf{x}_\text{new}$ can be computed as:

$\hat{y}_\text{new} = \phi(\mathbf{w} \cdot \mathbf{x}_\text{new} + b)$


This is the basic algorithm for a single-layer perceptron. For multi-layer perceptrons, the process is similar but with additional layers and activation functions.

## Advantages and Disadvantages

### Advantages

- Simplicity: The perceptron algorithm is a simple and easy-to-understand algorithm. It has a straightforward mathematical formulation, making it a great choice for beginners in the field of machine learning.

- Convergence: The perceptron algorithm is guaranteed to converge if the training set is linearly separable. This means that it will eventually learn to correctly classify all training examples.

- Fast training: The perceptron algorithm is computationally efficient and can be trained quickly, even on large datasets.

- Robustness: The perceptron algorithm is relatively robust to noise in the data and can handle mislabeled or noisy examples without affecting its overall performance.


### Disadvantages

- Limited to linearly separable data: The perceptron algorithm can only classify linearly separable data. This means that if the data cannot be separated by a linear boundary, the perceptron will not be able to learn an accurate classification function.

- Sensitivity to initial weights: The performance of the perceptron algorithm can be sensitive to the initial weights and biases. If the initial weights are set poorly, the algorithm may not converge or may converge to a suboptimal solution.

- Lack of probabilistic output: The perceptron algorithm does not output a probability estimate for the classification, only a binary decision boundary. This makes it less suitable for applications that require probabilistic estimates, such as Bayesian inference.

- Inability to learn complex patterns: The perceptron algorithm is limited in its ability to learn complex patterns and relationships in the data. It can only learn linear decision boundaries, which may not be sufficient for more complex classification problems.

- Lack of generalization: The perceptron algorithm tends to overfit the training data, which can lead to poor generalization to new, unseen examples. Regularization techniques can be used to address this issue, but they can also increase the complexity of the algorithm.

## Dataset
The Penguins Dataset contains size measurements for three penguin species observed on three islands in the Palmer Archipelago, Antarctica. These data were collected from 2007 - 2009 by Dr. Kristen Gorman's team. It consists of 344 rows and 7 columns. The three different species of penguins are Chinstrap, Adélie, and Gentoo penguins. Download link is: [palmer penguine dataset](https://www.kaggle.com/datasets/parulpandey/palmer-archipelago-antarctica-penguin-data).
* species
* island
* bill_length(mm)
* bill_depth(mm)
* flipper_length(mm)
* body_mass(g)
* sex
