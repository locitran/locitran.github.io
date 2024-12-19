---
layout: notes
title: Deep Neural Networks
nav_order: 4
---

- An input consists of a feature vector $\mathbf{x} \in \mathbb{R}^{1 \times d}$, where $d$ is the number of features. 
- True label is $\mathbf{y} \in \mathbb{R}^{1 \times c}$, where $c$ is the number of classes.
- Predicted value is $\mathbf{\hat{y}} \in \mathbb{R}^{1 \times c}$.

A forward propagation through $L$ layers is given by:

$$
\begin{cases}
\mathbf{v}^{(0)} = \mathbf{x} & (1) \\
\mathbf{u}^{(l)} = \mathbf{v}^{(l-1)} \mathbf{W}^{(l)} + \mathbf{b}^{(l)} & (2) \\
\mathbf{v}^{(l)} = \sigma(\mathbf{u}^{(l)})  & (3) \\
\mathbf{\hat{y}} = \mathbf{v}^{(L)} & (4)
\end{cases}
$$

Where layer $l = 1, 2, \ldots, L$ and $\sigma$ is the activation function. Basically, the forward propagation is a series of matrix multiplications and activation functions. Starting from **Eq. 2**, the input is transformed/propagated through the network until the output layer. $\mathbf{u}^{(l)}$ and $\mathbf{v}^{(l)}$ are intermediate values at layer $l$ that may not be visible to the user, hence it's called a hidden layer. The weight matrix $\mathbf{W}^{(l)} \in \mathbb{R}^{d_{l-1} \times d_l}$ and bias vector $\mathbf{b}^{(l)} \in \mathbb{R}^{1 \times d_l}$ are the parameters that are learned during training.

