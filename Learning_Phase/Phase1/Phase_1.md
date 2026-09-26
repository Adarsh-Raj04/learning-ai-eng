# Phase 1 — Mathematics for Machine Learning

## Complete Summary & Revision Sheet

> **Goal of Phase 1:** Build enough mathematical understanding to know what is happening behind ML/AI systems, derive foundational algorithms, and be ready for Deep Learning, GenAI, and Agentic AI engineering — without going into research-level mathematics.

---

# Phase 1 Roadmap

1. Linear Algebra
2. Calculus
3. Probability
4. Statistics
5. Optimization
6. Phase 1 Projects

**Status:** Linear Algebra ✅ | Calculus ✅ | Probability ✅ | Statistics ✅ | Optimization ✅

---

# 1. Linear Algebra

## 1.1 Scalars

A **scalar** is a single numerical value.
Example:

$$
x=5
$$

Used for individual values such as a learning rate, bias, temperature, or a single feature.

---

## 1.2 Vectors

A **vector** is an ordered collection of numbers.

$$
\mathbf{x}=
\begin{bmatrix}
x_1\\
x_2\\
x_3
\end{bmatrix}
$$

A vector can represent:

- Features of one data point
- An embedding
- A direction
- Model parameters

---

## 1.3 Vector Magnitude / L2 Norm

$$
\|\mathbf{x}\|_2=
\sqrt{x_1^2+x_2^2+\cdots+x_n^2}
$$

It represents the length of a vector.

---

## 1.4 Distance Between Vectors

$$
\|\mathbf{x}-\mathbf{y}\|_2
$$

It measures how far two vectors are from each other.

### ML relevance

Used in:

- Similarity search
- Clustering
- Embeddings
- Vector databases

---

## 1.5 Dot Product

$$
\sum_i x_i y_i
$$

For:

$$
\mathbf{x}=[x_1,x_2]
$$

$$
\mathbf{y}=[y_1,y_2]
$$

$$
\mathbf{x}\cdot\mathbf{y}=x_1y_1+x_2y_2
$$

### ML relevance

Dot products appear everywhere:

- Similarity
- Linear models
- Neural networks
- Attention
- Embeddings

---

## 1.6 Norms

### L1 Norm

$$
\|\mathbf{x}\|_1=\sum_i|x_i|
$$

### L2 Norm

$$
\|\mathbf{x}\|_2=\sqrt{\sum_i x_i^2}
$$

---

## 1.7 Unit Vector

A unit vector has magnitude 1.

$$
|\mathbf{u}|=1
$$

---

## 1.8 Normalization

To convert a non-zero vector into a unit vector:

$$
\boxed{
\mathbf{x}_{norm}=
\frac{\mathbf{x}}{|\mathbf{x}|}
}
$$

Important:
**Normalization here means making the vector's norm equal to 1. It does not necessarily mean forcing every value into the 0–1 range.**

### ML relevance

Important for:

- Embeddings
- Similarity search
- Vector databases

---

## 1.9 Orthogonality

Two vectors are orthogonal when their dot product is zero.

$$
\boxed{\mathbf{x}\cdot\mathbf{y}=0}
$$

For non-zero vectors, this means they are perpendicular.

---

## 1.10 Projection

Projection represents how much of one vector lies in the direction of another.
Projection of $\mathbf{a}$ onto $\mathbf{b}$:

$$
\frac{\mathbf{a}\cdot\mathbf{b}}
{\mathbf{b}\cdot\mathbf{b}}\mathbf{b}
$$

### ML relevance

Projection is important for:

- Dimensionality reduction
- PCA intuition
- Feature representations

---

# 2. Matrices

## 2.1 Matrix

A matrix is a rectangular arrangement of numbers.

$$
X=
\begin{bmatrix}
x_{11}&x_{12}\\
x_{21}&x_{22}
\end{bmatrix}
$$

In ML, a dataset is commonly represented as a matrix:

$$
X\in\mathbb{R}^{n\times d}
$$

where:

- (n) = number of samples
- (d) = number of features

---

## 2.2 Matrix Addition

Matrices of the same shape can be added element-wise.

$$
A+B
$$

---

## 2.3 Scalar Multiplication

Every element is multiplied by the scalar.

$$
cA
$$

---

## 2.4 Transpose

Rows become columns.

$$
A^T
$$

---

## 2.5 Matrix Multiplication

For:

$$
A\in\mathbb{R}^{m\times n}
$$

and:

$$
B\in\mathbb{R}^{n\times p}
$$

the result is:

$$
AB\in\mathbb{R}^{m\times p}
$$

Each output element is a **row × column dot product**.

### ML relevance

Matrix multiplication is fundamental to:

- Linear regression
- Neural networks
- Transformers
- Attention
- LLMs

---

## 2.6 Identity Matrix

The identity matrix acts like the number 1 for matrix multiplication.

$$
AI=IA=A
$$

---

## 2.7 Matrix Inverse

The inverse reverses a matrix transformation.

$$
AA^{-1}=A^{-1}A=I
$$

A matrix has an inverse only when it is invertible.

---

## 2.8 Determinant

The determinant is a scalar associated with a square matrix.
For:

$$
A=
\begin{bmatrix}
a&b\\
c&d
\end{bmatrix}
$$

$$
\det(A)=ad-bc
$$

Important relationship:

$$
\boxed{\det(A)=0\Rightarrow A\text{ has no inverse}}
$$

---

## 2.9 Linear Transformation

A matrix can transform vectors:

$$
\mathbf y=A\mathbf x
$$

The transformation can change:

- Direction
- Magnitude
- Orientation
- Relationships between components

---

## 2.10 The ML Expression (XW+b)

A core ML operation is:

$$
\boxed{Z=XW+b}
$$

where:

- (X) = input/features
- (W) = weights
- (b) = bias
- (Z) = transformed output

This is the foundation of a neural-network layer.

---

## 2.11 Eigenvalues and Eigenvectors

For a matrix (A):

$$
\boxed{A\mathbf v=\lambda\mathbf v}
$$

where:

- $\mathbf{v}$ = eigenvector
- $\lambda$ = eigenvalue

The transformation changes the magnitude of an eigenvector without changing its direction.

### ML relevance

Useful for understanding:

- PCA
- Matrix transformations
- Dimensionality reduction

---

## 2.12 SVD

Singular Value Decomposition decomposes a matrix:

$$
\boxed{A=U\Sigma V^T}
$$

Conceptually, it breaks a matrix transformation into simpler transformations.

### ML relevance

Useful for understanding:

- Dimensionality reduction
- Matrix approximation
- Latent representations

---

# 3. Calculus

## 3.1 Function

A function maps inputs to outputs.

$$
y=f(x)
$$

ML models are essentially functions that map inputs to predictions.

---

## 3.2 Limit

A limit describes the value a function approaches as its input approaches a particular value.

$$
\lim_{x\to a}f(x)
$$

### ML relevance

Provides the mathematical foundation for derivatives and continuous optimization.

---

## 3.3 Derivative

The derivative measures how quickly a function changes with respect to its input.

$$
\boxed{
\frac{dy}{dx}
}
$$

### Example

$$
y=x^2
$$

$$
\frac{dy}{dx}=2x
$$

### ML relevance

Tells us how changing a parameter changes the loss.

---

## 3.4 Partial Derivative

Used when a function has multiple variables.

$$
L(x,y)
$$

Partial derivative with respect to (x):

$$
\frac{\partial L}{\partial x}
$$

It measures the effect of changing (x) while treating the other variables as fixed.

---

## 3.5 Gradient

The gradient contains all first-order partial derivatives.
For:

$$
L(x,y)
$$

$$
\boxed{
\nabla L=
\begin{bmatrix}
\frac{\partial L}{\partial x}\\
\frac{\partial L}{\partial y}
\end{bmatrix}
}
$$

### ML relevance

The gradient tells an optimizer how the loss changes with respect to model parameters.

---

## 3.6 Chain Rule

For:

$$
y=f(g(x))
$$

The chain rule is:

$$
\frac{dy}{dx}
=
\frac{dy}{dg}
\frac{dg}{dx}
$$

### ML relevance

The chain rule is the mathematical foundation of **backpropagation**.

---

## 3.7 Computational Graph

A computational graph represents a calculation as connected operations.
Example:

$$
x,w,b
\rightarrow
z=wx+b
\rightarrow
L=z^2
$$

### ML relevance

Neural networks can be represented as computational graphs, allowing gradients to be calculated systematically.

---

## 3.8 Backpropagation

Backpropagation calculates gradients of the loss with respect to model parameters by applying the chain rule backward through the computational graph.

### ML relevance

It allows neural networks to determine how their weights should change during training.

---

## 3.9 Gradient Descent

$$
\theta_{new}=\theta-\eta\nabla L(\theta)
$$

where:

- $\theta$ = parameters
- $\eta$ = learning rate
- $\nabla L$ = gradient

### ML relevance

Moves model parameters toward lower loss.

---

## 3.10 Jacobian

For a vector-valued function:

$$
\mathbf f(x_1,\ldots,x_n)
$$

the Jacobian contains all first-order partial derivatives.

$$
\frac{\partial f_i}{\partial x_j}
$$

### ML relevance

Useful for understanding vector transformations and derivatives in neural-network computations.

---

## 3.11 Hessian

The Hessian contains second-order partial derivatives.

$$
\frac{\partial^2L}{\partial x_i\partial x_j}
$$

### ML relevance

Describes curvature of a loss function and is useful for understanding optimization.

---

# 4. Probability

## 4.1 Random Variable

A random variable maps outcomes of a random experiment to numerical values.
Example:

$$
X=\text{number of heads}
$$

---

## 4.2 Probability Distribution

A distribution describes the probabilities associated with possible values of a random variable.

---

## 4.3 Conditional Probability

$$
\boxed{
P(A|B)=\frac{P(A\cap B)}{P(B)}
}
$$

It represents the probability of (A) given that (B) occurred.

### ML relevance

Important for conditional prediction and probabilistic reasoning.

---

## 4.4 Bayes' Theorem

$$
\boxed{
P(A|B)=
\frac{P(B|A)P(A)}
{P(B)}
}
$$

### ML relevance

Used in probabilistic inference and provides intuition for updating beliefs using evidence.

---

## 4.5 Expectation

$$
\boxed{
E[X]=\sum_xxP(X=x)
}
$$

Expectation represents the probability-weighted average outcome.

### ML relevance

Important throughout ML and statistics.

---

## 4.6 Variance

$$
\boxed{
Var(X)=E[(X-\mu)^2]
}
$$

Equivalent form:

$$
Var(X)=E[X^2]-(E[X])^2
$$

It measures how spread out values are around the mean.

---

## 4.7 Covariance

$$
Cov(X,Y)=E[(X-E[X])(Y-E[Y])]
$$

It measures how two variables vary together.

---

## 4.8 Bernoulli Distribution

A Bernoulli random variable has two possible outcomes, usually 0 and 1.

$$
\boxed{
P(X=x)=p^x(1-p)^{1-x}
}
$$

where:

$$
x\in{0,1}
$$

---

## 4.9 Binomial Distribution

Models the number of successes in (n) independent Bernoulli trials.

$$
\boxed{
P(X=k)=
\binom nk
p^k(1-p)^{n-k}
}
$$

---

## 4.10 Gaussian / Normal Distribution

A Gaussian distribution is represented as:

$$
\boxed{
X\sim N(\mu,\sigma^2)
}
$$

where:

- $\mu$ = mean
- $\sigma^2$ = variance
- $\sigma$ = standard deviation

---

## 4.11 Likelihood

Likelihood measures how plausible observed data is under a particular parameter value.

$$
\boxed{
L(\theta|Data)=P(Data\mid\theta)
}
$$

The notation emphasizes that the data is observed and we evaluate different parameter values.

---

## 4.12 Maximum Likelihood Estimation — MLE

MLE chooses the parameter that maximizes the likelihood:

$$
\arg\max_\theta P(Data\mid\theta)
$$

### ML relevance

Provides the foundation for estimating model parameters from observed data.

---

## 4.13 Maximum A Posteriori — MAP

MAP incorporates a prior:

$$
\arg\max_\theta P(Data\mid\theta)P(\theta)
$$

### Key difference

- MLE → likelihood
- MAP → likelihood + prior

---

## 4.14 LLM Token Probabilities

An LLM predicts the probability distribution of the next token:

$$
\boxed{
P(\text{next token}|\text{context})
}
$$

Example:

```
"The capital of France is"
```

The model assigns probabilities to possible next tokens such as:

```
Paris → high probability
London → lower probability
Tokyo → lower probability
```

### ML relevance

This is the probabilistic foundation of next-token prediction.

---

# 5. Statistics

## 5.1 Mean

$$
\frac{1}{n}\sum_{i=1}^{n}x_i
$$

Represents the average of the observations.

---

## 5.2 Median

The middle value after sorting the data.
Median is less sensitive to extreme outliers than the mean.

---

## 5.3 Mode

The most frequently occurring value.

---

## 5.4 Population vs Sample

### Population

The complete group being studied.

### Sample

A subset selected from the population.
Example:

```
10,000 employees → Population
500 selected employees → Sample
```

---

## 5.5 Population Variance

$$
\boxed{
\sigma^2=
\frac{1}{N}
\sum_{i=1}^{N}(x_i-\mu)^2
}
$$

---

## 5.6 Sample Variance

$$
\boxed{
s^2=
\frac{1}{n-1}
\sum_{i=1}^{n}(x_i-\bar{x})^2
}
$$

---

## 5.7 Standard Deviation

$$
\boxed{
\sigma=\sqrt{\sigma^2}
}
$$

It measures spread in the same units as the original data.

---

## 5.8 Standardization

$$
\boxed{
z=\frac{x-\mu}{\sigma}
}
$$

It tells how many standard deviations a value is from the mean.

---

## 5.9 Confidence Interval

A common large-sample 95% CI for a mean is:

$$
\boxed{
\bar{x}
\pm
1.96\frac{\sigma}{\sqrt n}
}
$$

The interval expresses uncertainty around an estimated mean under the assumptions of the interval calculation.

---

## 5.10 Hypothesis Testing

Typical structure:

- $H_0$ = null hypothesis
- $H_1$ = alternative hypothesis
- Calculate a test statistic
- Calculate a p-value
- Compare with a chosen significance level $\alpha$

If:

$$
p<\alpha
$$

we reject $H_0$.
Important:
A p-value is **not** the probability that the alternative hypothesis is true.

---

## 5.11 Correlation

Pearson correlation:

$$
\boxed{
r=
\frac{Cov(X,Y)}
{\sigma_X\sigma_Y}
}
$$

Range:

$$
-1\le r\le1
$$

It measures the strength and direction of a linear relationship.
**Correlation does not imply causation.**

---

## 5.12 Bias-Variance Tradeoff

Expected prediction error can be conceptually decomposed as:

$$
\boxed{
Bias^2+Variance+\text{Irreducible Noise}
}
$$

### High Bias

Usually associated with underfitting.

```
Training performance → poor
Validation performance → poor
```

### High Variance

Usually associated with overfitting.

```
Training performance → very good
Validation performance → much worse
```

---

## 5.13 Generalization

Generalization is the ability of a model to perform well on unseen data.

### ML relevance

The goal is not simply to memorize training data but to learn patterns that transfer to new examples.

---

# 6. Optimization

## 6.1 Objective / Loss Function

The loss measures how wrong the model is.
Example MSE:

$$
\boxed{
L=
\frac{1}{n}
\sum_{i=1}^{n}
(y_i-\hat y_i)^2
}
$$

Training attempts to minimize the loss.

---

## 6.2 Convexity

A convex objective has a bowl-like optimization landscape.
Important intuition:

$$
\boxed{
\text{For a convex problem, a local minimum is a global minimum.}
}
$$

---

## 6.3 Gradient Descent

$$
\theta_{new}=\theta-\eta\nabla L
$$

The gradient points toward increasing loss, so we move in the opposite direction.

---

## 6.4 SGD

Uses one example per update.

$$
\theta_{t+1}=\theta_t-\eta\nabla L_i(\theta_t)
$$

---

## 6.5 Mini-Batch GD

Uses a small batch of examples:

$$
\theta_{t+1}
=
\theta_t
-
\eta
\frac{1}{B}
\sum_{i=1}^{B}
\nabla L_i(\theta_t)
$$

---

## 6.6 Momentum

Uses previous gradient information to smooth and accelerate optimization.

$$
v_t=
\beta v_{t-1} + (1-\beta)\nabla L(\theta_t)
$$

$$
\theta_{t+1}=\theta_t-\eta v_t
$$

---

## 6.7 Adam

Adam combines momentum-like estimates with adaptive scaling.

$$
m_t=
\beta_1m_{t-1} + (1-\beta_1)g_t
$$

$$
v_t=
\beta_2v_{t-1} + (1-\beta_2)g_t^2
$$

Then, using bias-corrected estimates:

$$
\theta_{t+1}
=
\theta_t
-
\eta
\frac{\hat m_t}{\sqrt{\hat v_t}+\epsilon}
$$

### ML relevance

Adam is widely used in neural-network training.

---

## 6.8 Learning Rate

The learning rate controls update size.

$$
\theta_{new}=\theta-\eta\nabla L
$$

- Too small → slow training
- Too large → unstable training / overshooting

---

## 6.9 Regularization

Regularization adds a penalty to control model complexity.

### L1

$$
L_{\text{total}}=L+\lambda\sum_i|w_i|
$$

Tends to push some weights toward zero.

### L2

$$
L_{\text{total}}=L+\lambda\sum_iw_i^2
$$

Penalizes large weights.

### ML relevance

Helps reduce overfitting and improve generalization.

---

# 7. The Complete Mathematical ML Flow

This is the most important connection across Phase 1:

$$
\boxed{
X
\rightarrow
f(X;\theta)
\rightarrow
\hat y
\rightarrow
L(y,\hat y)
\rightarrow
\nabla_\theta L
\rightarrow
Optimizer
\rightarrow
\theta_{new}
}
$$

In words:

```
Input
  ↓
Model / Function
  ↓
Prediction
  ↓
Loss
  ↓
Derivative / Gradient
  ↓
Optimization
  ↓
Updated Parameters
  ↓
Better Prediction
  ↓
Repeat
```

---

# 8. How the Phase 1 Topics Connect

## Linear Algebra → Model Representation

Vectors and matrices represent:

- Data
- Features
- Weights
- Embeddings
- Transformations

Core operation:

$$
XW+b
$$

---

## Calculus → Learning

Derivatives and gradients tell us:

> How does changing a parameter change the loss?

Core operation:

$$
\nabla L
$$

---

## Probability → Uncertainty & Prediction

Probability tells us:

> How likely is an outcome?

Core concepts:

$$
P(A|B),\quad E[X],\quad Var(X),\quad P(\text{token}|\text{context})
$$

---

## Statistics → Data & Evaluation

Statistics tells us:

> What can we infer from data, and how reliable is that inference?

Core concepts:

- Sampling
- Mean / variance
- Confidence intervals
- Hypothesis testing
- Correlation
- Bias / variance
- Generalization

---

## Optimization → Learning the Parameters

Optimization tells us:

> How do we change model parameters so the loss decreases?

Core operation:

$$
\theta_{new}=\theta-\eta\nabla L
$$

---

# 9. One Mental Model for the Entire Phase

Think of ML as:

### Step 1 — Represent the data

$$
X
$$

**Linear Algebra**
↓

### Step 2 — Build a function

$$
\hat y=f(X;\theta)
$$

**Linear Algebra + Calculus**
↓

### Step 3 — Measure error

$$
L(y,\hat y)
$$

**Statistics / Probability / Optimization**
↓

### Step 4 — Understand how parameters affect error

$$
\nabla_\theta L
$$

**Calculus**
↓

### Step 5 — Update parameters

$$
\theta_{new}=\theta-\eta\nabla L
$$

**Optimization**
↓

### Step 6 — Evaluate uncertainty and generalization

**Probability + Statistics**
↓

### Step 7 — Repeat

$$
\boxed{
\text{Learn parameters that generalize to unseen data}
}
$$

---

# 10. What You Should Be Able to Explain After Phase 1

You should now be able to explain, at a foundational AI Engineer level:

- What vectors and matrices represent in ML
- Why dot products are important
- How matrix multiplication powers neural-network layers
- What embeddings are mathematically
- Why vector similarity works
- What derivatives represent
- Why gradients are needed for training
- How the chain rule leads to backpropagation
- What probability distributions represent
- How likelihood differs from probability intuition
- MLE vs MAP
- Why LLMs predict token probabilities
- Mean, variance, covariance, correlation
- Population vs sample
- Confidence intervals and hypothesis testing
- Bias vs variance
- Underfitting vs overfitting
- What a loss function does
- How Gradient Descent works
- Batch GD vs SGD vs Mini-batch GD
- Why Momentum exists
- What Adam does at a high level
- How learning rate affects training
- Why L1/L2 regularization is used
- The complete prediction → loss → gradient → update training loop

---

# 11. Phase 1 → Next Phase

With these foundations, the next practical step is:

## Phase 1 Projects

### Project 1 — Linear Regression From Scratch

Implement using:

- Python
- NumPy
- Mathematics from Phase 1

Understand:

$$
\hat y=XW+b
$$

$$
MSE=
\frac{1}{n}\sum(y-\hat y)^2
$$

$$
\nabla L
$$

$$
W_{new}=W-\eta\nabla L
$$

**No sklearn for the first implementation.**

---

### Project 2 — Logistic Regression From Scratch

Understand:

$$
z=XW+b
$$

$$
\sigma(z)=\frac{1}{1+e^{-z}}
$$

Then:

$$
P(y=1|X)=\sigma(z)
$$

and train using a suitable classification loss and gradient-based optimization.

---

### Project 3 — Gradient Descent From Scratch

Implement Gradient Descent explicitly using NumPy and visualize the optimization process.

---

# Phase 1 Final Status

$$
\text{ML Mathematical Foundation}
$$

**Phase 1 Foundations: COMPLETE ✅**
**Next: From Mathematics → Working ML Models**
