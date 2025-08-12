---
title: Borel functions and Isomorphisms
draft: false
tags: 
date:
---
### Surjection from the Baire space and Injection from the Cantor space
In this section we show that for each Polish space $X$, there is a continuous surjection from the Baire space $\mathcal{N}$ onto $X$ and if it is also *Perfect*, there is a continuous injection from the Cantor space $\mathcal{C}$ into $X$.

**1A.1 For each Polish space $X$, there is a continuous surjection $f:\mathcal{N}\to X$.**
Proof. Inductively, we define a map $\omega^{<\omega}\to \mathcal{P}(X)$ s.t.

1. Each finite sequence $s$ is mapped to the closure of a basic ball $\overline{U_s}$.

2. $U_\emptyset = X$ and $U_s= \bigcup_{n\in \omega}U_{s\smallfrown n}$.

3. If $s\subseteq t$, then $center(U_t)\in U_s$.

4. $radius(U_s)<\frac{1}{2^{l(s)}}$ for $s\neq \emptyset$.

Such map can be inductively defined (in particular, condition 2 can be satisfied) as the space $X$ is separable and hence have a countable base. Now for $a\in \mathcal{N}$, define $f(a)$ to be the element in $\bigcap_{s\subseteq a} U_s$. $\bigcap_{s\subseteq a} U_s$ is at most a singleton, it is nonempty as $center(U_s)$ is a cauchy sequence and by completeness it converges to some $c$. And such limit point must be in $\bigcap_{s\subseteq a} U_s$.

$f$ thus defined is surjective by condition 2.$\Box$

**1A.3 For each *Perfect* Polish space $X$, there is a continuous injection $f:\mathcal{C}\to X$, where $\mathcal{C}$ is the Cantor space.**
Proof. The idea of the proof is quite similar to the previous one, consider the map $2^{<\omega}\to \mathcal{P}(X)$ s.t.

1.  Each finite sequence $s$ is mapped to the closure of a basic ball $C_s$.

2. $C_{s\smallfrown 0}\cap  C_{s\smallfrown 1} = \emptyset$.

3. If $s\subseteq t$, then $C_t\subseteq C_s$.

4. $radius(C_s)<\frac{1}{2^{l(s)}}$ for $s\neq \emptyset$.

Perfectness makes sure that there each $C_s$ would not be a singleton and hence condition 2 can be satisfied. Now for $a\in \mathcal{C}$, define $f(a)$ to be the element in $\bigcap_{s\subseteq a} U_s$. Injectivity is guaranteed by condition 2.$\Box$

----
Borel function is a function that reflects basic open sets to Borel sets. $f:X\to Y$  is Borel if for each basic open $U$ in $Y$, $f^{-1}[Y]$ is Borel. A Borel isomorphism is a bijection s.t. both its inverse and itself is Borel.

By checking closure properties, it is easy to show that a Borel function reflects Borel sets and sets in point class $\boldsymbol{\Pi}^1_n,\boldsymbol{\Sigma}^1_n,\boldsymbol{\Delta}^1_n$.

The main theorem is the following, which shows that every Polish space is Borel isomorphism to a subspace of the Baire space.

**1G.2 For every Product space there is continuous surjection $\pi:\mathcal{N}\to X$ and there is a closed subset $A$ of $\mathcal{N}$ s.t. $\pi[A] = X$, $\pi$ is bijective on $A$ and the reverse of $\pi|_A$ is Borel.**

Proof. Let $f$  be constructed as in Theorem 1A.1. Consider the map $g:X\to \mathcal{N}$ by $g(x) = a$ where $a$ is defined inductively as:
$$a(n) = min \{m\mid x\in U_{\langle a(0)\dots a(n-1)\rangle\smallfrown m}\}$$

Then for each $x\in X$, $f\cdot g(x) = x$. Let $g[X] = A$ and $g$ is bijective between $A$ and $X$. Notice for a $g(x) = a, g(y)=b\in \mathcal{N}$, $$a|_n \subseteq b\iff y\in U_{a|_n}\land \forall_{i<n} m_i\leq a(i)(y\not\in U_{\langle m_0,\dots ,m_{n-1}\rangle})$$ Therefore $g^{-1}[U_s]$ is Borel for arbitrary $s\in \omega^{<\omega}$. Hence $g$ is Borel.

Now $a\in A$ iff $\bigwedge_{i}\bigwedge_{m_j\leq a(j),j< i} f(a)\not\in U_{j\mapsto m_j}$. This is a closed set and hence we are done. $\Box$

----
### Luzin's Favorite characterisation of Borel Sets

In this section, building on the results above, we show that a set is Borel iff it is an injective, continuous image of a closed set in the Baire space.

**1G.5 Every Borel set in Polish space $X$ is a continuous, injective image of a closed set in $\mathcal{N}$.**

Proof. Suppose $P$ is closed, then $P$ inheriting the subspace topology is a Polish space and hence by 1G.2 the conclusion holds.

Now we show that the property that $P$ is a continuous, injective image of a closed set in $\mathcal{N}$  is closed under countable union and intersection and we are done.

Say $\pi_n:\mathcal{N}\to P_n$ is continuous and are injective on closed set $B_n\subseteq \mathcal{N}$. As $U_n = \{\alpha\in \mathcal{N}\mid \alpha(0) = n\}$ is homeomorphic to $\mathcal{N}$, we may assume $\pi_n:U_n\to P_n$ and $B_n\subseteq U_n$. 

Closure under countable union: 
Let $B = \{(n)\frown\alpha\mid \alpha\in B_n\}$. Here $(n)\frown\alpha$ just means mapipng $0$ to $n$ and other $i$ to $\alpha(i+1)$. Then the map $\pi((n)\frown\alpha) = \pi_n(\alpha)$ is the injection from closed set $B$ to $\bigcup P_n$.

Closure under countable intersection:
The idea is to devise a set $B$ whose elements code elements in $B_n$ that share the same image:

Fix a bijection $\Gamma:\omega^2\to \omega$, let $$B = \{\alpha\mid \alpha_n\in B_n, \pi_n(\alpha_n) = \pi_m(\alpha_m)\text{ for any }n,m\}$$
Here $\alpha_n(i) = \alpha(\Gamma(n,i))$. This is a closed set and set $\pi:\alpha\mapsto \pi_0(\alpha_0)$ and $\pi[B] = \bigcap P_n$.$\Box$

The converse of this statement is that:

**2E.7 If $C\subseteq \mathcal{N}$ is closed and $f$ is continuous and injective on $C$ to $X$, then $f[C]$ is Borel. 
This shows that the image of a Borel set under a continuous injection is Borel.**

Proof.


Notice that in Baire space, every compact set is no where dense, and hence the Baire space can not be written as a countable union of compact sets, and hence the following 'Proof' does not work:

For Polish spaces $U,X$, If $f:U\to X$ is a continuous function, $C\subseteq U$ is closed and $U$ can be written as a countable union of compact sets, then $f[X]$ is $\boldsymbol{\Sigma}^0_1$.

Proof: Let $U = \bigcup_n U_n$ where $U_n$ is compact, then $U_n\cap C$ is compact. And hence $f[U_n\cap C]$ is compact (continuous function preserves compactness) and hence closed as $X$ is Hausdorff. Hence $f[X] =\bigcup_n f[U_n\cap C]$ and is $\boldsymbol{\Sigma}^0_1$.