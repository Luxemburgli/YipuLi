---
title: Well Founded Tree and Sigma 1 2 Sets
draft: false
tags: 
date:
---
 
A tree $T$ is well-founded if $[T] = \emptyset$, i.e. there is no infinite branch in the tree. We can do backward induction on a well-founded tree given by the following scheme:

On a well-founded tree $T$, $p(u)$ holds for all $u\in T$ if $P(u\frown x)$ for all $u\frown x\in T$ entails $P(u)$.

A tree $T$ is well founded iff it admits a rank function 
$$\rho(u) = 0 \text{ if $u$ is terminal in $T$ or }u\not\in T$$
$$\rho(u) = sup\{\rho(u\frown x)+1\mid u\frown x\in T\}$$
Given a $\alpha\in \omega^\omega$ and a tree on $\omega\times \kappa$, it gives a tree on $\kappa$:
$$T(\alpha) = \{u\in \kappa^{<\omega}\mid (\alpha|_{len(u)},u)\in T\}$$
It is then obvious that:

**2D.2 $P\subseteq \omega^\omega$ is $\kappa$ Suslin iff there is a tree on $\omega\times \kappa$ s.t. $$\alpha\in P\text{ iff }T(\alpha)\text{ is not wellfounded}$$**

This is trivial fact links elements in a co-analytic sets to properties of the tree $T(\alpha)$, and consequently to rank functions on $T(\alpha)$, thus giving a representation of it. Indeed, the rest of the notes is built on this seemingly trivial result. 

**2D.3(Shoenfield) Every $\boldsymbol{\Sigma}^1_2$ pointset is $\aleph_1$ Suslin.** 

Let $P$ be $\boldsymbol{\Sigma}^1_2$, then $P(\alpha)$ iff $\exists^{\mathcal{N}}\beta U(\alpha,\beta)$, here $U$ is $\boldsymbol{\Pi}^1_1$ in $\mathcal{N}^2$. There is a tree $T$ in $U$ of $\omega^3$ s.t. 
$$P(\alpha) \text{ iff }\exists^{\mathcal{N}}\beta, T(\alpha,\beta) \text{ admits a rank into }\aleph_1$$
The main idea is to devise a tree on $\omega^2\times \aleph_1$ s.t. each infinite branch codes a rank function of $T(\alpha,\beta)$.

Let $u_n$ enumerates $\omega^{<\omega}$ s.t. $len(u_n)\leq n$. For a function $f$ from $\omega$, let $f^*$ be the lifting $f^*(u_n) = f(n)$. Then 
$$P(\alpha) \text{ iff }\exists^{\mathcal{N}}\beta,\exists f:\omega\to \omega_1, f^*|T(\alpha,\beta)\text{ reverse the initial segment relation.}$$
Let $S$ be a tree on $\omega^2\times \omega_1$ s.t. $$S(s,t,h)\text{ iff }h^*|T_{s,t}\text{ reverse the initial segment relation.}$$
$T_{s,t} = \{u\in \omega\mid (s|_{len(u)},t|_{len(u)},u)\in T\}$. Here $h$ codes the rank function of $T_{s,t}\subseteq T(\alpha,\beta)$.

Now $P(\alpha)$ 

iff $\exists^{\mathcal{N}}\beta,\exists f:\omega\to \omega_1, f^*|T(\alpha,\beta)$ reverse the initial segment relation.

iff $\exists^{\mathcal{N}}\beta,\exists f:\omega\to \omega_1,$ for all $n$, $f^*|T_{s,t}$ reverse the initial segment relation.

iff $\exists^{\mathcal{N}}\beta,\exists f:\omega\to \omega_1,$ $S(\alpha|_n,\beta|_n,f|_n)$.

Then we can fix a coding of $\omega^2\times \aleph_1$ to $\omega\times \aleph_1$ and we are done. $\Box$

Remark: The idea of the proof is to code rank functions on $T(\alpha,\beta)$ with functions in $\omega_1^\omega$.

-----
### Mostowski's Absoluteness
**Theorem 25.4(Mostowski's Absoluteness) If $P$ is a $\boldsymbol{\Sigma}^1_1$ property s.t. $P = p[T]$ with $T$ a tree on $\omega^2$, $M$ is a model such that $T\in M$, $M\models P = p[T]$ and $M\models$ every well founded tree has a rank function, then $P$ is absolute for $M$**

Proof. For $x\in M$:
$x\in P$ iff $T(x)$ is ill-founded iff there is an infinite descending chain iff there is no rank function on $T(x)$. The first is a $\Sigma_1$ property and the second $\Pi_1$. Hence $x\in P$ iff $M\models x\in P$. $\Box$ 

----

### Inductive analysis of (non-well-founded) trees

For an arbitrary tree $T$, we let its well founded part $WF(T)$ be defined as: $$WF(T) = \{u\mid u\not\in T \text{ or there is no }f\in [T] s.t. u\subseteq f\}$$

Then, the rank function $\rho$ would we well defined on $WF(T)$. Set $\rho(x) = \infty$ if $x\not\in WF(T)$. If we are making the tree underlying the rank function explicit, we write $\rho(T,x)$.

**2F.1 (Sierpinski) Let $T$ be a tree on $\omega\times \kappa$ and put $A = p[T]$, $B = \mathcal{N} - A$. For each sequence $u = (\xi_0\dots \xi_{n-1})\in \kappa^\omega$ from $\kappa$ and $\lambda\leq \kappa$, let $$B^\lambda_u = \{\alpha\in \mathcal{N}\mid \rho(T(\alpha), u)\leq \lambda\}$$ Then $$B^0_u = \bigcap_{\xi<\kappa}\{\alpha\mid (\alpha|_{n+1}, u\frown(\xi))\not\in T\}$$ $$B^\lambda_u = \bigcap_{\xi<\kappa}\bigcup_{\zeta<\lambda}B^\zeta_{u\frown (\xi)}$$ and $$B = \bigcup_{\lambda<\kappa^+}B^\lambda_\emptyset = B_\emptyset^\kappa$$**

Proof. We only verify the last equation: $\alpha\in B \text{ iff }T(\alpha)$ is well founded iff $\rho(T(\alpha).\emptyset)$ is defined, and it must be less than $\kappa^+$. $\Box$

Remark: The set $B^\lambda_u$ is the set of irrationals such that the rank of $u$ along $T(\alpha)$ is below $\lambda$. The following theorem shows the usefulness of this definition. 

Notice that $B^0_\emptyset = \bigcap_{\xi<\kappa}\{\alpha\mid (\alpha0, \xi)\not\in T\}$ and hence is $\kappa+1$ Borel. 

It follows that $B^\lambda_u$ is $\kappa+1$ Borel, for each $\lambda,u$ by an induction.

**2F.2 If $A$ is $\kappa$-Suslin, then $$A = \bigcup_{\lambda<\kappa^+}C_\lambda$$ $$A = \bigcap_{\lambda<\kappa^+}D_\lambda$$ for some $\kappa+1$-Borel $C_\lambda,D_\lambda$. In particular, $\boldsymbol{\Sigma}^1_1$ sets are both intersections and unions of $\aleph_1$ Borel sets**

Proof. Let $A = p[T]$ for $T$ a tree on $\omega\times \kappa$, then let $B = \mathcal{N} - A$, $B = \bigcup_{\lambda<\kappa^+}B^\lambda_\emptyset$ by the previous Lemma. 

Hence $$A = \bigcap_{\lambda<\kappa^+} \mathcal{N} - B^\lambda_\emptyset$$
The set $B^\lambda_\emptyset$ is $\kappa+1$ Borel, and hence $A$ is the interdection of $\kappa^+$ many $\kappa+1$ Borel sets.

To establish the intersection part, consider $$E_\lambda = \{\alpha\mid \rho(T(\alpha),\emptyset)\leq \lambda\}\bigcup \{\alpha\mid \exists u ,\rho(T(\alpha),u) = \lambda\} = B^\lambda_\emptyset\cup\bigcup_u(B^\lambda_u - \bigcup_{\xi<\lambda}B^\xi_u)$$
This is a $\kappa+1$ Borel set, so it suffice to show that $B = \bigcap_{\lambda<\kappa^+}E_\lambda$.

If $\alpha\in B$, then $T(\alpha)$ would be well-founded, hence for each $\lambda$, either $\rho(T(\alpha),\emptyset)\leq \lambda$ or $\rho(T(\alpha),\emptyset)> \lambda$, in the latter case there is $u$ s.t. $\rho(T(\alpha),u)= \lambda$, since rank function is surjective for its range.

If $\alpha\in \bigcap_{\lambda<\kappa^+}E_\lambda$, if $\alpha\in B^\lambda_\emptyset$ for some $\lambda$, we are done since then $T(\alpha)$ would be well-founded. If not, then then rank function $\rho_{T(\alpha)}$ would be a function from $T\subseteq \omega\times \kappa$ onto $\kappa^+$, which is impossible. $\Box$

**2F.3 Every $\boldsymbol{\Sigma}^1_2$ set is a union of $\aleph_1$ many Borel sets**

Proof. Let $P(x)\iff \exists^\mathcal{N}\alpha Q(x,\alpha)$, here $Q(x,\alpha)$ is $\boldsymbol{\Pi}^1_1$. 

By the previous theorem we have $P(x)\iff \exists^\mathcal{N}\alpha\exists \xi<\aleph_1 B_\xi(x,\alpha)$, where $B_\xi$ are Borel.

Consider the point set given by $\exists^\mathcal{N},\alpha B_\xi(x,\alpha)$, it is analytic so can again be written as $\exists \zeta<\aleph_1, B_{\xi,\zeta}(x,\alpha)$. 

Hence $P(x)\iff \exists \xi,\zeta<\aleph_1,B_{\xi,\zeta}(x,\alpha)$.  $\Box$

----
### A Proof of Separation Theorem

We apply the theory developed in this section to give a new proof of separation theorem in [[Suslin Sets and the Separation theorems]].

For a given set $B$ whose complement is $\kappa$-Suslin where $\mathcal{N} - B = p[T]$, $T$ is a tree on $\omega\times \kappa$. For each $C\subseteq B$ and $u = (\xi_0\dots \xi_n)\in \omega^{<\omega}\times \kappa^{<\omega}$, we define
$$Index(C,T,u) = sup\{\rho(T(\alpha),(\xi_0\dots \xi_n))\mid \alpha\in C\land \alpha(0) = k_0\dots \alpha(n-1) = k_{n-1}\}$$
The definition is well defined as for each $\alpha\in B$, $T(\alpha)$ exists and obviously all $\rho(T(\alpha),(\xi_0\dots \xi_n))$ are less than $\kappa^+$ as the size of $T(\alpha)$ is $\kappa$.

Now we show that for all $C\subseteq B$ that is $\kappa$-Suslin, $Index(C,T,\emptyset) < \kappa^+$.

Assume for contradiction that $Index(C,T,\emptyset) = \kappa^+$, let $C = p[S]$.

Now $Index(C,T,\emptyset) = sup_\alpha\{\rho(T(\alpha),\emptyset)\mid \alpha\in C\}$. 

$\rho(T(\alpha),\emptyset) = sup_\xi\{\rho(T(\alpha),(\xi))+1\mid (\alpha(0),\xi)\in T\}$ and hence $$Index(C,T,\emptyset) = sup_{\xi,n\in \kappa\times \omega} sup_{\alpha\in C}\{\rho(T(\alpha),(\xi))+1\mid \alpha\in C\land \alpha(0) = n\}$$
Since $\kappa^+$ is regular, there is $n_0,\xi_0$ s.t. $\kappa^+ = sup_{\alpha\in C}\{\rho(T(\alpha),(\xi))+1\mid \alpha\in C\land \alpha(0) = n\}$ i.e. $Index(C,T,(n_0,\xi_0)) = \kappa^+$.

Similarly, $C = \bigcup_{m,\eta\in \omega\times \kappa}p[S_{(m,\eta)}]$ and hence $$Index(C,T,(n_0,\xi_0)) = \kappa^+ =\bigcup_{m,\eta\in \omega\times \kappa} Index(p[S_{(m,\eta)}],T,(n_0,\xi_0))$$
Hence for some $m_0,\eta_0$, $\kappa^+ =Index(p[S_{(m_0,\eta_0)}],T,(n_0,\xi_0)) = sup_\alpha\{\rho(T(\alpha),(\xi_0))\mid \alpha\in p[S_{(m_0,\eta_0)}], \alpha(0) = n_0\}$. Obviously $n_0 = m_0$.

Hence we can get $n_0,n_1\dots, \xi_0,\xi_1\dots \eta_0,\eta_1\dots$ recursively s.t. $$\kappa^+ =Index(p[S_{(m_0,\eta_0\dots n_{k-1},\eta_{k-1})}],T,(n_0,\xi_0\dots n_{k-1},\xi_{k-1}))$$
Let $\alpha = (n_0,n_1\dots)$, but $\alpha\in p[S]\cap p[T]$, which is absurd given $C\subseteq B$. $\Box$

**Separation Theorem**

Proof. Given $A_1,A_2$ $\kappa$-Suslin and disjoint, for $B_1$ the complement of $A_1 = p[T_1]$, we can write it to $$B_1 = \bigcup_{\lambda<\kappa^+}\{\alpha\in B_1\mid \rho(T_1(\alpha),\emptyset) \leq \lambda\}$$
By the result above, for each $C\subseteq B$ that is $\kappa$ Suslin, $C\subseteq \{\alpha\in B_1\mid \rho(T_1(\alpha),\emptyset) \leq \lambda\}$ for some $\lambda$. The latter set is just $B^\lambda_\emptyset$ and is $\kappa+1$ Borel, hence the two sets are separated by $B^\lambda_\emptyset$.