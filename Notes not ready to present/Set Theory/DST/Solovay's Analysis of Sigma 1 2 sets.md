---
title: Solovay's Analysis of Sigma 1 2 sets
draft: false
tags: 
date:
---
We build on the results in the Solovay model part of [[Note_for_the_forcing_project (1).pdf]] to give a characterisation of Lesbegue Measurability and Baire Property of $\Sigma^1_2$ sets. The result would essentially parallel the Mansfield Solovay theorem in [[Pointsets in Constructible Universe]].

**Theorem 25.38 The following are equivalent:**
1. For each $a\subseteq \omega$, $\aleph_1^{L[a]}$ is countable
2. Every $\boldsymbol{\Sigma^1_2}$ set has perfect set property
3. Every $\boldsymbol{\Pi^1_1}$ set has perfect set property

Can we say the same for PSP?

----
Recall that we say a set of reals is Solovay over $M$ iff there is a formula, with parameters in $M$ s.t. 

$$x\in S\iff M[x]\models \varphi(x)$$

Recall the following theorem:
**Corollary 26.6 Let $S$ be a Solovay set of reals over $M$.**
1. If the set of all reals that are not random over $M$ is null, then $S$ is Lebesgue measurable.
2. If the set of all reals that are not Cohen over $M$ is meager, then $S$ is Baire.


**Theorem 26.20 For $a\in \mathcal{N}$, every $\Sigma^1_2(a)$ is Lebesgue measurable iff reals that are random over $L[a]$ is conull.**

**For $a\in \mathcal{N}$, every $\Sigma^1_2(a)$ is Baire iff reals that are Cohen over $L[a]$ is comeager.**

Proof. We only prove the case for Lebesgue Measurability. For the right to left direction: If $A$ is $\Sigma^1_2(a)$, we observe that it is Solovay over $L[a]$:

By Shoenfield Theorem in [[Well Founded Tree, Coanalytic Sets and Sigma 1 2 Sets]], let $T\in L[a]$ be a tree of $\omega\times \omega_1$ such that for all real $x$,
$$x\in A\iff T(x)\text{ is ill-founded.}$$
By the absoluteness of ill-foundedness, 
$$x\in A\iff (L[a])[x]\models T(x)\text{ is ill-founded.}$$
Hence $A$ is Solovay over $L[a]$. Hence if reals that are random over $L[a]$ is conull, then by Corollary 26.6 we have that $A$ is Lebesgue measurable.

For the other direction, we let $$B = \bigcup\{A_c\mid c\text{ is a Borel code}, c\in L[a], A_c\text{ is null.}\}$$
This is the union of all null Borel sets coded in $L[a]$, since $BC$, the set of all Borel codes is a $\Pi^1_1$ property, this set is a $\Sigma^1_2(a)$.

It suffice to show that $B$ is null, since a real is random over $M$ iff it is not in any Borel null set coded in $M$ (Lemme 26.4). 

Now consider $C(x,c)\subseteq \mathcal{N}$ which denotes the inclusion relation of $x$ and a null $A_c$, and $D(x,c)$ which says that $c$ is the first such $c$ that satisfies $C(x,c)$ in $L[a]$:
$$C(x,c)\iff c\in BC\land A_c\text{ is null }\land x\in A_c$$
$$D(x,c)\iff C(x,c)\land c\in L[a]\land \forall d<_{L[a]}c,\neg C(x,d)$$
Finally, we compare $x,y$ by the following:
$$x\preceq y\iff \exists c,d(D(x,c)\land D(y,d)\land c\leq_{L[a]}d)$$
applying the trick in Lemma 25.27 and Corollary 25.29 in [[Pointsets in Constructible Universe]], 
$$D(x,c)\iff C(x,c)\land c\in L[a]\land \exists e(R(e,c)\land \forall n\neg C(x,e_n))$$
Hence $D$ is a $\Sigma^1_2(a)$ relation.
Hence $\preceq$ is $\Sigma^1_2(a)$, thus by assumption is Lesbegue measurable in $\mathcal{N}^2$. For arbitrary $y\in B$ and say $D(y,d)$, notice $\{x\mid x\preceq y\} = \bigcup_{c<_{L[a]}d}A_c$, which is a countable union of null sets, thus null. Hence by Fubini, $\preceq$ is null. By a similar argument, $B^2 - \preceq$ is null. Hence $B$ is a null set. $\Box$

The following is what we got as a Corollary:

**Corollary 26.21 If $\omega_1^{L[a]}<\omega_1$, then all $\Sigma^1_2(a)$ sets are Lesbegue measurable, have the Baire property and the perfect set property.**

Proof. The Lesbegue measurable and the Baire property part follows from the above theorem, as if $\omega_1^{L[a]}<\omega_1$, there are only countably many Borel codes in $L[a]$ and hence the random and Cohen reals are conull and comeagre. 

The perfect set property part follows from Mansfield Solovay theorem in [[Code of WO and WF, and the Study of Sigma 1 2 sets under Recursion Theory]]. 

The following theorem is one of the most basic correlation between large cardinals and regularity of the reals, it turns out that $\omega_1$ is inaccessible in $L[a]$ for all $[a]$ under a measurable cardinal, hence the theorem follows. But for now I do not properly understand the fact.

**Theorem (Corollary 14.3 in Kanamori) If there is a measurable cardinal, then all $\boldsymbol{\Sigma^1_2}$ is Lesbegue measurable, have the Baire property and the perfect set property.**

----
### Judah - Shelah's theorem on $\Delta^1_2$ sets
Here we show that For $a\in \mathcal{N}$, every $\Delta^1_2(a)$ is Lebesgue measurable iff there is a real random over $L[a]$. And of course the similar statement holds for Baire property and Cohen reals. 

**Exercise 26.21 For $a\in \mathcal{N}$, every $\Delta^1_2(a)$ is Lebesgue measurable iff there is a real random over $L[a]$.**

Proof. For the left to right direction, in the proof of theorem 26.20, if there is no random real over $L[a]$, then $B = \mathcal{N}$ and $$x\preceq y\iff \forall c(D(y,c)\to \neg D(x,c))$$
Hence it is also a $\Pi^1_2(a)$ relation and hence $\preceq$ is $\Delta^1_2(a)$. Thus there is a $\Delta^1_2(a)$ null set.

For the other hand, let $r$ be a real random over $L[a]$, let $A = Q = \neg P$ where $P,Q$ are $\Sigma^1_2(a)$. Notice on the forcing notion $\mathcal{B}/I_n$, $I_n$ is the null ideal, the set $$D = \{p\mid p\Vdash P^{L[a][\dot{r}]}(\dot{r})\text{ or }p\Vdash Q^{L[a][\dot{r}]}(\dot{r})\}$$
The set is dense as, for any ultrafilter $U$, either $\dot{r}_U\in A^{L[a][U]}$ or not. By Shoenfield absoluteness, $A^{L[a][U]} = A\cap L[a][U] = Q \cap L[a][U] = Q^{L[a][U]}$. Similarly for $\neg P$. This means either $\dot{r}_U\in P^{L[a][U]}$ or $\dot{r}_U\in Q^{L[a][U]}$. Hence $1\Vdash  P^{L[a][\dot{r}]}(\dot{r})\vee Q^{L[a][\dot{r}]}(\dot{r})$.

Let $W$ be a maximal countable antichain of $D$, it exist as the forcing notion is c.c.c. consider 
$$Z_P = \bigcup\{A_c\mid c\in BC\cap L[a],A^{L[a]}_c\in W, A^{L[a]}_c\Vdash P^{L[a][\dot{r}]}(\dot{r})\}$$
and similarly define $Z_Q$. It suffice to show that $Z_P - P$ and $Z_Q - Q$ are null, then as $Z_P\cap Z_Q$ is null and $\mu^{L[a]}(Z_P)+\mu^{L[a]}(Z_Q) = 1$ by maximality of $W$, hence $P - Z_P \approx P\cap Z_Q = Z_Q - Q$, here $\approx$ means equal in measure. This means that $Z_Q\Delta A = Z_Q\cap Q$ is null, and hence since $Z_Q$ is a countable union of Borel sets, $A$ is Lebesgue measurable.

However, I fail to completely understand the argument that $Z_P - P$ is null.