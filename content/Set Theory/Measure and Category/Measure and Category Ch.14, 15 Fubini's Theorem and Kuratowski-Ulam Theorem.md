2024-12-03  23:00
Tags: #measure_and_category #Measure_Theory 

The following is the Fubini's thoerem I learnt from measure theoretic probability class:

If $\pi$ is the product measure of $\mu$ and $\nu$ on space $X\times Y$, where both $\mu$ and $\nu$ are $\sigma$ finite, then $$
\int F d\pi = \int \int F d\mu d\nu
$$

It follows that 
**Theorem 14.2 If $E$ is a set on $X\times Y$ of measure zero, then $\{x\mid E_{x}\text{ is null for }\mu\}$ is co-null for $\nu$**
Proof: Let $F$ be the indicator function of $E$.

**Theorem 14.3 If $E$ is a set on $X\times Y$ that is measurable under $\pi$, then $\{x\mid E_{x}\text{ is measurable }\mu\}$ is co-null for $\nu$.**

-----


**Theorem 15.1 Let $X,Y$ be Polish space, if $E$ is a closed nowhere dense set on $X\times Y$, then $\{x\mid E_{x}\text{ is no where dense}\}$ is comeager. Consequently, if $E$ is a meager set, then $\{x\mid E_{x}\text{ is no where dense}\}$ is comeager**

Let $V_{1},V_{2},\dots$ be the a base for $Y$. Let $G = (X\times Y) - E$, which is open dense. Let $$
G_{n} = \{x\mid (x,y)\in G \text{ for some }y\in V_{n}\}
$$If $x\in G_{n}$, then let $(x,y)\in G\cap (X\times V_{n})$, as $G$ is open, there is $(x,y)\in U\times V\subseteq G\cap (X\times V_{n})$ and hence $x\in U\subseteq G_{n}$, which means $G_{n}$ is open.

Moreover, $G_{n}$ is dense open as for $U\subseteq X$ open, $G$ intersects $U\times V_{n}$, hence $G_{n}$ intersects $U$. Hence $\bigcap G_{n}$ is comeager in $X$, for $x\in \bigcap G_{n}$, $E_{x} = Y - G_{x}$ is no where dense as $G_{x}$ is open dense in $Y$.

This finishes the proof. 

By a similar proof, 

**Theorem 15.2 If $E$ is a subset of $X\times Y$ with the property of Baire, then $E_{x}$ has the property of Baire for all $x$ except for a set of first category.**

**Theorem 15.3 If $A\times B$ is a subset of $X\times Y$ that is meager (or null), then $A$ or $B$ is meager (or null).**



## Reference