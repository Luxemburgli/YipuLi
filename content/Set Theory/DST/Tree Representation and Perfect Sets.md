---
title: Tree Representation and Perfect Sets
draft: false
tags: 
date:
---
### Perfect Set

For  a tree $T\subseteq \omega^{<\omega}\times \kappa^{<\omega}$, the body of a tree $[T]$ consists of all the infinite branches of $T$. $[T] = \{f\in \omega^{\omega}\times \kappa^{\omega}\mid f|_n\in T\}$.

**2C.1 A set $C\subseteq \omega^{\omega}\times \kappa^{\omega}$ is closed iff it is $[T]$ for some tree $T$.
A set $P\subseteq \omega^\omega$ is $\kappa$-Suslin iff there is a tree $T$ on $\omega\times \kappa$ s.t. $P$ is the projection of $[T]$.**

Let $T_u = \{v\in T\mid v\text{ extends }u\}$. Hence $[T_u] = \bigcup_{n\in \omega,\xi\in \kappa}[T_{u\frown (n,\xi)}]$, $p[T_u] = \bigcup_{n\in \omega,\xi\in \kappa}p[T_{u\frown (n,\xi)}]$.

**2C.2 (The Perfect Set Theorem) In the Baire space, if P is $\kappa$-Suslin and has more than $\kappa$ elements, then $P$ has a non-empty perfect subset.**

Proof. Let $P = p[T]$. Consider the transfinite pruning of the tree:
$$T^0 = T$$
$$T^{\xi+1} =\{u\in T^\xi\mid p[T^\xi_u] \text{ is not a singleton or empty}\}$$
$$T^{\lambda} =\bigcap_{\xi<\lambda}T^\xi$$
Since $T$ is at most of size $\kappa$, the pruning process becomes constant after some $\xi<\kappa^+$. Let $T^* = T^\lambda$.

We show that $T^*$ is not empty. If $\alpha\in p[T]- p[T^*]$, let $(\alpha,f)\in [T]$, then $(\alpha,f)\in [T^\xi] - [T^{\xi+}]$ for some $\xi$. This means that for some $(\alpha|_n,f|_n)$, $p[T^\xi_{(\alpha|_n,f|_n)}]$ is a singleton $\{\alpha\}$.

This shows that $p[T]- p[T^*]\subseteq \bigcup\{p[T^\xi_u]\mid \xi\leq \kappa,u\in T^\xi-T^{\xi+1}\}$. Given $p[T]$ is of cardinality greater than $\kappa$, $p[T^*]$ is non-empty.

Now we show that $p[T^*]$ is a perfect set. For each $\alpha\in p[T^*]$, we show that it is not an isolated point. If not, there is $U_s$ s.t. $\alpha$ is the only sequence extending $s$. But there is $(\alpha,f)\in [T^*]$, the set $p[T^*_{(s,f|_n)}]$ should contain two elements, otherwise the node would be pruned. Then there is another $\beta\in U_s$. Hence $p[T^*]$ contains not isolated points and is perfect. $\Box$

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

Define a new tree $J$ on $\omega\times\kappa\times \kappa$ s.t. $u\in J$ iff $\tau(u)\in T$ and $\sigma(u)\in S$. Notice $J$ is well founded (see the definition here [[Well Founded Tree and Sigma 1 2 Sets]]) since $A$ and $B$ is disjoint. We then induct on this well founded tree to construt $C_{u}$ s.t. 

1) $C_u$ separates $p[T_{\tau(u)}]$ and $p[S_{\sigma(u)}]$.

2) $C_u$ is $\kappa +1$ Borel.

For $p[T_{\tau(u)}] = \bigcup_{n\in \omega,\alpha<\kappa}p[T_{\tau(u)\smallfrown(n,\alpha)}]$ and $p[S_{\tau(u)}] = \bigcup_{m\in \omega,\beta<\kappa}p[S_{\tau(u)\smallfrown(m,\beta)}]$, it suffice to find a separating set for each $p[T_{\tau(u)\smallfrown(n,\alpha)}]$ and $p[S_{\tau(u)\smallfrown(m,\beta)}]$. 

If $n = m$ and $u\smallfrown (n,\alpha,\beta)\in J$ then by IH we are done.

If $n = m$ but $u\smallfrown (n,\alpha,\beta)\not\in J$, then either $(n,\alpha)\not\in T$ or $(n,\beta)\not\in S$, hence $\emptyset$ or $\omega^\omega$ separates the two.

If $n\neq m$ then $\{a\mid a(l(u)) = n\}$ separated the two.

Consequently, $C_\emptyset$ separates the two.$\Box$

Hence, $\boldsymbol{\Sigma}^1_1\cap \boldsymbol{\Pi}^1_1 = \boldsymbol{\Delta}^1_1$ is the Borel sets.


----
It follows that for $f:X\to Y$, if the graph of $f\subseteq X\times Y$ is $\boldsymbol{\Sigma}^1_1$, then $f$ is Borel. As for open $U\subseteq Y$,

$x\in f^{-1}(U) \text{ iff }\exists^{\mathcal{N}}y, (x,y)\in f\land y\in p^{-1}(U) \text{ iff }\forall^{\mathcal{N}}y, ((x,y)\in f\to y\in p^{-1}(U))$.

Here $p$ is some continuous projection from Baire space to $Y$. The first characterisation is $\boldsymbol{\Sigma}^1_1$ and the second is $\boldsymbol{\Pi}^1_1$. Hence the function is Borel.

The following is a characterisation of Borel functions, in the sense of its hierarchy in the product space:

**Theorem For Polish spaces $X,Y$ and $f:X\to Y$, $f$ is a Borel function iff $f\subseteq X\times Y$ is Borel in $X\times Y$ iff $f$ is analytic in $X\times Y$.**

Proof. If $f\subseteq X\times Y$ is a graph of a function and is analytic, notice $$(x,y)\in f\text{ iff }\forall y'((x,y)\in f \to y' = y)$$
Hence it is also a $\boldsymbol{\Pi}^1_1$ pointset, thus it is Borel.

If $f$ is a Borel function, let $U_k$ be a countable base of $Y$, then notice $$(x,y)\not\in f \text{ iff }\exists k, x\in f^{-1}(U_k), y\not\in U_k$$
$X\times Y - f$ is a Borel set, hence $f$ is a Borel set. We omit the proof of other directions.$\Box$


