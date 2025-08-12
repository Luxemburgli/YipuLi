---
title: Ch.13 of Schindler's text book
draft: false
tags: 
date:
---
## Problem 13.1
The solution goes as the hint in D.A. Martin's Exercise 8.3.2

We fix an enumeration of $\omega^\omega$: $(x_\alpha,\alpha<2^{\aleph_0})$. Let $(M_\alpha,\pi_{\alpha,\beta},\alpha<\beta\in Ord)$ be the linear iteration of $V$ by $U$, the normal $\kappa$ complete ultrafilter on $\kappa$.  Let $N = M_{2^{\aleph_0}}$. Let $\kappa_\alpha$ be $\pi_{0,\alpha}(\kappa)$.

For $s\in \omega^{<\omega}$, $\alpha<2^{\aleph_0}$, define $j^s_{\alpha,\beta}:N\to N$ elementary by: $$j^s_{\alpha,\alpha+1} = \begin{cases}\pi_{\omega\cdot \alpha,\omega\cdot \alpha+1} &\text{ if }s\subseteq x_\alpha,x_\alpha\not\in A\\
id &\text{otherwise}
\end{cases}$$
The case $j^s_{\gamma,\alpha+1}$ where $\gamma<\alpha$ is defined by $j^s_{\gamma,\alpha} = j^s_{\alpha,\alpha+1}\cdot j^s_{\gamma,\alpha}$. And the limit case is by directed limit.

Define $M_\emptyset = V$, $M_s = N$ for $s\neq \emptyset$. For $s\subseteq t$ s.t. $lh(t) = lh(s) + 1$, $$k_{s,t} = \begin{cases}
\pi_{0,\aleph_0} &\text{if }s = \emptyset \\
j^s_{0,2^{\aleph_0}} &\text{otherwise}
\end{cases}$$
The other $k_{s,t}$ are defined by commutivity. We notice the effect of $k_{s,t}$ on the critical points where $lh(t) = lh(s) + 1$:
$$k_{s,t}(\kappa_{\omega\cdot \alpha+k}) = \begin{cases}\kappa_{\omega\cdot \alpha+k+1} &\text{ if }s\subseteq x_\alpha,x_\alpha\not\in A\\
\kappa_{\omega\cdot \alpha+k} &\text{otherwise}
\end{cases}$$

Now we show that $(M_s,k_{s,t},s\subseteq t\in\omega^{<\omega})$ is a embedding normal form for $A$.

If $x_\alpha\not \in A$, then for each $n$, $k_{0,x|_n}(\kappa_\alpha)>k_{0,x|_{n+1}}(\kappa_\alpha)$ as $\pi_{\omega\cdot \alpha}$ is acted in $k_{x|_{n},x|_{n+1}}$. Hence $M_{x_\alpha}$ is ill founded.

If $x_\alpha\in A$, let $n_\beta = 0$ if $x_\beta \in A$, otherwise $n_\beta = max\{n\mid x_\beta|_n = x_\alpha|_n\}$.  $M_{x_\alpha}$ can be decomposed as $dir\lim (\pi_{\omega\cdot \alpha}^{n_\alpha}(N), \alpha<2^{\aleph_0})$, which is well-founded. $\Box$

------
## Problem 13.2
If $x\not\in A$, then the tree $T_x: = \{t\in \alpha^{<\omega}\mid (x|_{len(t)},t)\in T\}$ is well-founded. Then for each $n$, $$||[id]_{\mu_{x|_n}}||_{\pi_{\mu_{x|_n}(T_x)}}$$ is an ordinal. To show that the direct limit is ill-founded, it suffice to show that $$||[id]_{\mu_{x|_{n+1}}}||_{\pi_{\mu_{x|_{n+1}}(T_x)}}<\pi_{\mu_{x|_n},\mu_{x|_{n+1}}}(||[id]_{\mu_{x|_n}}||_{\pi_{\mu_{x|_n}(T_x)}}) = ||\pi_{\mu_{x|_n},\mu_{x|_{n+1}}}([id]_{\mu_{x|_n}})||_{\pi_{\mu_{x|_{n+1}}(T_x)}}$$
Suppose $||\pi_{\mu_{x|_n},\mu_{x|_{n+1}}}([id]_{\mu_{x|_n}})||_{\pi_{\mu_{x|_{n+1}}(T_x)}} = \beta$, we have $\pi_{\mu_{x|_n},\mu_{x|_{n+1}}}([id]_{\mu_{x|_n}})(t) =[id]_{\mu_{x|_n}}(t|_n) = t|_n$ for arbitrary $t\in T_{x|_{n+1}}$. Thus there is $X\in \mu_{x|_{n+1}}$ s.t. for all $t\in X, ||t|_n||_{\pi_{\mu_{x|_{n+1}}}} = \beta$, but as for any $t\in X$, $$||t||_{\pi_{\mu_{x|_{n+1}}}}<||t|_n||_{\pi_{\mu_{x|_{n+1}}}}$$we have the desired result. $\Box$

---
## Problem 13.3
(b) to (a). Fix $T$ on $\omega\times \alpha$ s.t. $A = p[T]$ and $\mu_s$ is a $<\delta^+$ closed ultrafilter on $T_s$. We define the following system of elementary embedding: $(M_s,\pi_{s,t},s\subseteq t\in \omega^{<\omega})$. Where $M_s = Ult(V,\mu_s)$. Then by problem 13.2 we have $x\in A$ iff $dir\lim_{n<\omega}(M_{x|_n})$ is well-founded. It suffice to check that thus defined, the embedding normal form is $2^{\aleph_0}$ closed and its additivity is bigger than $\delta$.

As $crit(\pi_{\mu_s}) \geq \delta^+$, $\pi_{s,t}|_{\delta+1} = id$ for any $s\subseteq t\in \omega^{<\omega}$. To show that the embedding normal form is $2^{\aleph_0}$ closed, either $\mu_s$ is trivial and thus $Ult(V,\mu_s) = V$, thus trivially $2^{\aleph_0}$ closed; or $\mu_s$ is not trivial in which case let $\kappa$ be the critical point of $\pi_{\mu_s}$ and thus $2^{\aleph_0}<\kappa$, $Ult(V,\mu_s)$ is $\kappa$ closed.

(a) to (b). Let $(M_s,\pi_{s,t},s\subseteq t\in\omega^{<\omega})$ be the assumed embedding normal form. We work as hinted. Let $\alpha^n_x,n<\omega$ be the ordinals witnessing $M_x$ is ill-founded in $x\not\in A$; let $T$ be the Windßus tree for the embedding normal form and $\alpha_s(x)$ be as defined in the proof theorem 13.2. Define the following ultrafilter $\mu_s$ on $T_s$: for $X\subseteq T_s$, $$X\in \mu_s\iff (\pi_{\emptyset,s}(\alpha_\emptyset)\dots\alpha_s)\in \pi_s(X)\subseteq  \pi_s(T_s) = \{f\mid (s,f)\in \pi_s(T)\}$$
Let $\sigma_s:V\to Ult(V,\mu_s)$ be the generated elementary embedding. The conclusion follows from the following claims:

(1) If $s\subseteq t\in \omega^{<\omega}$, then $\mu_s,\mu_t$ is cohere. This is because $$\begin{align*}
(\pi_{\emptyset,s}(\alpha_\emptyset),\dots \alpha_s)\in \pi_s(X)&\iff (\pi_{\emptyset,t}(\alpha_\emptyset),\dots \pi_{s,t}(\alpha_s))\in \pi_t(X)\\
&\iff (\pi_{\emptyset,t}(\alpha_\emptyset),\dots \pi_{s,t}(\alpha_s),\dots \alpha_t)\in \pi_t(\{f\in T_t\mid f|_{|s|}\in X\})
\end{align*}$$
(2) There is the factor elementary embedding $k_s:Ult(V,\mu_s)\to M_s$ s.t. $k_s\cdot \sigma_{s} = \pi_s$.

Just let $k_s: \sigma_s(F)((\pi_{\emptyset,t}(\alpha_\emptyset),\dots \pi_{s,t}(\alpha_s),\dots \alpha_t))\mapsto \pi_s(F)((\pi_{\emptyset,t}(\alpha_\emptyset),\dots \pi_{s,t}(\alpha_s),\dots \alpha_t))$
for $F:T_s\mapsto V$.

(3) If $x\in A$, then $$dir\lim_{n<\omega}(ult(V,\mu_{x|_n}),\pi_{\mu_{x|_n},\mu_{x|_m}},n<m<\omega)$$ is well founded.

This is because by point (2), we have for $s\subseteq t\in \omega^{<\omega}$, $\pi_{s,t}\cdot k_s = k_t\cdot \sigma_{s,t}$. This gives for each $Ult(V,\mu_s)$, a map $\pi_{s,x}\cdot k_s: Ult(V,\mu_s)\to M_x$ satisfying $\pi_{s,x}\cdot k_s =\pi_{t,x}\cdot k_t\cdot \sigma_{s,t}$. Hence this gives an elementary embedding $j:dir\lim_{n<\omega}(ult(V,\mu_{x|_n}),\pi_{\mu_{x|_n},\mu_{x|_m}},n<m<\omega) \to M_x$, witnessing the well-foundedness of the directed limit.

(4) Each $\mu_s$ is $<\delta^+$ closed, otherwise say $\xi$ is the least cardinal s.t. $\mu_s$ is $<\xi$ closed. Then there is a partition $X_i,i<\xi$ of $T_s$ s.t. $X_i\not\in \mu_s$. Define $a:x=f\mapsto i$ if $f\in X_i$ for $f\in T_s$. We thus have $\xi\leq[a]_{\mu_s}<\sigma_s(\xi)$. Finally, as $\pi_s(\xi)\geq \sigma_s(\xi)$ and $\xi\leq\delta$, this contradicts the fact that $\pi_s|_{\delta+1} = id$.$\Box$

---
## Problem 13.4
(1) Assume that $A = \{x\mid \exists y, x\oplus y\in B\}$, assume that $T$ on $\omega\times \alpha$ and the system $\mu_s,s\in \omega^{<\omega}$ witnesses the $\delta$-homogeneously Susliness of $B$. 

Fix a bijection $\Gamma:\omega\times \alpha\to \alpha$. We first define the tree $T^*$ on $\omega\times \alpha$ as $t^*\in T^*$ iff the map $t$ defined by $t(2n,\xi)=t^*(n,\Gamma(n,\xi))$ and $t(2n,\xi) = t^*(n,\xi)$ is in $T$. Then $p[T] = A$.

Next for any $y\in \omega^{\omega}$, $x\not\in A$, let $\alpha_n^{x,y}$ witness the ill-foundedness of $dir\lim_{n<\omega}(Ult(V,\mu_{s_1\oplus s_2}), s_1\subseteq x,s_2\subseteq y)$. Let $\gamma$ be some ordinal greater than all of them. Fix an enumeration of $\omega^{<\omega}$ s.t. $s_i\subseteq s_j$ then $i<j$. Define the following tree on $\omega\times \gamma^{<\omega}$: $(s,(\alpha_0\dots \alpha_{k-1}))\in S$ iff for all $i<j<k$, if $s_i\subsetneq s_j$ then $$\delta^+<\alpha_j<\pi_{\mu_{s|lh(s_i)\oplus s_i,s|lh(s_j)\oplus s_j}}(\alpha_i)$$
Then we have $x\in p[S]$ iff $x\not\in A$. 

Next we show that for any $\mathbb{P}\in H_{\delta^+}$, $\Vdash^\mathbb{P}p[T^*]\cup p[S] = \omega^{\omega}$. By the argument in problem 10.19, we have for $\mathbb{P}$ name $\tau$, $\pi_{\mu_s}^{V[G]}(\tau_G) = (\pi_{\mu_s}(\tau))_G$, specifically for element $a$ in $V$, $\pi_{\mu_s}^{V[G]}(a) = \pi_{\mu_s}(a)$. 

Let $G$ be a generic filter, work in $V[G]$. If $x\not\in p[T^*]$, then for all $y\in \omega^\omega$, $x\oplus y\not\in B$, i.e. for any $y\in \omega^\omega$, there is $\alpha_n^{x,y}$ witnessing the ill-foundedness of $dir\lim_{n<\omega}(Ult(V,\mu_{s_1\oplus s_2}), s_1\subseteq x,s_2\subseteq y)$. Thus $(x|_n, (\alpha^{x,y}_0,\dots,\alpha^{x,y}_{n-1})), n\in \omega$ would be an infinite branch in $S$.

(2) Let $A$ be arbitrary $\boldsymbol{\Sigma}^1_2$ set, and write $A = \{x\mid \exists y\in \omega^\omega, x\oplus y \in B\}$ where $B$ is $\boldsymbol{\Pi}^1_1$. 

From the proof of theorem 13.3, we obtain that $B$ has a $2^{\aleph_0}$ closed embedding normal form which has additivity greater than $\delta$ for arbitrary $\delta<\kappa$. By the proof of problem 13.3 there is tree $T$ and system $\mu_s,s\in \omega^{<\omega}$ s.t. each $\mu_s$ is $<\kappa$ closed. By the proof of problem 13.4, $A$ is thus $<\kappa$ universally Baire. 

(3) Prove by induction on $n$ that if there are $n$ many measurable cardinals $\delta_1<\dots <\delta_n$ under $\kappa$, then all $\boldsymbol{\Pi}^1_{n+1}$ sets have a $2^{\aleph_0}$ closed embedding normal form whose additivity is bigger than $\delta_1$. The  The induction step is by theorem 13.6. For the base case: it is clear that the construction in theorem 13.3 is has additivity bigger than $\delta_n^+$. 

Then apply problem 13.3 and problem 13.4 and we are done.

---
## Problem 13.5
Let $A = p[T]$, $A^c = p[U]$ where $\Vdash_{\mathbb{P}}p[U]\cup p[T] = \omega^\omega$ for all $\mathbb{P}\in H_{\delta_1}$. Then for $g$ generic for $\mathbb{P}\in H_{\delta_1}$, $V[g]\models A^*\neq \emptyset$ iff $V[g]\models T$ is ill-founded iff $V\models T$ is ill-founded iff $V\models A\neq \emptyset$.$\Box$


---
