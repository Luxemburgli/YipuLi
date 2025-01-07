---
title: Measure and Category Ch.6 Banach Mazur Game (and Revisiting Baire's Category Theorem)
draft: false
tags:
  - "#measure_and_category"
  - "#Game"
  - "#Topology"
date:
---
*Theorem*(Baire's Category Theorem) The complement of countable union of nowhere dense set is dense.

Proof. The strategy is to be one-step-a-time pick a closed interval disjoint from the nowhere dense set. So that the final intersection is not empty by completeness of the real, yet it avoids all the nowhere dense sets.

In the following discussion by closed interval we mean nontrivial interval $[a,b]$ where $a\neq b$.

Let $U = \bigcup_{n}N_{n}$, where $N_{n}$ is nowhere dense. For arbitrary open interval $I$, pick closed interval $I_{1}\subset I - N_{0}$ and so on. Then $\bigcap_{n}I_{n}$ is not empty and is in $I$.

The Banach Mazur Game is the following game: Player (A) and (B) play on a closed interval $I$ and $A\subset I$. (A) picks closed $I_{2k}\subset I_{2k-1}$ and (B) picks closed $I_{2k+1}\subset I_{2k}$. Then (A) wins if $\bigcap_{n}I_{n}$ intersects $A$, otherwise (B) wins.

Clearly if (B) has a winning strategy if $A$ is meagre: he simply avoids one nowhere dense set at a time each time he chooses, as in the proof of Baire's Category Theorem.

*Theorem 6.1* (B) has a winning strategy iff $A$ is meagre.
Proof.

Instead of copying the proof on the Oxtoby book, I actually wonder whether the following is a more simple proof. The proof relies on the fact that instead of allowed to play irrational intervals, the two players are only allowed to play rational intervals. This Banach Mazur game is just same as the previous one.

If $x\in A$, then $x$ cannot be forced my (A), which means that there should be a stage where the strategy of (B) tells him to avoid $x$. Let $t$ be arbitrary legal sequence of intervals already played and is of even length ((B)'s turn), meaning 

1. $t_{n}\subset t_{n-1}$
2. The strategy $\tau$ applied on $t|_{2k-1}$ actually produces $t_{2k}$.

Then there should be a sequence of move $t$ s.t. whatever (A) chooses to move later on, (B) can move to avoid $x$. i.e.
$$
a\in \bigcup_{t\text{ a sequence of move}}\bigcap_{I\subset t_{2n}}\tau(t,I)^{c}
$$

The set $\bigcap_{I\subset t_{2n}}\tau(t,I)$ should be nowhere dense in as its complement is $\bigcup_{I\subset t_{2n}}\tau(t,I)$, which is open dense in $t_{2n}$ (for whatever interval I, $\tau(t,I)$ is in that interval!). 

Now that given our assumption that the rational intervals are the only legal moves, $A$ is meager as it is a contained in a countable union of nowhere dense sets.


Now, by a strategy stealing argument, 

*Theorem 6.2* (A) has a winning strategy iff $A^{c}\cap I_{0}$ is meagre for some closed interval $I_{0}\subset I$. i.e. $A$ is comeagre with respect to some closed interval.

---

## The Banach Mazur Game in the Baire Space.

In the Baire space, the Banach Mazure game is actually 

Indeed, 

*Theorem 6.1* (B) has a winning strategy iff $A$ is meagre.
Proof.


## Reference