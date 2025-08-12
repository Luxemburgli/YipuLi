---
title: Code of WO and WF, and the Study of Sigma 1 2 sets under Recursion Theory
draft: false
tags: 
date:
---
### Light Face point classes

For now, I do not properly understand notions in recursion theory, by the end of the spring semester of 2025, I well return and polish on this part.

The light face point class are defined as following:

A set $A\subseteq \mathcal{N}$ is $\Sigma^0_1$ iff there is recursive $R\subseteq \bigcup_{n\in \omega}\omega^n$ s.t. $A = \{x\mid \exists n R(x|_n)\}$.

The $\Sigma^0_n,\Pi^0_n$ sets are built from $\Sigma^0_1$ sets as usual, they are called arithmetic sets.

A set $A\subseteq \mathcal{N}$ is $\Sigma^1_1$ iff there is a recursive $R\subseteq \bigcup_{n\in \omega}(\omega^n\times \omega^n)$ s.t. $$x\in A \text{ iff }\exists y\in \omega^\omega\forall n\in \omega(R(x|_n,y|_n))$$

A set $A\subseteq \mathcal{N}$ is $\Sigma^1_1(a)$ iff there is a recursive $R$ in $a$ s.t. $$x\in A \text{ iff }\exists y\in \omega^\omega\forall n\in \omega(R(x|_n,y|_n,a|_n))$$

We fix a recursive function $\Gamma$ from $\omega^2$ to $\omega$, we say $x\in \mathcal{N}$ codes a binary relation $E_x$ on $\omega$, if $$mE_xn \iff x(\Gamma(m,n)) = 0$$
Let $WF = \{x\in \mathcal{N}\mid x \text{ codes a well-founded relation}\}$. $WO = \{x\in \mathcal{N}\mid x \text{ codes a well-ordering}\}$.

----
### WF and WO

**Lemma 25.9 in Jech WF and WO are $\Pi^1_1$**
Proof. $x\in WF \text{ iff }\forall z\in \omega^\omega \exists k \neg z(k+1)E_xz(k)$. The property $\exists k \neg z(k+1)E_xz(k)$ is arithmetical.

However, neither of WF, WO is Borel. The following theorem shows that WF, WO are $\boldsymbol{\Pi}^1_1$ complete and are in the sense the most representative $\boldsymbol{\Pi}^1_1$ set.

**Theorem 25.12 For each $\boldsymbol{\Pi}^1_1$ set $C$ on $\mathcal{N}$ there is continuous function $f:\mathcal{N}\to \mathcal{N}$ s.t. $C = f^{-1}(WF)$. The similar conclusion is true for WO.**

Proof. We find tree $T$ on $\omega^2$ s.t. $\alpha\in C$ iff $T(\alpha)$ is well-founded.

Consider a coding $\pi: \omega\to \omega^{<\omega}$, we let $f:\mathcal{N}\to \mathcal{N}$ be given by the following: $f(\alpha)$ is a code of the tree relation of $T(\alpha)$, we can canonically choose a code for each relation.

$$mE_{f(\alpha)}n \iff \pi(m)<_{T(\alpha)}\pi(n)$$

Then clearly $C = f^{-1}(WF)$, $f$ is continous.$\Box$

**Corollary 25.13 WF,WO are not $\boldsymbol{\Sigma}^1_1$.**

----
### Shoenfield Absoluteness
We recall the proof of Shoenfield theorem in [[Well Founded Tree, Coanalytic Sets and Sigma 1 2 Sets]] that every $\boldsymbol{\Sigma}^1_2$ set is $\aleph_1$ Suslin, as the rank function on a $\omega$ tree can be coded as function from $\omega$ to $\omega_1$.

Reviewing on the proof, if $A$ is $\Sigma^1_2(a)$, then $T$ is definable from $a$ and hence $S$ is definable from $a$. This shows that the final $S\in L[a]$.

The coding of rank function motivates the following theorem:

**Theorem 25.20 (Shoenfield Absoluteness)_Every $\Sigma^1_2(a)$ relation and every $\Pi^1_2(a)$ relation is absolute for all inner models M of ZF+DC such that a ∈ M.**

Remark: It suffice that $M$ is a transitive model containing $a,\omega_1$ and models ZF+DC.

Proof. Let $U$ be a tree arithmetic in $a$ on $\omega^3$ s.t. $$x\in A\iff \exists y Ux,y)\text{ is well-founded}$$
<font color="red">I suspect that if U is arithmetic in a and a is in M entails that U is in M, but I'm not sure.</font>
Hence $$x\in A^M\iff \exists y\in M, M\models U(x,y)\text{ is well-founded}$$
Given absoluteness of well-foundedness,  $$a\in A^M\iff \exists y\in M,  U(x,y)\text{ is well-founded}$$
And hence $A^M\subseteq A\cap M$.

On the other hand, the proof of Shoenfield theorem give us $T$ of $\omega\times \omega_1$ s.t. $$x\in A\iff T(x)\text{ if ill founded}$$
Hence by absoluteness of well-foundedness, $$x\in A\cap M\iff M\models T(x)\text{ if ill founded}$$
Working backward in $M$ as in the proof of Shoenfield theorem, this gives $U$ of $\omega^3$ and $y$ s.t $x\in A\cap M\to M\models\exists y U(x,y)$ is well founded. This means $x\in A^M$. Hence $x\in A\cap M$ iff $x\in A^M$. This completes the proof. $\Box$

Jech states that the theorem entails that all $\boldsymbol{\Sigma}^1_2$ relations are absolute for $L$, which I don't understand for now.

**Corollary 25.21 If $A\subseteq \omega$ is $\Sigma^1_2(a)$ then $A\in L[a]$. Every $\Sigma^1_2$ (thus $\Pi^1_2$) real is constructible.**

Proof. By the absoluteness theorem, $A^{L[a]} = A\cap L[a] = A$ as $\omega\subseteq L[a]$.

----

### Perfect Set Property for $\Sigma^1_2$ Sets.

**Theorem 25.23(Mansfield-Solovay) If $A$ is a $\Sigma^1_2(a)$ set of $\mathcal{N}$, and it contains an element not in $L[a]$, then $A$ contains a perfect set.**

This is a corollary of the following, which is a result in parallel with 2C.2 in [[Tree Representation and Perfect Sets]], using the pruning tree technique. Also refer to [[Solovay's Analysis of Sigma 1 2 sets]] for Solovay's characterisation of other regular properties of $\Sigma^1_2(a)$ sets.

**Lemma 25.24 If $A$ is $\kappa$ Suslin and  $T$ is a tree on $\omega\times \kappa$ s.t. $A = p[T]$, then either $A\subseteq L[T]$ or $A$ contains a perfect set, in particular in the latter case, there is a perfect tree $U\in L[T]$ s.t. $[U]\subseteq A$.**

Proof. This is another Cantor-Bendixon style proof.

Let $$T' = \{(s,h)\in T\mid \exists (s_1,h_1),(s_2,h_2)\in T \text{ extending }(s,h) \text{ and }s_1,s_2\text{ are incompatible.}\}$$
And $T_0 = T,T_{\alpha+1} = T'_\alpha, T_\lambda = \bigcap_{\xi<\lambda}T_\xi$.

The operation $T'$ is absolute for models containing $T$. Hence inductively, $T_\alpha\in L[T]$ for all $T$. Fix $T_\alpha$ s.t. $T_\alpha = T_\beta$ for $\beta\geq \alpha$.

Case 1: $T_\alpha = \emptyset$, hence for each $x\in A$, $(x,f)\in T$ for some $f\in \kappa^\omega$. Find $\xi$ s.t. $(x,f)\in [T_\xi] - [T_{\xi+1}]$. Hence there is $(s,h)\in T$ s.t. whenever $(s',h')\supseteq (s,h)$, $(s',h')\subseteq (x,f)$. This means $(x,f) = \bigcup\{(s',h')\in T_\xi\mid (s,h)\subseteq (s',h')\}$ and thus $x\in L[T]$. 

Case 2: $T_\alpha\neq \emptyset$. Then every node in $T_\alpha$ has two or more extensions imcompatible in the first coordinate, hence we can construct a perfect $U$ of $\omega$ from the first coordinates of $T_\alpha$. $U\in L[T]$ and $[U]\subseteq p[T] = A$. $\Box$

----

### Ordinal Definability of Projective sets
This section we aim to show that every projective set is definable from a sequence of ordinals, this answering a question remained in [[Note_for_the_forcing_project (1).pdf]].

**Lemma 25.25 $A\subseteq \mathcal{N}$ is $\Sigma^1_2$ iff it is $\Sigma_1$ over $(HC,\in)$.**

Proof sketch. The idea is to use a real to code a model.

As a corollary, all $\Sigma^1_n(a)$ are definable as a $\Sigma_n$ formula over $(HC,\in)$ with parameter $a$.

**Corollary If $A$ is projective, then $A$ is definable from a sequence of ordinals.**

Proof. Say $A$ is $\boldsymbol{\Sigma^1_n}$, then $A$ is $\Sigma^1_n(a)$ for some $a\in\mathcal{N}$. Then it is definable in $HC$ from $a$, $a$ is a sequence of ordinals and hence $A\in OD(S)$. 