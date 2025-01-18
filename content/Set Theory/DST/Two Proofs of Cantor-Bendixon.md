---
title: Two Proofs of Cantor-Bendixon
draft: false
tags: 
date:
---
**2A.1 (Cantor-Bendixon)In a Polish space, if $C$ is a uncountable closed set, then it can be uniquely decomposed into a perfect set $P$ and a countable set $S$ s.t. $C = P\cup S$.**

Proof 1. Let $x\in C$ be an condensation point of $C$ if for each neighbourhood $N$ of $x$, $N\cap C$ is uncountable.

Let $P = \{x\in C\mid x \textit{ is a condensation point.}\}$, $S = C\setminus P$.

$S$ is countable: Fix a countable base of the space. For each $x\in S$, pick an basic neighbourhood s.t. $N_x\cap C$ is countable. Since $S\subseteq \bigcup_{x\in S}N_x\cap C$, $S$ is countable.

$P$ is perfect: First show that $P$ is closed. If $x$ is limit point of $P$, then it is a limit of $C$ and hence $x\in C$. For arbitrary neighbourhood $N$ of $x$ and $x'\in N\cap P$, $N$ is also a neighbourhood of $x'$ and hence $N\cap C$ is uncountable. Hence $x\in P$. Next show that $P$ has no isolated point. For $x\in P$ and $N$ a neighbourhood of $x$, $N\cap C$ is uncountable, but $N\cap P$ has at most countably many points less than $N\cap C$, hence it is not empty.

Uniqueness: Let $C = P'\cup S'$ satisfies the above conditions. If $x\in P'$, let $N$ be a neighbourhood of $x$, pick another neighbourhood $N_1$ s.t. $\overline{N_1}\subseteq N$. Then $\overline{N_1\cap P'}\subseteq N\cap P'$ and is perfect. Hence $\overline{N_1\cap P'}$ is uncountable and hence $x\in P$. If $y\in S'$, then there is neighbourhood $N$ of $y$ s.t. $N\cap P' = \emptyset$. Hence $N\cap A = N\cap S'$, $N\cap A$ is countable and hence $y\in S$.$\Box$

----

Proof 2. The second proof consists of taking iterative derivatives of the closed set.

For a set $A$, let the derivative of $A$ be $A' = \{x\mid x\text{ is a limit point of }A\}$.

Consider $C_0 = C$, $C_{\xi+1} = C_\xi'$ and $C_\lambda = \bigcap_{\xi<\lambda}C_\xi$.

Since $C_0\supseteq C_1\supseteq \dots\supseteq C_\xi\supseteq \dots$, there is an ordinal $\alpha$ s.t $C_\alpha = C_\beta$ for $\beta>\alpha$. $C_\alpha$ would be closed and perfect as $C_\alpha = C_\alpha'$.

Let $U_k$ be an enumeration of basic open sets. Now if $x\in C - C_\alpha$, then $x\in C_\beta - C_\beta'$ for some unique $\beta<\alpha$ and let $k_x$ be the least $U_k$ s.t. $x\in U_k$ and $U_k$ is disjoint from $C_\beta - \{x\}$. If $\beta\leq \gamma$, $x\neq y$, then $k_x,k_y$ would be distinct. Hence $C-C_\alpha$ injects into the natural numbers by $x\mapsto k_x$ and hence $C - C_\alpha$ is countable. $\Box$

The above proof also shows that the isolated point of any set is countable.