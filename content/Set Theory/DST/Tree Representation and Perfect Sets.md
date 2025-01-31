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

The proof of the following Lemma applies the method in [[Two Proofs of Cantor-Bendixon]].

**2C.2 (The Perfect Set Theorem) In the Baire space, if P is $\kappa$-Suslin and has more than $\kappa$ elements, then $P$ has a non-empty perfect subset.**

Proof. Let $P = p[T]$. Consider the transfinite pruning of the tree:
$$T^0 = T$$
$$T^{\xi+1} =\{u\in T^\xi\mid p[T^\xi_u] \text{ is not a singleton or empty}\}$$
$$T^{\lambda} =\bigcap_{\xi<\lambda}T^\xi$$
Since $T$ is at most of size $\kappa$, the pruning process becomes constant after some $\xi<\kappa^+$. Let $T^* = T^\lambda$.

We show that $T^*$ is not empty. If $\alpha\in p[T]- p[T^*]$, let $(\alpha,f)\in [T]$, then $(\alpha,f)\in [T^\xi] - [T^{\xi+}]$ for some $\xi$. This means that for some $(\alpha|_n,f|_n)$, $p[T^\xi_{(\alpha|_n,f|_n)}]$ is a singleton $\{\alpha\}$.

This shows that $p[T]- p[T^*]\subseteq \bigcup\{p[T^\xi_u]\mid \xi\leq \kappa,u\in T^\xi-T^{\xi+1}\}$. Given $p[T]$ is of cardinality greater than $\kappa$, $p[T^*]$ is non-empty.

Now we show that $p[T^*]$ is a perfect set. For each $\alpha\in p[T^*]$, we show that it is not an isolated point. If not, there is $U_s$ s.t. $\alpha$ is the only sequence extending $s$. But there is $(\alpha,f)\in [T^*]$, the set $p[T^*_{(s,f|_n)}]$ should contain two elements, otherwise the node would be pruned. Then there is another $\beta\in U_s$. Hence $p[T^*]$ contains not isolated points and is perfect. $\Box$
