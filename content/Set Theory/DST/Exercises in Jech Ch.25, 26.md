---
title: Exercises in Jech Ch.25, 26
draft: false
tags: 
date:
---
## Ch. 26

*Exercise 26.1*

First we show that $\mathcal{B}_c$ has a countable dense set. Consider the set $\{[I_n]\mid n\in \omega\}$, where $I_n$ enumerates the rational intervals. For arbitrary Borel set that is not empty $B$, as $B$ has Baire property, $B = U\Delta M$, where $U$ is open and not empty and $M$ is meager. Hence $B\Delta U = M$ and $[B] = [U]$. Hence there is $[I_n]\leq [B]$. Hence $\{[I_n]\mid n\in \omega\}$ is dense.

If $\mathcal{B}$ is another complete, atomless Boolean algebra with $D_n,n\in \omega$ as its dense set, then the map $$\pi: \mathcal{B}  \to \mathcal{B}_c$$
$$\bigvee_{n\in A} [I_n] \mapsto \bigvee_{n\in A}D_n$$
is an isomorphism.

----

*Exercise 26.2*

**Exercise 26.21 For $a\in \mathcal{N}$, every $\Delta^1_2(a)$ is Lebesgue measurable iff there is a real random over $L[a]$.**

Proof. For the left to right direction, in the proof of theorem 26.20, if there is no random real over $L[a]$, then $B = \mathcal{N}$ and $$x\preceq y\iff \forall c(D(y,c)\to \neg D(x,c))$$
Hence it is also a $\Pi^1_2(a)$ relation and hence $\preceq$ is $\Delta^1_2(a)$. Thus there is a $\Delta^1_2(a)$ null set.

For the other drection, let $r$ be a real random over $L[a]$, let $A = Q = \neg P$ where $P,Q$ are $\Sigma^1_2(a)$. Notice on the forcing notion $\mathcal{B}/I_n$, $I_n$ is the null ideal, the set $$D = \{p\mid p\Vdash P^{L[a][\dot{r}]}(\dot{r})\text{ or }p\Vdash Q^{L[a][\dot{r}]}(\dot{r})\}$$
is dense as, for any generic filter $U$, either $\dot{r}_U\in A^{L[a][U]}$ or not. By Shoenfield absoluteness, $A^{L[a][U]} = A\cap L[a][U] = Q \cap L[a][U] = Q^{L[a][U]}$. Similarly for $\neg P$. This means either $\dot{r}_U\in P^{L[a][U]}$ or $\dot{r}_U\in Q^{L[a][U]}$. Hence $1\Vdash  P^{L[a][\dot{r}]}(\dot{r})\vee Q^{L[a][\dot{r}]}(\dot{r})$.

Let $W$ be a maximal countable antichain of $D$, it exist as the forcing notion is c.c.c. consider 
$$Z_P = \bigcup\{A_c\mid c\in BC\cap L[a],A^{L[a]}_c\in W, A^{L[a]}_c\Vdash P^{L[a][\dot{r}]}(\dot{r})\}$$
and similarly define $Z_Q$. It suffice to show that $Z_P - P$ and $Z_Q - Q$ are null, then as $Z_P\cap Z_Q$ is null and $\mu^{L[a]}(Z_P)+\mu^{L[a]}(Z_Q) = 1$ by maximality of $W$, hence $P - Z_P \approx P\cap Z_Q = Z_Q - Q$, here $\approx$ means equal in measure. This means that $Z_Q\Delta A = Z_Q\cap Q$ is null, and hence since $Z_Q$ is a countable union of Borel sets, $A$ is Lebesgue measurable.

To show that $Z_P - P$ is null, let $M\in L[a]$ be a ctm for ZFC such that $\{c\in BC\cap L[a]\mid A^{L[a]}_c\in W, A^{L[a]}_c\Vdash P^{L[a][\dot{r}]}(\dot{r})\}\in M$, then the reals not random over $M$ is null. If $x$ is random over $M$, and is in $Z_p$, then for some $A_c^{L[a]}\Vdash P^{L[a][\dot{r}]}(\dot{r})$, $x\in A_c$, hence $x\in A_c^{M[x]}$ and $A^{M}_c\Vdash P^{M[\dot{r}]}(\dot{r})$. This means that $x\in P^{M[x]}$, by absoluteness $x\in P$. Hence $Z_P - P$ are all reals that are not random over $M$, thus null. This completes the proof.


----

*Exercise 26.4*

For arbitrary $X\subseteq [\omega]^2$, consider the set $\bigcup \{N_{\{n_1,n_2\}}\mid \{n_1,n_2\}\in X\}\subseteq [\omega]^\omega$ and this is a clopen set. Here $N_{\{n_1,n_2\}} = \{x\in [\omega]^\omega\mid \{n_1,n_2\}\text{ is an initial segment of } x\}$.

Hence pick $[y]^\omega$ homogeneous of  $\bigcup \{N_{\{n_1,n_2\}}\mid \{n_1,n_2\}\in X\}$. Then $[y]^2$ is homogeneous of $X$.

---

*Exercise 26.8*
Consider the forcing notion consisting of pairs $(s,E)$ where $s$ is in $\omega^{<\omega}$ and $E$ is a finite subset of $\lambda$.

$(s,E)< (t,F)$ if $s\supseteq t$ and for all $\alpha\in F$, $n\in dom(s)-dom(t)$, $s(n)>f_\alpha(n)$.

This forcing notion is c.c.c. as it can be decomposed into $\omega$ many parts $C_n$ with the property that for any $p_1\dots p_m\in C_n$, they have a  common extension. The decomposation is just $C_s = \{(s,E)\mid E\in [\lambda]^{<\omega}\}$

Then, the set $D_\alpha = \{(s,E)\mid \alpha\in E\}$ is dense and by MA, we have generic $G$ and $g = \bigcup G$ dominates the family of functions.

---
*Exercise 26.9*

Take a cofinal sequence $\{\alpha_\beta\mid \beta<\mu\}$ of $\mathfrak{d}$, we show that there is an unbounded family of size $\mu$.

If let $D$ be a dominating family of size $\mathfrak{d}$, write $D_\beta = \{f_\gamma\mid \gamma<\alpha_\beta\}$. Then for each $\beta<\mu$, there is $g_\beta$ s.t. for all $f\in D_\beta$, $g$ is not bounded by $f$. This is because $D_\beta$, being smaller than $\mathfrak{d}$, is not dominating.

We claim that $G = \{g_\beta\mid \beta<\mu\}$ is an unbounded family. Assume for contradiction that $f$ bounds $G$, take $f'\in D$ dominating $f$, then $f'$ bounds $G$ and this is a contradiction.

---
*Exercise 26.10*
If $F$ is a bounded family, then there is $g$ s.t. for all $f\in F$, $\forall^\infty n, f(n)<g(n)$. Then $F \subseteq \bigcup_n \{f\mid \forall m>n, f(m)<g(m)\}$, which is a countable union of countable, thus meager sets.

If $F$ is a dominating family, then $\omega^\omega = \bigcup_{f\in F}\bigcup_n \{g\mid \forall m>n, g(m)<f(m)\}$, this is a $\mathfrak{d}$ union of meager sets.

---
*Exercise 26.12*
If $F$ satisfies (26.30), then $\omega^\omega = \bigcup_{f\in F}\{g\mid \forall^\infty n f(n) \neq g(n)\} = \bigcup_{f\in F}\bigcup_n\{g\mid \forall m>n, f(m)\neq g(m) \}$.

The set $\{g\mid \forall m>n, f(m)\neq g(m) \}$ is no where dense.

If a family $F$ does not satisfy (26.31), then $F\subseteq \bigcup_n\{f\mid \forall m>n, f(m)\neq g(m) \}$ and hence is meager.

---
*Exercise 26.16*
Let $|A|<2^{\aleph_0}$.

Consider the Cohen forcing $\omega^{<\omega}$, for arbitrary sequence of real $a_0\geq a_1\dots$ For arbitrary $a\in A$, As in $L[a, (a_n,n\in \omega)]$, there are $\omega_1$ many dense sets of $\omega^{<\omega}$, there is a generic filter $G$ by MA that is generic over every $L[a, (a_n,n\in \omega)]$ for $a\in A$. Let $x\in \omega^{<\omega}$ be the generic real. 

Let $r_n$ be an enumeration of the rationals and $I_n$ be the interval with center $r_{x(n)}$ and radius $a_n$.

Notice for each $a\in A$, $\{t\mid a\in I_{len(t)}\}$ is a dense set in $L[a, (a_n,n\in \omega)]$, this means that $a\in \bigcup I_n$.

---

