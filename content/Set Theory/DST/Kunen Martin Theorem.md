---
title: Kunen Martin Theorem
draft: false
tags: 
date:
---
 For a relation $R$, let its strict part be 
 $<_R\subseteq R$ where $x<_R y$ iff $xRy$ and not $yRx$. Notice $<_R$ need not be an order. 
 
  $R$ is well-founded if there is no infinite descending chain for its strict part.

Here I follow the proof in the handout given by Christian Rosendal, because I think the proof of 2G.1 in Moschovakis is wrong.

For a strict, well-founded relation $\prec$, we associate a tree $T_\prec$ consisting of the descending chains of the relation, ordered by inclusion. Then $T_\prec$ admits a rank function $\rho$, and we say the rank of $\prec$, $\rho(\prec)$ is $\rho(\emptyset)$. It is clear that $\rho(\prec)$ is the upper bound of the order type of increasing chains of $\prec$.

**Theorem(Kunen-Martin) If relation $<$ on $\mathcal{N}$ in $\kappa$-Suslin, then $\rho(\prec)<\kappa^+$.**

Proof. The idea is to map the tree of descending chains of $\prec$ to <font color = "red">a tree of approximation of descending chains </font> that has cardinality less than $\kappa^+$. Then use the fact that if there is $\phi:T\to T'$ order preserving, then $\rho(T)\leq \rho(T')$.

Write $x\prec y$ iff $\exists^\mathcal f\in \kappa^\omega (x,f,y)\in [T]$, where $T$ is a tree of $\omega\times \kappa\times \omega$.

Let $W$ be a tree consisting of strings $$(s_0,u_1,s_1,u_2\dots s_n,u_n)$$
where $s_i\in \omega^{<\omega}$, $u_i\in \kappa^{<\omega}$ and $(s_{i-1},u_{i},s_i)\in S$. Let 
$$(s_0,u_1,s_1,u_2\dots s_n,u_n) >^* (s_0',u_1',s_1',u_2'\dots s_m',u_m')$$
if $m>n$ and $s_i,u_i$ are initial segments of $s_i',u_i'$ respectively.

The tree can be seen as collecting finite approximations of a descending sequence of $R$.

The order $>^*$ is well founded, as otherwise given a sequence $(s_0^n,u_1^n,s_1^n,u_2^n\dots s_n^n,u_n^n)$ would induce a descending sequence for $R$ given by: $x_i = \bigcup_n s_i^n$, and $f_i = \bigcup_nu^n_i$ would witness $x_{i-1}Rx_i$. 

Now the tree $W$ is of cardinality $\kappa$, hence $\rho(W,\emptyset)\leq \kappa$.

Let $S$ be the tree of descending chains of $\prec$. Consider the map $\phi:S\to W$ given by $\phi(x_0,\dots x_n) = (x_0|_n, f_1|_n x_1|_n\dots f_n|_n, x_n|_n)$, here $f_i$ is a witness such that $\exists f, (x_0,f,x_1)\in [T]$. This map is of course order preserving. Hence $\rho(\prec)<\rho(<^*)<\kappa^+$. $\Box$

As a corollary, increasing chains in $\boldsymbol{\Sigma}^1_1$ well-founded relations are at most countable and increasing chains in $\boldsymbol{\Sigma}^1_2$ well-founded relations have order type less than $\omega_2$.

 
%%

Remember from [[Suslin Sets and the Separation theorems]] the definition of semi scales:

A *norm* on a pointset $P$ is a function $\varphi:P\to Ordinals$ which assigns an ordinal number $\varphi(x)$ to every $x\in P$. A *$\lambda$-norm* is a norm that is bounded by $\lambda$.

A *semi-scale* is a sequence of norms $\varphi_n$ s.t. if $x_0,x_1\dots$ are in $P$ and $x$ is their limit, and if for each $n$ $\varphi_n(x_0),\varphi_n(x_1)\dots$ is ultimately constant, then $x\in P$. A *$\lambda$-semi-scale* is a semi-scale that consists of $\lambda$-norms.

A semi-scale is *good* if whenever for each $n$ $\varphi_n(x_0),\varphi_n(x_1)\dots$ is ultimately constant, then there is $x\in P$ s.t. it is the limit of $x_n$.

<font color="red">I feel like the proof of this theorem is wrong, why does a sequence points ultimately landing in a ball entails it converges?</font>

 **2G.1 If $P$ admits a $\kappa$ semi-scale, then it admits a good $\kappa$ semi-scale**

Proof. Fix a bijection $\pi:\omega\times \kappa\to \kappa$. For each $x\in P$, fix a function $q(x,i)$ s.t. $x\in U_{q(x,i)}$ and $radius U_{q(x,i)}\leq \frac{1}{2}$. Here $U_n$ is a countable basis.

Then consider the norm $\psi_n(x) = \pi(q(x,n),\varphi_n(x))$.

In $\psi_n(x_0),\psi_n(x_1)\dots$ is ultimately constant, then the sequence 
$$q(x_0,n), q(x_1,n)\dots$$
$$\varphi_n(x_0), \varphi_n(x_1)\dots$$
are both ultimately constant.

%%



