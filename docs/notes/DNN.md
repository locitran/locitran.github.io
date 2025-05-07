---
layout: notes
title: Deep Neural Networks
nav_order: 4
---

Deep Neural Networks (DNNs) are nothing but a series of matrix multiplications and activation functions, which we may be familiar with from linear regression. 

There are two main differences I can say:
1. Linear regression uses identity function, i.e., $\sigma(x) = x$, while DNNs use non-linear activation functions, which bring a huge flexibility to the model.
2. Linear regression has only one layer, while DNNs have multiple layers.

In linear regression, the one-layer forward propagation is given by:
$$
\begin{cases}
\mathbf{u} = \mathbf{x} \mathbf{W} + \mathbf{b} & (1) \\
\mathbf{y} = \sigma(\mathbf{u}) & (2)
\end{cases}
\quad \Rightarrow \quad
\mathbf{y} = \sigma(\mathbf{x} \mathbf{W} + \mathbf{b}) = \mathbf{x} \mathbf{W} + \mathbf{b}
$$

Where: 
*   $\mathbf{x} \in \mathbb{R}^{1 \times d}$: input feature vector
*   $\mathbf{W} \in \mathbb{R}^{d \times c}$: weight matrix
*   $\mathbf{b} \in \mathbb{R}^{1 \times c}$: bias vector
*   $\sigma$ is the activation function. 
*   $\mathbf{y} \in \mathbb{R}^{1 \times c}$: predicted output.

Basically, **(1)** is a linear transformation of $\mathbf{x}$ by $\mathbf{W}$, and **(2)** is a non-linear transformation of $\mathbf{u}$ by $\sigma$. By specifying the shape of $\mathbf{W}$, we can control the shape of $\mathbf{y}$. 

In DNNs, the multiple-layer forward propagation is given by:

$$
\begin{cases}
\mathbf{v}^{(0)} = \mathbf{x} & (1) \\
\mathbf{u}^{(l)} = \mathbf{v}^{(l-1)} \mathbf{W}^{(l)} + \mathbf{b}^{(l)} & (2) \\
\mathbf{v}^{(l)} = \sigma(\mathbf{u}^{(l)})  & (3) \\
\mathbf{\hat{y}} = \mathbf{v}^{(L)} & (4)
\end{cases}
$$

Where:
*   $l = 0, 1, 2, \ldots, L$: layer index
*   $\mathbf{v}^{(l)} \in \mathbb{R}^{1 \times d_l}$: output of layer $l$
*   $\mathbf{u}^{(l)} \in \mathbb{R}^{1 \times d_l}$: intermediate variable of layer $l$
*   $\mathbf{W}^{(l)} \in \mathbb{R}^{d_{l-1} \times d_l}$: weight matrix of layer $l$
*   $\mathbf{b}^{(l)} \in \mathbb{R}^{1 \times d_l}$: bias vector of layer $l$

For example, $l = 3$ and $\sigma$ is identical function, then:

$$
\begin{cases}
\mathbf{v}^{(3)} = \mathbf{x} \\
\mathbf{u}^{(3)} = \mathbf{v}^{(2)} \mathbf{W}^{(3)} + \mathbf{b}^{(3)} \\
\mathbf{v}^{(2)} = \sigma(\mathbf{u}^{(2)})  \\
\mathbf{u}^{(2)} = \mathbf{v}^{(1)} \mathbf{W}^{(2)} + \mathbf{b}^{(2)} \\
\mathbf{v}^{(1)} = \sigma(\mathbf{u}^{(1)})  \\
\mathbf{u}^{(1)} = \mathbf{v}^{(0)} \mathbf{W}^{(1)} + \mathbf{b}^{(1)}  \\
\mathbf{v}^{(0)} = \mathbf{x}  \\
\end{cases}
\quad \Rightarrow \quad
\begin{aligned}
\mathbf{v}^{(2)} &= \sigma(\mathbf{v}^{(1)} \mathbf{W}^{(2)} + \mathbf{b}^{(2)}) \\
&= \sigma(\sigma(\mathbf{x} \mathbf{W}^{(1)} + \mathbf{b}^{(1)}) \mathbf{W}^{(2)} + \mathbf{b}^{(2)}) \\
&= \mathbf{x} \mathbf{W}^{(1)} \mathbf{W}^{(2)} + \mathbf{b}^{(1)} \mathbf{W}^{(2)} + \mathbf{b}^{(2)} \\
&= \mathbf{x} \mathbf{W} + \mathbf{b} \quad (\mathbf{W}=\mathbf{W}^{(1)} \mathbf{W}^{(2)}, \mathbf{b}=\mathbf{b}^{(1)} \mathbf{W}^{(2)} + \mathbf{b}^{(2)}) \\
\end{aligned}
$$

