---
title: Suslin Sets
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

For a more deeper study of norms and scales, refer to [[Pointsets in Constructible Universe]].

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

The following equivalence may motivate the definition behind Suslin operation:

**Lemma $A$ is analytic iff it is the image of $\mathcal{N}$ under a continuous image.**

Proof. Let $f: \mathcal{N}\to X$ be a continous function, consider the Suslin system $P_u = \overline{f(N_u)}$. Further notice that $$\{f(a)\} = \bigcap_n f(N_{a|_n}) = \bigcap_n\overline{f(N_{a|_n})}$$
This is true as suppose for contradiction $f(c)\in \bigcap_n\overline{f(N_u)}$ while $c\neq a$, then pick $U,V$ s.t. $a\in U$ and $c\in V$. Pick $a\in N_u\subseteq f^{-1}(U)$ and hence $f(N_u)\subseteq U$ and is disjoint from $V$, a contradiction to $c\in f(N_u)$. 

This shows $f[\mathcal{N}] = \bigcup_{a\in \mathcal{N}}\bigcap_n\overline{f(N_{a|_n})} = \mathcal{N}^\omega P_u$.

On the other hand, if $A$ is analytic, we consider a regular Suslin system $P_u$. Let the map be defined as $\pi: a\in \mathcal{N}\mapsto \bigcap_nP_{a|_n}\in X$. We abuse notation here since $\bigcap_nP_{a|_n}$ is a singleton. The map exists by completeness of $X$. 

Now we check that it is continuous, for arbitrary open $U\subseteq X$, $a\in \pi^{-1}[U]$ iff $\pi(a)\in U$ iff $\bigcap_nP_{a|_n}\in U$.

This is equivalent to exists some $N$, $\bigcap_{n<N}P_{a|_n}\subseteq U$. This is because let $U_{\frac{1}{2^n}}\subseteq U$ be a ball around $\pi(a)$ with radius $\frac{1}{2^n}$, then the $P_{a|_n}$ must be contained in $U_{\frac{1}{2^n}}\subseteq U$.

This is equivalent to there exists $N$, $\alpha\in N_{\alpha|_N}\subseteq \pi^{-1}[P_{\alpha|_N}]\subseteq \pi^{-1}[U]$. Hence $\pi^{-1}[U]$ is open. $\Box$

----

**2B.2 $\kappa$-Suslin sets are closed under countable intersection, $\kappa$ disjunction and $\mathcal{A}^\kappa$.**

**Continuous image of Analytic sets**

----

### Separation theorem
A set is $\kappa$ Borel if it is contained in the smallest $\kappa$ algebra containing open sets and closed sets (an algebra that is closed under $<\kappa$ intersection and complements).

**2E.1 (Strong Separation Theorem)
Let $A,B$ be disjoint $\kappa$-Suslin sets, then there is a $\kappa+1$ Borel set $X$ that separates them. i.e. there is $\kappa+1$ Borel set $C$ s.t. $A\subseteq C$ and $C\cap B = \emptyset$.**

Proof.
First notice that if $A = \bigcup_{i\in I}A_i$ and $B = \bigcup_{j\in J}B_j$, and $C_{i,j}$ separates $A_i$ and $B_j$, then $C = \bigcup_{i}\bigcap_jC_{i,j}$ separates $A,B$.

 The proof by contradiction: Suppose for contradiction that there is no set separating $A,B$. Decompose $A = p[T] = \bigcup_{n\in \omega,\alpha<\kappa}p[T_{(n,\alpha)}]$ and $A = p[S] = \bigcup_{m\in \omega,\beta<\kappa}p[S_{(m,\beta)}]$. Here $T_{(n,\alpha)}$ is the 'generated subtree' from $(n,\alpha)$. Then there is $T_{(n_0,\alpha_0)},S_{(m_0,\beta_0)}$ that is not separated, hence $n_0 = m_0$ since otherwise they are separated by $\{a\mid a(0) = n_0\}$. 

Recursively working in this way, we can find $(n_0,\alpha_0,\dots)$ and $(n_0,\beta_0,\dots)$ as branches of $T,S$ separately and this is a contradiction to assumed disjointness.

The proof by construction:

For a sequence $u = (n_0,\alpha_0,\beta_0,n_1,\alpha_1,\beta_1,\dots)$ from $\omega\times \kappa\times \kappa$ we let $\tau(u) = (n_0,\alpha_0,n_1,\alpha_1,\dots)$ and $\sigma(u) = (n_0,\beta_0,n_1,\beta_1,\dots)$.

Define a new tree $J$ on $\omega\times\kappa\times \kappa$ s.t. $u\in J$ iff $\tau(u)\in T$ and $\sigma(u)\in S$. Notice $J$ is well founded (see the definition here [[Well Founded Tree, Coanalytic Sets and Sigma 1 2 Sets]]) since $A$ and $B$ is disjoint. We then induct on this well founded tree to construt $C_{u}$ s.t. 

1) $C_u$ separates $p[T_{\tau(u)}]$ and $p[S_{\sigma(u)}]$.

2) $C_u$ is $\kappa +1$ Borel.

For $p[T_{\tau(u)}] = \bigcup_{n\in \omega,\alpha<\kappa}p[T_{\tau(u)\smallfrown(n,\alpha)}]$ and $p[S_{\tau(u)}] = \bigcup_{m\in \omega,\beta<\kappa}p[S_{\tau(u)\smallfrown(m,\beta)}]$, it suffice to find a separating set for each $p[T_{\tau(u)\smallfrown(n,\alpha)}]$ and $p[S_{\tau(u)\smallfrown(m,\beta)}]$. 

If $n = m$ and $u\smallfrown (n,\alpha,\beta)\in J$ then by IH we are done.

If $n = m$ but $u\smallfrown (n,\alpha,\beta)\not\in J$, then either $(n,\alpha)\not\in T$ or $(n,\beta)\not\in S$, hence $\emptyset$ or $\omega^\omega$ separates the two.

If $n\neq m$ then $\{a\mid a(l(u)) = n\}$ separated the two.

Consequently, $C_\emptyset$ separates the two.$\Box$

Hence, $\boldsymbol{\Sigma}^1_1\cap \boldsymbol{\Pi}^1_1 = \boldsymbol{\Delta}^1_1$ is the Borel sets.

For another interesting proof separation theorem based on analysis of well-founded trees, see [[Well Founded Tree, Coanalytic Sets and Sigma 1 2 Sets]].

----
### Borel functions have Borel Graphs

It follows that for $f:X\to Y$, if the graph of $f\subseteq X\times Y$ is $\boldsymbol{\Sigma}^1_1$, then $f$ is Borel. As for open $U\subseteq Y$,

$x\in f^{-1}(U) \text{ iff }\exists^{\mathcal{N}}y, (x,y)\in f\land y\in p^{-1}(U) \text{ iff }\forall^{\mathcal{N}}y, ((x,y)\in f\to y\in p^{-1}(U))$.

Here $p$ is some continuous projection from Baire space to $Y$. The first characterisation is $\boldsymbol{\Sigma}^1_1$ and the second is $\boldsymbol{\Pi}^1_1$. Hence the function is Borel.

The following is a characterisation of Borel functions, in the sense of its hierarchy in the product space:

**Theorem For Polish spaces $X,Y$ and $f:X\to Y$, $f$ is a Borel function iff $f\subseteq X\times Y$ is Borel in $X\times Y$ iff $f$ is analytic in $X\times Y$.**

Proof. If $f\subseteq X\times Y$ is a graph of a function and is analytic, notice $$(x,y)\in f\text{ iff }\forall y'((x,y)\in f \to y' = y)$$
Hence it is also a $\boldsymbol{\Pi}^1_1$ pointset, thus it is Borel.

If $f$ is a Borel function, let $U_k$ be a countable base of $Y$, then notice $$(x,y)\not\in f \text{ iff }\exists k, x\in f^{-1}(U_k), y\not\in U_k$$
$X\times Y - f$ is a Borel set, hence $f$ is a Borel set. We omit the proof of other directions.$\Box$