---
title: Convolution and the Sum of Random Variables
draft: false
tags:
  - "#Course/Sem/Measure_Theoretic_Probability"
  - "#Measure_Theory"
  - "#Probability_Theory"
date:
---
It turns out that from the probability perspective, convolution of two functions can be seen as the probability of the sum of the two functions, understood as random variables.

For two independent variables $X$ and $Y$, with distribution $\mu$ and $\nu$, $$
P(X+Y \in H) = \int \nu(H - x)\,d\mu = \mu*\nu(H)
$$
Note that only when two variables are independent are their product well-defined. This is because $\mu\times\nu(A\times B) = \mu\times\nu(X\in A\land Y\in B) = \mu(A)\nu(B)$. 

If the distribution function $F,G$ of $X,Y$ each has density $f,g$, we can compute that the distribution of $X+Y$  is given by the following, if $H = (-\infty, y)$, $$(F * G)(y) = \int G(y - x)\, dF(x)
$$

By Fubini's Theorem,  $F*G$ has density $$
f*g(y) = \int g(y- x)f(x)\,dx
$$

-----

An example is the exponential distribution. For $X_{1},\dots X_{n}$ following $\alpha e^{-\alpha x}$ for $x\geq 0$, let $$
g_{k}(x) = \alpha \frac{(\alpha x)^{k-1}}{(k - 1)!}e^{-\alpha x}
$$

An inductive argument shows that $X_{1}+\dots+X_{n}$ follows $g_{k}(x)$.


## Reference