---
layout: post
title: "Frequently Asked Questions (and Answers)"
author: MMA
social: true
comments: false
permalink: /faq/
---

[Linear Algebra](#linear-algebra)
1. [What are scalars, vectors, matrices, and tensors?](#what-are-scalars-vectors-matrices-and-tensors)
2. What is Hadamard product of two matrices?
3. What is a scalar valued function?
4. What is a vector valued function?
5. What is the gradient?
6. What is a Jacobian matrix?
7. What is a Hessian matrix?
8. What is an identity matrix?

[Numerical Optimization](#numerical-optimization)

[Set Theory](#set-theory)

1. [What is a random experiment?](#what-is-a-random-experiment)
2. [What is a sample space?](#what-is-a-sample-space)
3. [What is an empty set?](#what-is-an-empty-set)
4. [What is an event?](#what-is-an-event)
5. [What are the operations on a set?](#what-are-the-operations-on-a-set)
6. [What is mutually exclusive (disjoint) events?](#what-is-mutually-exclusive-disjoint-events)
7. [What is a non-disjoint event?](#what-is-a-non-disjoint-event)
7. [What is exhaustive events?](#what-is-exhaustive-events)
8. [What is Inclusion-Exlusive Principle?](#what-is-inclusion-exlusive-principle)


[Probability](#probability)

9. [What is a probability?](#what-is-a-probability)
10. [What are the probability axioms?](#what-are-the-probability-axioms)
11. [What is a random variable?](#what-is-a-random-variable)
12. Compare “Frequentist probability” vs. “Bayesian probability”?
13. What is a probability distribution?
14. What is a probability mass function?
15. What is a probability density function?
16. What is a joint probability distribution?
17. What are the conditions for a function to be a probability mass function?
18. What are the conditions for a function to be a probability density function?
19. What is a marginal probability? Given the joint probability function, how will you calculate it?
20. What is conditional probability? Given the joint probability function, how will you calculate it?
21. State the Chain rule of conditional probabilities.
22. What are the conditions for independence and conditional independence of two random variables?
23. [What are expectation, variance and covariance?](#what-are-expectation-variance-and-covariance)
24. What is the covariance for a vector of random variables?
25. [What is a Bernoulli distribution? Calculate the expectation and variance of a random variable that follows Bernoulli distribution?](#what-is-a-bernoulli-distribution-calculate-the-expectation-and-variance-of-a-random-variable-that-follows-bernoulli-distribution)
26. What is a multinoulli distribution?
27. What is a normal distribution?
28. Why is the normal distribution a default choice for a prior over a set of real numbers?
29. What is the central limit theorem?
30. What are exponential and Laplace distribution?
31. What are Dirac distribution and Empirical distribution?
32. What is mixture of distributions?
33. Name two common examples of mixture of distributions? (Empirical and Gaussian Mixture)
34. Is Gaussian mixture model a universal approximator of densities?
35. Write the formulae for logistic and softplus function.
36. Write the formulae for Bayes rule.
37. What do you mean by measure zero and almost everywhere?
38. If two random variables are related in a deterministic way, how are the PDFs related?
39. Define self-information. What are its units?
40. What are Shannon entropy and differential entropy?
41. What is Kullback-Leibler (KL) divergence?
42. [Can KL divergence be used as a distance measure?](#can-kl-divergence-be-used-as-a-distance-measure)
43. Define cross-entropy.
44. What are structured probabilistic models or graphical models?
45. In the context of structured probabilistic models, what are directed and undirected models? How are they represented? What are cliques in undirected structured probabilistic models?
46. What is population mean and sample mean?
47. What is population standard deviation and sample standard deviation?
48. Why population s.d. has N degrees of freedom while sample s.d. has N-1 degrees of freedom? In other words, why 1/N inside root for pop. s.d. and 1/(N-1) inside root for sample s.d.?
49. What is the formula for calculating the s.d. of the sample mean?
50. What is confidence interval?
51. What is standard error?
52. [What is a p-value?](#what-is-a-p-value)

## Linear Algebra

#### What are scalars, vectors, matrices, and tensors?

Scalars are single numbers and are an example of a 0th-order tensor. The notation $x \in \mathbb{R}$ states that the scalar value $x$ is an element of (or member of) the set of real-valued numbers, $\mathbb{R}$.

There are various sets of numbers of interest within machine learning. $\matbb{N}$ represents the set of positive integers $(1,2,3, ...)$. $\matbb{Z}$ represents the integers, which include positive, negative and zero values. $\mathbb{Q}$ represents the set of rational numbers that may be expressed as a fraction of two integers.

Vectors are ordered arrays of single numbers and are an example of 1st-order tensor.  An $n$-dimensional vector itself can be explicitly written using the following notation:

\begin{equation}
\boldsymbol{x}=\begin{bmatrix}
  \kern4pt x_1 \kern4pt \\
  \kern4pt x_2 \kern4pt \\
  \kern4pt \vdots \kern4pt \\
  \kern4pt x_n \kern4pt
\end{bmatrix}
\end{equation}

We can think of vectors as identifying points in space, with each element giving the coordinate along a different axis

One of the primary use cases for vectors is to represent physical quantities that have both a magnitude and a direction. Scalars are only capable of representing magnitudes.

Matrices are rectangular arrays consisting of numbers and are an example of 2nd-order tensors. If $m$ and $n$ are positive integers, that is $m, n \in \mathbb{N}$ then the $m \times n$ matrix contains $mn$ numbers, with $m$ rows and $n$ columns.

If all of the scalars in a matrix are real-valued then a matrix is denoted with uppercase boldface letters, such as $A \in \mathbb{R}^{m \times n}$. That is the matrix lives in a $m \times n$-dimensional real-valued vector space. 

Its components are now identified by two indices $i$ and $j$. $i$ represents the index to the matrix row, while $j$ represents the index to the matrix column. Each component of $A$ is identified by $a_{ij}$.

The full $m \times n$ matrix can be written as:

$$
\boldsymbol{A}=\begin{bmatrix}
   a_{11} & a_{12} & a_{13} & \ldots & a_{1n} \\
   a_{21} & a_{22} & a_{23} & \ldots & a_{2n} \\
   a_{31} & a_{32} & a_{33} & \ldots & a_{3n} \\
   \vdots & \vdots & \vdots & \ddots & \vdots \\
   a_{m1} & a_{m2} & a_{m3} & \ldots & a_{mn} \\
\end{bmatrix}
$$

It is often useful to abbreviate the full matrix component display into the following expression:

\begin{equation}
\boldsymbol{A} = [a_{ij}]_{m \times n}
\end{equation}

Where $a_{ij}$ is referred to as the $(i,j)$-element of the matrix $A$. The subscript of $m \times n$ can be dropped if the dimension of the matrix is clear from the context.

Note that a column vector is a size $m \times 1$ matrix, since it has $m$ rows and $1$ column. Unless otherwise specified all vectors will be considered to be column vectors.

Tensor is n-dimensional array. It encapsulates the scalar, vector and the matrix. For a 3rd-order tensor elements are given by $a_{ijk}$, whereas for a 4th-order tensor elements are given by $a_{ijkl}$.

#### What is Hadamard product of two matrices?
Hadamard product is also known as Element-wise Multiplication. It is named after French Mathematician, Jacques Hadamard. Elements corresponding to same row and columns of given vectors/matrices are multiplied together to form a new vector/matrix.

$$
    \begin{bmatrix} 
3 & 5 & 7 \\
4 & 9 & 8 
\end{bmatrix} \times \begin{bmatrix} 
1 & 6 & 3 \\
0 & 2 & 9 
\end{bmatrix} = \begin{bmatrix} 
3 \times 1 & 5 \times 6 & 7 \times 3 \\
4 \times 0 & 9 \times 2 & 8 \times 9 
\end{bmatrix} = \begin{bmatrix} 
3 & 30 & 21 \\
0 & 18 & 72 
\end{bmatrix}
$$

#### What is a scalar valued function?

A scalar valued function is a function that take one or more values but returns a single value. For example:

$$
f(x, y, z) = x^{2} + 2y z^{5}
$$

A $n$-variable scalar valued function acts as a map from the space $\mathbb{R}^{n}$ to the real number line $\mathbb{R}$. That is: $f:\mathbb{R}^{n} \to \mathbb{R}$

#### What is a vector valued function?

A vector valued function (also known as vector function) is a function where the domain is a subset of real numbers and the range is a vector. For example:

$$
r(t) = <2x+1, x^{2}+3>
$$

presents a function whose input is a scalar $t$ and whose output is a vector in $\mathbb{R}^{2}$

#### What is the gradient?

The gradient of a function $f$, denoted as $\nabla f$ is the collection of all its first-order partial derivatives into a vector. Here, $f$ is a scalar-valued (real-valued) multi-variable function $f:\mathbb{R}^{n}\to \mathbb{R}$.

$$
\nabla f(x_{1}, x_{2}, x_{3}, ...) = \begin{bmatrix} \dfrac{\partial f}{\partial x_{1}} \\[6pt] \dfrac{\partial f}{\partial x_{2}}\\[6pt] \dfrac{\partial f}{\partial x_{3}}\\[6pt] .\\.\\. \end{bmatrix}
$$

In particular, $\nabla f(x_{1}, x_{2}, x_{3}, ...)$ is a vector-valued function, which means it is a vector and we cannot take the gradient of a vector. 

It is very important to remember that the gradient of a function is only defined if the function is real-valued, that is, if it returns a scalar value. 

The most important thing to remember about the gradient is that the gradient of $f$, if evaluated at an input $(x_{0},y_{0})$, points in the direction of the steepest ascent. So, if you walk in that direction of the gradient, you will be going straight up the hill. Similarly, the magnitude of the vector $\nabla f(x_{0},y_{0})$ tells you what the slope of the hill is in that direction, meaning that if you walk in that direction, you will increase the value of $f$ at most rapidly.  

Note that the symbol $\nabla$ is referred to either as nabla or del. 

Note that the gradient of a vector-valued function is the same as obtaining the Jacobian of this function.

#### What is a Jacobian matrix?

Jacobian matrix is a matrix of all first-order partial derivatives of a vector-valued function. Suppose $f:\mathbb{R}^{n} \to \mathbb{R}^{m}$ is a function which takes as input the vector $x \in \mathbb{R}^{n}$ and produces as output the vector $f(x) \in \mathbb{R}^{m}$. Then, the Jacobian matrix J of $f$ is a $m \times n$ matrix:

$$
J = \begin{bmatrix}
\dfrac{\partial f}{\partial x_{1}} & \cdots &\dfrac{\partial f}{\partial x_{n}}
\end{bmatrix} =
\begin{bmatrix}
\dfrac{\partial f_{1}}{\partial x_{1}} &\cdots &\dfrac{\partial f_{1}}{\partial x_{n}} \\[6pt]
& \cdots & \\[6pt]
\dfrac{\partial f_{m}}{\partial x_{1}} &\cdots &\dfrac{\partial f_{m}}{\partial x_{n}} \\[6pt]
\end{bmatrix}
$$

Note that when $m=1$, the Jacobian is the same as gradient because it is a generalization of the gradient.

#### What is a Hessian matrix?

The hessian matrix is a square matrix of the second-order partial derivatives of a scalar-values (real-valued) multi-variable function $f:\mathbb{R}^{n}\to \mathbb{R}$.

If we have a scalar-valued multi-variable function $f(x_{1}, x_{2}, x_{3}, ...)$, its Hessian with respect to x, is the $n \times n$ matrix of partial derivatives:

$$
H_{f} \in \mathbb{R}^{n\times n}= \begin{bmatrix}
\dfrac{\partial^{2}f(x)}{\partial x_{1}^{2}} & \dfrac{\partial^{2}f(x)}{\partial x_{1} \partial x_{2}} & \cdots & \dfrac{\partial^{2}f(x)}{\partial x_{1} \partial x_{n}}\\[7pt]
\dfrac{\partial^{2}f(x)}{\partial x_{2} \partial x_{1}} & \dfrac{\partial^{2}f(x)}{\partial x_{2}^{2}} & \cdots & \dfrac{\partial^{2}f(x)}{\partial x_{2} \partial x_{n}} \\[7pt]
\vdots & \vdots & \cdots & \vdots \\[7pt]
\dfrac{\partial^{2}f(x)}{\partial x_{n} \partial x_{1}} & \dfrac{\partial^{2}f(x)}{\partial x_{n} x_{2}} & \cdots & \dfrac{\partial^{2}f(x)}{\partial x_{n}^{2}}
\end{bmatrix}
$$

Similar to the gradient, the Hessian is defined only when $f(x)$ is real-valued.

Hessian is NOT the gradient of the gradient!

Note that Hessian of a function $f:\mathbb{R}^{n}\to \mathbb{R}$ is the Jacobian of its gradient, i.e., $H(f(x)) = J(\nabla f(x))^{T}$.

#### What is an identity matrix?

identity matrix, $I \in \mathbb{R}^{n \times n}$, is a square matrix with ones on the diagonal and zeros everywhere else.

$$
    I_{ij} = \left\{ \begin{array}{ll}
         1 & \mbox{if $i=j$};\\
        0 & \mbox{if $i \neq j$}.\end{array} \right.
$$

It has the property that for all $A \in \mathbb{R}^{m \times n}$

$$
    AI = IA = A
$$

Generally the dimensions of $I$ are inferred from context so as to make matrix multiplication possible. 








## Numerical Optimization

## Set Theory
![](https://github.com/mmuratarat/mmuratarat.github.io/blob/master/_posts/images/set_theory.gif?raw=true)

#### What is a random experiment?
A random experiment is an experiment or a process for which the outcome cannot be predicted with certainty.

#### What is a sample space?
The sample space (mostly denoted by $S$) of a random experiment is the set of all possible outcomes. $S$ is called the certain event.

Let $A$ be a set. The notation $x \in A$ means that $x$ belongs to $A$. 

#### What is an empty set?
In mathematics, the empty set, mostly denoted by $\emptyset$, is a set with no elements; its size or cardinality (count of elements in a set) is zero. Empty set is called the impossible event. 

Let $A$ be a set. 
* The intersection of any set with the empty set is the empty set, i.e., $A \cap \emptyset = \emptyset$.
* The union of any set with the empty set is the set we started with, i.e., $A \cup \emptyset = A$.
* The complement of the empty set is the universal set (U) for the setting that we are working in, i.e., $\emptyset^C = U - \emptyset = U$. Also, the complement of $U$ is the empty set: $U^{c} =  U - U = \emptyset$.
* The empty set is a subset of any set.

#### What is an event?
An event (mostly denoted by $E$) is a subset of the sample space. We say that $E$ has occured if the observed outcome $x$ is an element of $E$, that is $x \in E$

**Examples**:
* Random experiment: toss a coin, sample sample $S = \{ \text{heads}, \text{tails}\}$
* Random experiment: roll a dice, sample sample $S = \{1,2,3,4,5,6\}$

#### What are the operations on a set?
When working with events, __intersection__ means "and", and __union__ means "or".

$$
P(A \cap B) = P(\text{A and B}) = P(A, B)
$$

$$
P(A \cup B) = P(\text{A or B})
$$

#### What is mutually exclusive (disjoint) events?
The events in the sequence $A_{1}, A_{2}, A_{3}, \ldots$ are said to be mutually exclusive events if $E_{i} \cap E_{j} = \emptyset\text{ for all }i \neq j$ where $\emptyset$ represents the empty set. 

In other words, the events are said to be mutually exclusive if they do not have any outcomes (elements) in common, i.e., they are pairwise disjoint. 

![](https://github.com/mmuratarat/mmuratarat.github.io/blob/master/_posts/images/mutually_exclusive.png?raw=true)

For example, if events $A$ and $B$ are mutually exclusive:

$$
P(A \cup B) = P(A) + P(B)
$$

#### What is a non-disjoint event?
Disjoint Events, by definition, can not happen at the same time. A synonym for this term is mutually exclusive. Non-disjoint events, on the other hand, can happen at the same time. For example, a student can get grade A in Statistics course and A in History course at the same time.

![](https://github.com/mmuratarat/mmuratarat.github.io/blob/master/_posts/images/nondisjoint_events.png?raw=true)

For example, if events $A$ and $B$ are non-disjoint events, the probability of A or B happening (union of these events) is given by:

$$
P(A \cup B) = P(A) + P(B) - P(A \cap B)
$$

#### What is exhaustive events?
When two or more events form the sample space ($S$) collectively than it is known as collectively exhaustive events. The $n$ events $A_{1}, A_{2}, A_{3}, \ldots, A_{n}$ are said to be exhaustive if $A_{1} \cup A_{2} \cup A_{3} \cup \ldots \cup A_{n} = S$. 

#### What is Inclusion-Exlusive Principle?
* For $n=2$ events:

$$
P(A \cup B) = P(A) + P(B) - P(A \cap B)
$$

Let's prove this principle:

$$
\begin{split}
P(A \cup B) &= P(A \cup (B-A))\\
&= P(A) + P(B-A)\\
&= P(A) + P(B) - P(A \cap B)
\end{split}
$$

* For events $A_{1}, A_{2}, A_{3}, \ldots, A_{n}$ in a probability space:

$$
\begin{split}
P\left(\cup_{i=1}^{n} A_{i}\right) =\sum_{i=1}^{n} P(A_{i}) &- \sum_{1 \leq i \leq j \leq n} P(A_{i} \cap A_{j})\\
&+ \sum_{1 \leq i \leq j \leq k \leq n} P(A_{i} \cap A_{j} \cap A_{k}) - \ldots \\
& + \left(-1\right)^{n-1} P\left(\cap_{i=1}^{n} A_{i}\right)
\end{split}
$$

## Probability 

#### What is a probability?
We assign a probability measure $P(A)$ to an event $A$. This is a value between $0$ and $1$ that shows how likely the event is. If $P(A)$ is close to $0$, it is very unlikely that the event $A$ occurs. On the other hand, if $P(A)$ is close to $1$, $A$ is very likely to occur. 

#### What are the probability axioms?

* **Axiom 1** For any event $A$, $P(A) \geq 0$
* **Axiom 2** Probability of the sample space is $P(S)=1$ 
* **Axiom 3** If $A_{1}, A_{2}, A_{3}, \ldots$ are disjoint (mutually exclusive) (even countably infinite) events, meaning that they have an empty intersection, the probability of the union of the events is the same as the sum of the probabilities: $P(A_{1} \cup A_{2} \cup A_{3} \cup \ldots) = P(A_{1}) + P(A_{2}) + P(A_{3}) + \dots$.

#### What is a random variable?
A random variable is a variable whose values depend on all the possible outcomes of a natural phenomenon. There are two types of random variables, discrete and continuous. 

A discrete random variable is one which may take on only a countable number of distinct values such as 0,1,2,3,4,... Discrete random variables are usually (but not necessarily) counts. If a random variable can take only a finite number of distinct values, then it must be discrete. Examples of discrete random variables include the number of children in a family, the Friday night attendance at a cinema, the number of patients in a doctor's surgery, the number of defective light bulbs in a box of ten.

A continuous random variable is one which takes an infinite number of possible values. Continuous random variables are usually measurements. Examples include height, weight, the amount of sugar in an orange, the time required to run a mile.

#### What are expectation, variance and covariance?
In probability, the average value of some random variable X is called the **expected value** or the expectation, denoted by $E(x)$.

Suppose $X$ is a discrete random variable that takes values $x_{1}, x_{2}, . . . , x_{n}$ with probabilities $p(x_{1}), p(x_{2}), . . . , p(x_{n})$. The expected value of $X$ is defined by:

$$
E(X) = \sum_{j=1}^{n}  x_{j}p(x_{j}) = x_{1}p(x_{1}) + x_{2}p(x_{2})  + . . . + x_{n}p(x_{n}).
$$

Let $X$ be a continuous random variable with range $[a, b]$ and probability density function $f(x)$. The expected value of $X$ is defined by

$$
E(X) = \int_{a}^{b} xf(x) dx.
$$

In probability, the **variance** of some random variable $X$, denoted by $Var(X)$ is a measure of how much values in the distribution vary on average with respect to the mean. Variance is calculated as the average squared difference of each value in the distribution from the expected value. Or the expected squared difference from the expected value.

$$
\begin{split}
Var(X) &= E\left[\left(X - E[X]\right)^{2}\right] \\
&= E\left[X^{2}-2XE(X) + \left(E(X) \right)^{2}\right] \\
&= E(X^{2}) - 2E(X)E(X) + \left(E(X) \right)^{2}\\
&= E(X^{2}) - \left(E(X) \right)^{2}
\end{split}
$$

In probability, **covariance** is the measure of the joint probability for two random variables. It describes how the two variables change (vary) together. It’s similar to variance, but where variance tells you how a single variable varies, covariance tells you how two variables vary together. It is denoted as the function $cov(X, Y)$, where $X$ and $Y$ are the two random variables being considered.

$$
cov(X, Y) = E\left[\left(X - E[X]\right) \left(Y - E[Y]\right)\right] =  E(XY)- E(X)E(Y)
$$

Note that $Var(X) = cov(X, X) = E\left[(X - E[X])^{2}\right]$. 

The sign of the covariance can be interpreted as whether the two variables increase together (positive) or decrease together (negative). The magnitude of the covariance is not easily interpreted. A covariance value of zero indicates that both variables are completely independent.

The covariance can be normalized to a score between $-1$ and $1$ to make the magnitude interpretable by dividing it by the standard deviation of X and Y. The result is called the correlation of the variables, also called the _Pearson correlation coefficient_, named for the developer of the method, Karl Pearson.

$$
corr(X, Y) = \rho_{X, Y}= \frac{cov(X,Y)}{\sigma_{X}\sigma_{y}}
$$

The covariance is especially useful when looking at the variance of the sum of two random variates, since

$$
Var(X+Y) = Var(X)+ Var(Y) + 2cov(X,Y)
$$

The covariance is symmetric by definition since

$$
cov(X,Y)=cov(Y,X). 
$$

#### What is a Bernoulli distribution? Calculate the expectation and variance of a random variable that follows Bernoulli distribution?
Suppose you perform an experiment with two possible outcomes: either success or failure. Success happens with probability $p$ while failure happens with probability $1-p$. A random variable that takes value $1$ in case of success and $0$ in case of failure is called a Bernoulli random variable.

$X$ has Bernoulli distribution with parameter $p$, the shorthand $X \sim Bernoulli(p), 0 \leq p \leq 1$, its probability mass function is given by:

$$
P_{X}(x) = \left\{ \begin{array}{ll}
         p & \mbox{if $x = 1 $};\\
        1-p & \mbox{if $x  = 0 $}.\end{array} \right.
$$

This can also be expressed as:

$$
P_{X}(x) = p^{x} (1-p)^{1-x},\,\,\, x \in \{0, 1 \}\,\,\,\text{for}\,\,\, 0 \leq p \leq 1
$$

Bernoulli distribution is a special case of Binomial distribution. If $X_{1},\dots ,X_{n}$ are independent, identically distributed (i.i.d.) random variables, all Bernoulli trials with success probability $p$, then their sum is distributed according to a binomial distribution with parameters $n$ and $p$:

$$
\sum _{k=1}^{n}X_{k}\sim Binomial(n,p)
$$

The Bernoulli distribution is simply $Binomial(1,p)$, also written as $Bernoulli(p)$.

Its expected value is:

$$
E(X) = \sum x p(x) = 1 \times p + 0 \times (1-p) = p
$$

Its variance is:

$$
Var(X) = E(X^{2}) - \left(E(X) \right)^{2} = \sum x^{2} p(x) - p^{2} = 1^{2} \times p + 0^{2} (1-p) - p^{2} = p - p^{2} = p (1-p)
$$

Distribution function of a Bernoulli random variable is:

$$
F_{X}(x) = P(X \leq x) = \left\{ \begin{array}{ll}
         0 & \mbox{if $x < 0 $};\\
        1-p & \mbox{if $0 \leq x < 1 $};\\
        1 & \mbox{if $0 \geq 1 $}.\end{array} \right.
$$

and the fact that $X$ can take either value $0$ or value $1$. If $x<0$, then $P(X \leq x) = 0$ because $X$ can not take values strictly smaller than $0$. If $0 \leq x < 1$, then $P(X \leq x) = 1-p$ because $0$ is the only value strictly smaller than 1 that $X$ can take. Finally, if $x \geq 1$, then $P(X \leq x) = 1$ because all values $X$ can take are smaller than or equal to $1$.

#### Can KL divergence be used as a distance measure?
It may be tempting to think of KL Divergence as a distance metric, however we cannot use KL Divergence to measure the distance between two distributions. The reason for this is that KL Divergence is not symmetric, meaning that $D_{KL}(p\mid \mid q)$ may not be equal to $D_{KL}(q\mid \mid p)$.

#### What is a p-value?
Before we talk about what p-value means, let’s begin by understanding hypothesis testing where p-value is used to determine the statistical significance of our results, which is our ultimate goal. 

When you perform a hypothesis test in statistics, a p-value helps you determine the significance of your results. Hypothesis tests are used to test the validity of a claim that is made about a population using sample data. This claim that’s on trial is called the null hypothesis. The alternative hypothesis is the one you would believe if the null hypothesis is concluded to be untrue. It is the opposite of the null hypothesis; in plain language terms this is usually the hypothesis you set out to investigate. 

In other words, we’ll make a claim (null hypothesis) and use a sample data to check if the claim is valid. If the claim isn’t valid, then we’ll choose our alternative hypothesis instead. Simple as that. These two hypotheses specify two statistical models for the process that produced the data. 

To know if a claim is valid or not, we’ll use a p-value to weigh the strength of the evidence to see if it’s statistically significant. If the evidence supports the alternative hypothesis, then we’ll reject the null hypothesis and accept the alternative hypothesis. 

p-value is a measure of the strength of the evidence provided by our sample against the null hypothesis. In other words, p-value is the probability of getting the observed value of the test statistics, or a value with even greater evidence against null hypothesis, if the null hypothesis is true. Smaller the p-value, the greater the evidence against the null hypothesis. 

If we are given a significance level, i.e., alpha, then we reject null hypothesis if p-value is less than equal the chosen significance level, i.e., accept that your sample gives reasonable evidence to support the alternative hypothesis. The term significance level (alpha) is used to refer to a pre-chosen probability and the term "p-value" is used to indicate a probability that you calculate after a given study. The choice of significance level at which you reject null hypothesis is arbitrary. Conventionally the $5\%$ (less than $1$ in $20$ chance of being wrong), $1\%$ and $0.1\%$ ($p < 0.05, 0.01\text{ and }0.001$) levels have been used. Most authors refer to statistically significant as $p < 0.05$ and statistically highly significant as $p < 0.001$ (less than one in a thousand chance of being wrong).

A fixed level alpha test can be calculated without first calculating a p-value. This is done by comparing the test statistic with a critical value of the null distribution corresponding to the level alpha. This is usually the easiest approach when doing hand calculations and using statistical tables, which provide percentiles for a relatively small set of probabilities. Most statistical software produces p-values which can be compared directly with alpha. There is no need to repeat the calculation by hand.

__Type I error__ is the false rejection of the null hypothesis and __type II error__ is the false acceptance of the null hypothesis. The significance level (alpha) is the probability of type I error. The power of a test is one minus the probability of type II error (beta). Power should be maximized when selecting statistical methods. 

The chances of committing these two types of errors are inversely proportional—that is, decreasing Type I error rate increases Type II error rate, and vice versa. To decrease your chance of committing a Type I error, simply make your alpha value more stringent. To reduce your chance of committing a Type II error, increase your analyses’ power by either increasing your sample size or relaxing your alpha level!