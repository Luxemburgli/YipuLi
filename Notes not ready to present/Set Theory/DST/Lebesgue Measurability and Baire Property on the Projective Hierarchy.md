---
title: Lebesgue Measurability and Baire Property on the Projective Hierarchy
draft: false
tags: 
date:
---
 
In this section, we will prove by an abstract and general argument that all analytic sets are Lebesgue measurable and have Baire property.

For a set $X$, a *$\kappa$-complete-ideal* is an ideal $\mathcal{I}$ that's closed under less than $\kappa$ union: if  $\lambda<\kappa$ and for $\xi<\lambda$, $X_\xi\in \mathcal{I}$, then $\bigcup_{\xi<\lambda}X_\xi$. Note: here I'm following the terminology in Jech.

We say $\mathcal{I}$ is *regular from above relative* to a point set $\Gamma$, if for every $P\subseteq X$ there is $P'\in \Gamma$ s.t. 
1. $P\subseteq P'$
2. If $A\subseteq P'-P$ and $A$ is in $\Gamma$, then $A$ is in $J$.
We say $P$ is $\Gamma$ module $\mathcal{I}$, if $P = $

The meagre ideal and the null ideal both are regular from above relative to the Borel point class: We show the case for Baire property, for $P$, consider $$D(P) = \{x\mid \text{ for all neighbourhood }N \text{ of }x, N\cap P \text{ is meager}\}$$
This is a closed set and $P - D(P)$ is meager since $X$ has countable basis. Let $W$ be a Borel and meager set that $W\supseteq P-D(P)$, Consider $P' = D(P)\cup W$. If $A\subseteq P' - P$ and is Borel, write $A = U\Delta M$, $U$ is open and $M$ meager, $U\subseteq A\cup M\subseteq (P'-P)\cup V\subseteq (D(P)-P)\cup (M\cup W)$. 
This means $N\cap P\subseteq Y$, $N\cap P$ is meager and $N\cap D(P) = \emptyset$. Hence $N\subseteq Y$, this means $N$ is meager, and by Baire category theorem $N$ is emptyset. Hence $A$ is meager. 

**2H.1 For a $\kappa+1$ complete ideal *regular from above relative* to the $\kappa+1$ Borel sets, the sets that are $\kappa+1$ Borel module $\mathcal{I}$ is closed under complementation, $\kappa$ union and Suslin operation $\mathcal{A}^\kappa$.**

**As a consequence, $\kappa$-Suslin sets are are $\kappa+1$ Borel module $\mathcal{I}$**

Proof. 
We first show that if $P_u$ are $\kappa+1$ Borel, for $u\in \kappa^{<\omega}$, then $P = \mathcal{A}^\kappa_uP_u$ is $\kappa+1$ Borel. 

$$P = \mathcal{A}^\kappa_uP_u = \bigcup_f\bigcap_n P_{f|_n}$$

We define $$Q_u = \mathcal{A}^\kappa_vP_{u\frown v}= \bigcup_f\bigcap_n P_{u\frown f|_n}$$

Hence $Q_\emptyset = P$, $Q_u\subseteq P_u$, and $Q_u = \bigcup_{\xi<\kappa}Q_{u\frown (\xi)}$.

Fix $Q_u'\supseteq Q_u$ in $\kappa+1$ Borel s.t.  if $A\subseteq Q_u'-Q_u$ is $\kappa+1$ Borel, then $A\in J$. We may assume that $Q^*_u\subseteq P_u$. 

We show that $Q'_\emptyset - P\subseteq \bigcup_u(Q'_u-\bigcup_{\xi<\kappa}Q'_{u\frown (\xi)})$. If this is true, then as $(Q'_u-\bigcup_{\xi<\kappa}Q'_{u\frown (\xi)})\subseteq (Q'_u-\bigcup_{\xi<\kappa}Q_{u\frown (\xi)}) = (Q'_u-Q_u)$, $(Q'_u-\bigcup_{\xi<\kappa}Q'_{u\frown (\xi)})$ is $\kappa+1$ Borel and thus in $\mathcal{I}$. Given that $Q'_\emptyset - P$ is in $\mathcal{I}$ and thus $P$ is $\kappa+1$ Borel.

Assume for contradiction that $x\in Q'_\emptyset - P$, but for each $u$ in $\kappa^{<\omega}$, either $x\not\in Q'_u$ or for some $\xi<\kappa,x\in Q'_{u\frown (\xi)}$. 

From $Q'_\emptyset$, we take $\xi_1$ s.t. $x\in Q'_{(\xi_1)}$. Recursively, we get some $\xi_1,\xi_2\dots$ s.t. $x\in Q'_{(\xi_1\dots \xi_n)}$. Hence $x\in \bigcap_n Q'_{f|_n}$, where $f= (\xi_1,\xi_2\dots)$. Hence $x\in \bigcap_n P_{f|_n}$ and thus $x\in P$. This is a contradiction.

Now if $P = \mathcal{A}^\kappa_uP_u$, where $P_u\Delta P_u'\in \mathcal{I}$ for some $P_u'$ that is $\kappa+1$ Borel. 
The conclusion follows from the fact that:

$$\mathcal{A}^\kappa_uP_u\Delta \mathcal{A}^\kappa_uP_u'\subseteq \bigcup_u(P_u\Delta P'_u)$$
$\Box$


----
This general fact has the following consequence assuming $add(\mathcal{I}_n) = add(\mathcal{I}_m) =\mathfrak{c}$, all $\kappa$-Suslin sets, where $\kappa<\\mathfrak{c}$ are Lebesgue measurable and Baire.
