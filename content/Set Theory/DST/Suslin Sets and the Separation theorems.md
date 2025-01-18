---
title: Suslin Sets and the Separation theorems
draft: false
tags: 
date:
---
A set $P\subseteq X$ is *$\kappa$-Suslin* if there is closed $C\subseteq X\times \kappa^\omega$ s.t. $P$ is the projection of $C$ along $X$. i.e. $$x\in P \text{ iff }\exists f\in \kappa^\omega, (x,f)\in C$$
Hence the $\boldsymbol{\Sigma}^1_1$ sets are the $\omega$-Suslin sets. We start with two representations of Suslin sets.

A $\kappa$-Suslin system is a map $\kappa^{<\omega}\to \mathcal{P}(X)$, $u\mapsto P_u$, and given a $\kappa$-Suslin system, $$\mathcal{A}^x_u P_u = \bigcup_{f\in \kappa^\omega}\bigcap_n P_{f|_n}$$
A $\kappa$-Suslin system is regular if:
1. Each $P_u$ is the closure of some basic neighbourhood or empty.
2. If $u$ is an initial segment of the sequence $v$, then $P_u\supseteq P_v$.
3. $radius(P_u)\leq \frac{1}{2^{len(u)-1}}$.

A *norm* on a pointset $P$ is a function $\varphi:P\to Ordinals$ which assigns an ordinal number $\varphi(x)$ to every $x\in P$. A *$\lambda$-norm* is a norm that is bounded by $\lambda$.

A *semi-scale* is a sequence of norms $\varphi_n$ s.t. if $x_0,x_1\dots$ are in $P$ and $x$ is their limit, and if for each $n$ $\varphi_n(x_0),\varphi_n(x_1)\dots$ is ultimately constant, then $x\in P$. A *$\lambda$-semi-scale* is a semi-scale that consists of $\lambda$-norms.

**2B.1 The following are equivalent:**
1. $P$ is $\kappa$-Suslin.
2. $P$ has a $\kappa$-semiscale.
3. $P = \mathcal{A}^\kappa_u P_u$ where the $\kappa$ Suslin system is regular.
4. $P = \mathcal{A}^\kappa_u P_u$ where the $\kappa$ Suslin system consists of closed sets.

Proof. (1) to (2) (AC). Consider the norm $\varphi_n(x) = f_x(n)$ where $f_x$ is chosen s.t. $$x\in P \text{ iff }\exists f_x\in \kappa^\omega, (x,f_x)\in C$$
(2) to (3) Fix an enumeration of the basic opens. Fix a bijection $\kappa\to \omega\times \kappa$ s.t. $\pi(\xi) = (\pi_1(\xi),\pi_2(\xi))$. Let $P_{\xi_0\dots \xi_{n-1}}$ be $\overline{U_{\pi_1(\xi_{n-1})}}$ if 
1. $\overline{U_{\pi_1(\xi_{0})}} \supseteq \overline{U_{\pi_1(\xi_{1})}}\supseteq\dots \supseteq\overline{U_{\pi_1(\xi_{n-1})}}$.
2. $radius(\overline{U_{\pi_1(\xi_{i})}}) \leq \frac{1}{2^i}$.
3. there is $y\in \overline{U_{\pi_1(\xi_{n-1})}}\cap P$ s.t. $\varphi_i(y) =\pi_2(\xi_i)$.
Then the system is clearly regular. To show $P = \mathcal{A}^x_u P_u$, $\subseteq$ is easy. Conversely, if there is $f$ s.t. $x\in P_{f|_n}$ for all $n$, consider the $y_n$ s.t. $\varphi_i(y_n) =\pi_2(f(i))$. $x$ is the limit of $y$ and $\varphi_n(y_i)$ is eventually constant. Hence $x\in P$ by the property of a semi-scale.

(3) to (4) is trivial.

(4) to (1), if $P = \bigcup_{f\in \kappa^\omega}\bigcap_n P_{f|_n}$ where $\bigcap_nP_{f|_n}$ is closed, then $P$ is the projection of the closes set $\bigcap_n P_{f|_n}$.$\Box$

----

**2B.2 $\kappa$-Suslin sets are closed under countable intersection, $\kappa$ disjunction and $\mathcal{A}^\kappa$.**

**Continuous image of Analytic sets**