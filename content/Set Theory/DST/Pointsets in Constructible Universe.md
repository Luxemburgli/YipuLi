---
title: Pointsets in the Constructible Universe
draft: false
tags: 
date:
---
### A $\boldsymbol{\Delta}^1_2$ set that is not Lebesgue Measurable and does not have Baire Property in $L$
The property of being constructible, and the canonical well order of $L$, $<_L$ is $\Sigma_1$ in the Levy hierarchy. Moreover, since all the reals are in $HC,\in$, the hereditarily countable sets, working from $HC$ the property of being a constructible real, and their well-order is $\Sigma_1$. Hence by theorem 25.25 in [[Code of WO and WF, and the Study of Sigma 1 2 sets under Recursion Theory]], $\mathcal{N}\cap L$ and $<_L|_\mathcal{N}$ is $\boldsymbol{\Sigma}^1_2$. We will henceforth omit the restriction of the well order and by $<_L$ we just mean the canonical well order in $L$ of $\mathcal{N}$.

In $L$, we know that $<_L$ is also $\Pi^1_2$ as $x<_L y$ iff not $x>_Ly$ for distinct $x,y$. Hence $<_L$ is $\Delta^1_2$ in $L$.

Things easily relativize: If $a\in \mathcal{N}$ then $\mathcal{N}\cap L[a]$ is $\Sigma^1_2(a)$.

Recall the following fact:

**Exercise 13.21 In $L$, the order type of $<_L$ restricted on $\mathcal{N}^L$ is $\omega_1$**

**Theorem 25.28 In $L$ there is a $\Sigma^1_2$ set that is not Lebesgue Measurable nor Baire.**

Proof. Consider the set $\{(x,y)\mid x<_Ly\}$. By [[Kunen Martin Theorem]], the length of $<_L$ is at most $\omega_1$, and hence Its slice over $y$, $\{x\mid x<_Ly\}$ is countable, thus meager and null. By the two theorems in [[Measure and Category Ch.14, 15 Fubini's Theorem and Kuratowski-Ulam Theorem]], this shows that $A = \{(x,y)\mid x<_Ly\}$, if measurable must be null and if having property of Baire must be meager.

Similarly, for $\mathcal{N}^2-A$ we have  $\{y\mid x\geq_Ly\}$ is countable and hence $\mathcal{N}^2-A$ if measurable must be null and if having property of Baire must be meager. Hence $A$ is neither Lebesgue Measurable nor Baire. $\Box$

-----

### A $\Sigma^1_2$ that does not have the perfect set property in $L$.

For this we need the boundedness lemma, recall from [[Code of WO and WF, and the Study of Sigma 1 2 sets under Recursion Theory]] that $WO$ is a $\Pi^1_1$ set and is not $\boldsymbol{\Sigma^1_1}$.

Let $\rho(x)$ be the order type of the order $x$ codes if $x\in WO$, notice $\rho(x)\leq\rho(y)$ is a $\Sigma^1_1$ as $$\rho(x)\leq\rho(y) \iff \exists f\in \mathcal{N}, \forall m,n\in \mathbb{N} (mE_xn\to f(m)E_yf(n))$$

**Corollary 25.14(Boundedness Lemma) If $B\subseteq WO$ is a $\boldsymbol{\Sigma}^1_1$, then the order type of elements in $B$ is bounded by some $\alpha<\omega_1$**
Proof. Assume for contradiction that this not the case. 
Then $$x\in WO \iff \exists z\in B, \exists f\in \mathcal{N}, \forall m,n\in \mathbb{N} (mE_xn\to f(m)E_zf(n))$$
This is a $\boldsymbol{\Sigma}^1_1$ relation, a contradiction. $\Box$

For $z\in \mathcal{N}$, let $z_n(m) = z(\Gamma(n,m))$, here $\Gamma$ is the canonical bijection $\omega^2\to \omega$.

The following says that the relation $R$ that corresponds a real $x$ to the real that codes all elements under $x$ by $<_L$ is $\Sigma^1_2$.

**Lemma 25.27 The following relation $R$ is $\Sigma^1_2$. $$(z,x)\in R\iff \{z_n\mid n\in \mathbb{N}\} = \{y\mid y<_L x\}$$**
Proof. The $\subseteq$ side is actually $\Sigma_1$ over $HC,\in$, hence a $\Sigma^1_2$ property.

$\{z_n\mid n\in \mathbb{N}\} \supseteq \{y\mid y<_L x\}$ iff there exists $L_\alpha$ with $\alpha$ countable that contains $x,z,z_n$ and $L_\alpha\models \forall y<_Lx\exists n(y = z_n)$.

Since definability is a $\Delta_1$ property thus absolute for transitive models of ZF, there is a finite fragment $\Theta$ of ZF s.t. if $M\models \Theta$, definability is absolute for $M$. Thus the above is equivalent to there exists ctm $M$ that contains $x,z,z_n$ and $M\models \Theta\land \forall y<_Lx\exists n(y = z_n)$.

By an argument similar to theorem 25.25 in [[Code of WO and WF, and the Study of Sigma 1 2 sets under Recursion Theory]], this is $\Sigma^1_2$ property. $\Box$

**Corollary 25.29 In $L$ there is a $\Sigma^1_2$ set without perfect set property.**

<font color = "red">Note: </font> Can't this result be strengthened to $\Delta^1_2$ set? Or is there a bug in my reasoning?

Proof. Let $$A(x) \iff x\in WO\land \forall y<_Lx(\neg \rho(y) = \rho(x))$$
Notice this is a $\Pi^1_2$ set as 
$$A(x)\iff x\in WO\land \forall y,( y<_Lx\to (\neg \rho(y) \leq \rho(x)\land\neg \rho(x) \leq \rho(y) ))$$

Also, $$A(x) \iff x\in WO \land \exists z(R(z,x)\land \forall n(\neg \rho(z_n) = \rho(x)))$$
Which is $\Sigma^1_2$ by the previous Lemma.

This is an uncountable set as $\rho(x),x\in A$ is cofinal in $\rho(<_L) = \omega_1$.

Finally, to show that $A$ does not have a perfect set, indeed it cannot contain a uncountable analytic set, let alone a perfect set. That's because any uncountable subset of $A$ would have rank function $\rho(x),x\in A$ be unbounded in $\omega$, and thus can't be analytic by the boundedness lemma. $\Box$

----

### A $\Pi^1_1$ that does not have the perfect set property in $L$.

To do prove this we have to develop the theory of norms and scales and prove a uniformization theorem for $\Pi^1_1$ sets.

Recall the definitions: 

A *norm* on a pointset $P$ is a function $\varphi:P\to Ordinals$ which assigns an ordinal number $\varphi(x)$ to every $x\in P$. A *$\lambda$-norm* is a norm that is bounded by $\lambda$.

There is a correspondence of norms with *pre-well-orderings* of a pointset. A pre-wellordering is a preorder such that $a\leq b$ or $b\leq a$ for all $a,b$ and $<$ is well-founded. The rank function of a pre-well-order is a norm and a norm induces a pre-well-order. The correspondence is not one-to-one, though.

A *semi-scale* is a sequence of norms $\varphi_n$ s.t. if $x_0,x_1\dots$ are in $P$ and $x$ is their limit, and if for each $n$ $\varphi_n(x_0),\varphi_n(x_1)\dots$ is ultimately constant, then $x\in P$. A *$\lambda$-semi-scale* is a semi-scale that consists of $\lambda$-norms.

The analysis of $\Pi^1_1$ relation as well-founded trees in section [[Well Founded Tree, Coanalytic Sets and Sigma 1 2 Sets]] gives us the following property: 

**Theorem 25.32 For every $\Pi^1_1$ set $A$ there is a norm $\varphi$ s.t. there is a $\Pi^1_1$ property $P\subseteq A^2$ as well as a $\Sigma^1_1$ property $Q\subseteq A^2$ s.t. $$\varphi(x)\leq\varphi(y)\iff P(x,y)\iff Q(x,y)$$**
Proof. Let $T$ be a tree of $\omega^2$ s.t. $\alpha\in A\iff T(\alpha) \text{ is well-founded.}$

Let $\varphi(\alpha)$ be defined as $\rho(T(\alpha))$.

Then $\varphi(\alpha)\leq \varphi(\beta)$ iff there is $f$ that is order preserving from $T(\alpha)$ to $T(\beta)$, which is a $\Sigma^1_1$ property. 

$\varphi(\alpha)\leq \varphi(\beta)$ iff for all $s\in \omega^{<\omega}$ s.t. $s\neq \emptyset$, there is no order preserving $f:T(\beta)\to T(\alpha)_s$. Remember $T(\alpha)_s$ is the subtree growing under $s$. The property says that it is not the case $\rho(T(x))> \rho(T(y))$. $\Box$

It is not hard to see that the argument generalizes 

**Corollary For every set $A$ that is a complement of $\kappa$-Suslin set, there is a norm $\varphi$ s.t. there is a $\kappa$-Suslin property $P\subseteq A^2$ as well as a co-$\kappa$-Suslin property $Q\subseteq A^2$ s.t. $$\varphi(x)\leq\varphi(y)\iff P(x,y)\iff Q(x,y)$$**


A *scale* on $A$ is a sequence of norms $\varphi_n$ s.t. if $x_0,x_1\dots$ are in $P$ and $x$ is their limit, and if for each $n$ $\varphi_n(x_0),\varphi_n(x_1)\dots$ is ultimately constant with value $\alpha_n$, then $x\in P$ and $\varphi_n(x)\leq \alpha_n$ for all $n$.

The following considerations motivates the definition. 

For a $\Pi^1_1$ set $A$ s.t. $x\in A$ iff $U(x)$ is well founded, $U$ is a tree on $\omega^2$. Recall by Shoenfield theorem in [[Well Founded Tree, Coanalytic Sets and Sigma 1 2 Sets]], for the tree $T$ on $\omega\times \omega_1$ where: 
$$T(s,h) \iff h^*|T_{s} \text{ is order preserving}$$
Here $h^*$ is the lifting $h(u_n) = h^*(n)$, $u_n$ is an enumeration of $\omega^{\omega}$ and $T_{s}$ stands for $\{s'\in \omega^{<\omega}\mid U(s',s|_{len(s')})\}$.

The observation is that not only $x\in A\iff x\in p[T]\iff\text{there is a branch in }T(x)$, but also $x\in A$ iff there is a least branch $g$ in $T(x)$, least in the sense that $g(n)\leq f(n)$ for any $n\in \mathbb{N}$ for any $f\in T(x)$, as the rank function is always the minimal order preserving function.

$g_x(n) = \rho(T(x), u_n)$.

Let the scale $\varphi_n(x)$ be given by $g_x(n)$. If $x_0,x_1\dots$ are a sequence of elements with limit $x$,  and $\varphi_n(x_i)$ are constant at $\alpha_n$. Let $\tilde{\varphi}(n,x_i) = \varphi_n(x_i)$ Then $(x,(\alpha_0,\alpha_1\dots))$ is the limit of $(x_0,\tilde{\varphi}(-,x_i)),\dots$, and as $[T]$ is closed, $(x,(\alpha_0,\alpha_1\dots))$ is in $[T]$ and hence $x\in p[T]$. For any $n$, $g_x(n)\leq \alpha_n$.

The following is the uniformization property for $\Sigma^1_2$ sets.

**Theorem 25.36 (Kondo)For every $\Pi^1_1$ pointset $A$ of $\mathcal{N}^2$, there is a $\Pi^1_1$ function $F:\{y\mid \exists x(x,y)\in A\}\to \mathcal{N}$ s.t. $F\subseteq A$**

Proof. Let $A\subseteq \mathcal{N}^2$ be $\Pi^1_1$, and let $\varphi_n(x)$ be the scale defined above on $A$. Consider the following recursively defined sets:

$$A_{2n+1} = \{(x,y)\in A_{2n}\mid \varphi_n(x) = min\{\varphi_n(x)\mid (x,y)\in A_{2n}\}\}$$
$$A_{2n+2} = \{(x,y)\in A_{2n+1}\mid x(n) = min\{x(n)\mid (x,y)\in A_{2n}\}\}$$

This is a decreasing sequence, and the intersection has at most one element by construction of $A_{2n+2}$. However, for each $y$ s.t. $\exists x(x,y)\in A$,  picking one element $(x_n,y)$ form each $A_{2n+2}$, this is a limiting sequence and $\varphi_n(x_i,y)$ is eventually constant, hence their limit $x,y\in A$. $\bigcap_n A_n$ is a function. Moreover, it is $\Pi^1_1$. $\Box$

**Theorem 25.37 If $V = L$ then there is a $\Pi^1_1$ set without the perfect set property**

Proof. Let $A$ be a $\Sigma^1_2$ uncountable set without a perfect subset. Let $A$ be the projection of $B\subseteq \mathcal{N}^2$ that is $\Pi^1_1$. By uniformization, there is $\Pi^1_1$ $f$ uniformizing $A$. $f$ is uncountable as its projection is still $A$. Suppose for contradiction that $f$ contains a perfect set $P$, then the projection of $P$ would be a uncountable analytic set in $A$, this is a contradiction to boundedness lemma. $\Box$

**Theorem 25.38 The following are equivalent:**
1. For each $a\subseteq \omega$, $\aleph_1^{L[a]}$ is countable
2. Every $\boldsymbol{\Sigma^1_2}$ set has perfect set property
3. Every $\boldsymbol{\Pi^1_1}$ set has perfect set property

Proof. 1 to 2 is  a corollary of Mansfield-Solovay theorem here [[Code of WO and WF, and the Study of Sigma 1 2 sets under Recursion Theory]]. 3 to 1 proceeds as corollary 25.29 and theorem 25.37, observing that $$x\in A\iff x\in L[a]\land x\in WO\land \forall y<_{L[a]}x(\neg \rho(y) = \rho(x))$$
gives an uncountable $\Sigma^1_2$ set $A$. $\Box$

----
### Well-ordering Property, Reduction Property and Separation
