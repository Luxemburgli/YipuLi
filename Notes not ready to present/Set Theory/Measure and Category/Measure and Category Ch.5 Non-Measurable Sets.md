---
title: Measure and Category Ch.5 Non-Measurable Sets
draft: false
tags:
  - "#measure_and_category"
  - "#Measure_Theory"
date:
---
The following construction shows that the real can be partitioned into a null a set and a meagre set, thus a set small in the measure theoretic sense and the other small in the topological sense.

Fix an enumeration of the rationals $\{q_{m}\mid m\in \mathbb{N}\}$. Let $U_{n,m}$ be the following sequence of open intervals, $(q_{m} - \frac{1}{2^{m}n}, q_{m} + \frac{1}{2^{m}n})$. Then $\lambda\left( \bigcup_{m}U_{n,m} \right)\leq \sum_{m}\frac{1}{2^{m-1}n} = \frac{4}{n}$ and hence $\lambda(\bigcap_{n}\bigcup_{m}U_{n,m}) = 0$ and $B = \bigcap_{n}\bigcup_{m}U_{n,m}$. On the other hand, each $\bigcap_{m} U_{n,m}^{c}$ is nowhere dense as $\bigcup_{m}U_{n,m}$ is open dense. Hence the complement of $B$ is meagre.

Now (Assuming AC), let $V$ be the vitali set on $[0,1]$, then $V\cap B$ is lebesgue measurable but without the property of Baire, and $V\cap B^{c}$ has the property of Baire but not Lebesgue measurable. This shows that the measurable sets and Baire sets does not include each other, under AC.

---

## Bernstein Set

Recall from descriptive set theory(to be written) that a set $P\subseteq \mathbb{R}$ is perfect iff $P = P'$, where $P'$ denotes the limit points of $P$. 

A set $B$ is *Berstein* iff $B$ and $B^{c}$ intersects all perfect sets.

In the book the definition a set $B$ is *Berstein* iff $B$ and $B^{c}$ intersects all uncountable closed sets is used, it is quick to see that these are equivalent. If $B$ intersects all uncountable closed sets, then it intersects all perfect sets since perfect sets are closed. If $B$ intersects all perfect sets, then it intersects all uncountable closed sets since every closed set contains a perfect set.

*Theorem 5.3*(AC) There is a Berstein Set.

Proof. Observe there are exactly continuum many Perfect sets, as there are continuum many closed intervals, and continuum many closed sets on the real. Now well order the perfect sets as $\{P_{\alpha}\mid \alpha<\mathfrak{c}\}$, recursively, we pick $p_{\alpha}\neq q_{\alpha}\in P_{\alpha} - \bigcup_{\beta<\alpha}\{p_{\beta},q_{\beta}\}$. This process can always be done. Then $B = \{p_{\alpha}\mid \alpha<\mathfrak{c}\}$ is Berstein. $\Box$

Every Bernstein set is not measurable and not Baire. This is proved by the following observation:

Every measurable subset of $B,B^{c}$ is null. For measurable $A\subseteq B$, every interval contained in $A$ is trivial, as $B^{c}$ intersects with every uncountable closed sets. As $$
\lambda(A) = sup\left\{ \sum I_{n} \mid I_{n}\text{ is a sequence of intervals in }A\right\}$$
It must be equal to 0. 

Every Baire subset of $B,B^{c}$ is meagre. For $A\subseteq B$ that is Baire, write $A=G\cup M$ where $G$ is $G_{\delta}$ and $M$ is meagre. Then $G$ is countable as otherwise it would contain a perfect set, which intersects $B^{c}$. Hence $A$ is meagre.

Then $B,B^{c}$ themselves can not be measurable/ Baire as the real can not be partitioned into two null/meagre sets.

*Theorem 5.5*(AC) Every set with positive outer measure contains a non-measurable subset. Every set of second category has a subset that is not Baire.

Intersect that set with $B$ and $B^{c}$. One of them must fail.

----
## Ulam Matrix

Here we mix the material in Oxtoby and Jech.

*Definition 10.11 in Jech* A *$(\aleph_{0},\aleph_{1})$-Ulam Matrix* is $\{A_{\alpha,n}\mid \alpha<\aleph_{1},n<\omega \}$ s.t. 

1. Each row is mutually disjoint: $A_{\alpha,n}\cap A_{\beta,n} = \emptyset$ for $\alpha\neq \beta$
2. The union of each column is different from $\aleph_{1}$ from an at most countable set.

The existence of an Ulam matrix. For $\alpha\in \aleph_{1}$, let $f_{\alpha}$ be a one-one map from $\{\beta\mid \beta<\alpha\}$ to $\omega$. Let $$
A_{\beta,n} = \{\alpha\mid \beta<\alpha, f_{\alpha}(\beta) = n \}$$

Then $A_{\beta,n}\cap A_{\beta',n} = \emptyset$ as each $f_{\alpha}$ is one-one. The union of each column is $\{\alpha\mid \alpha > \beta\}$, thus cocountable.

The existence of a Ulam Matrix entails that there is no $\mu:\mathcal{P}(\aleph_{1})\to \mathbb{R}$ that is a measure that assigns 0 to each singleton. First observe that each roll contains at most countably many set of positive measure, as elements in a row are disjoint. Then there are uncountable many null sets on each row, given there are only countably many roles, there is a column filled with null sets. Then this is a contradiction as the null set union a countable set is $\aleph_{0}$, but the countable set must be null be assumption.

A more general argument shows that for each successor cardinal $\lambda^{+}$, there exist a $(\lambda,\lambda^{+})$ Ulam Matrix, thus no measure on its powerset. Given we know that the first set with a measure on its powerset must be of regular cardinality (cite Jech), the first set with a measure on its powerset is weakly inacessible.


## Reference