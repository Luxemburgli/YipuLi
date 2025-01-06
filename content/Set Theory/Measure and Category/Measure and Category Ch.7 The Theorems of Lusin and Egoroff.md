2024-11-14  20:14
Tags: #measure_and_category #Measure_Theory 

We say a function $f:$ $\mathbb{R} \to \mathbb{R}$ is measurable iff each basic open set is reflected to a measurable set, and $f$ is Baire iff each open set is reflected to a set with the property of Baire.

**Theorem 8.1 A real valued function on $\mathbb{R}$ is Baire iff it's restriction on a comeager set is continuous**

Left to Right: Let $U_{1},U_{2}\dots$ be an enumeration of a base of the reals, then $f^{{-1}}(U_{i})$ is Baire and hence can be written as $G_{i}\Delta P_{i}$ where $G_{i}$ is open and $P_{i}$ is nowhere dense. Then $\bigcup_{i\in \omega}P_{i}$ is meager, then for the function $g = f|_{\mathbb{R} - \bigcup_{i\in \omega}P_{i}}$, it is continuous as for each $x\in \mathbb{R}$ and open set around it, there is $U_{k}$ as a neighbourhood around $x$ s.t. the reflection of $U_{k}$ along $g$ is $G_{k}$, hence $g$ is continous.

The other direction is easy.

Remark: This is a bit different from $f$ is continuous on a comeagre set. Consider the following example illustrating the difference of continuous on a set and the restriction on a set is continuous: Let $f = I_{x\geq 0}$, the indicator function of $x\geq 0$, then $f$ is not continuous on $x\geq 0$, but its restriction on $x\geq 0$ is constant $1$, which is continuous.

----
On the other hand, it is not necessary that a measurable function has a restriction to a co-null set that is continuous. 

Consider again  $U_{1},U_{2}\dots$ , the enumeration of open rational intervals. We inductively define a sequence of pairwise disjoint closed nowhere dense set with positive measure s.t. $N_{2n}\cup N_{2n-1}\subseteq U_{n}$. 

Given $N_{2n}$ defined, we consider the set $\bigcup_{i\leq 2n} N_{i}$, $U_{n} - \bigcup_{i\leq 2n} N_{i}$ is open and we take two disjoint closed nowhere dense sets with positive measure from it. Then let $A = \bigcup_{n\in \mathbb{N}}N_{2n}$, $A$ and $\mathbb{R} - A$ has positive measure and in every interval. Let $f$ be the indicator function of $A$, hence the restriction of $f$ to any co-null set would have domain interseting $A$, making it nowhere continuous.

**Theorem 8.2 (Lusin) A real valued function $f$ is measurable iff for each $\epsilon>0$ there is an open set $E$ with measure less than $\epsilon$ s.t. the restriction of $f$ on $\mathbb{R} - E$ is continuous**

The right to left direction, for each $n$, $f^{{-1}}(U) - G_{n}\subseteq E_{n}$ for some open set $G_{n}$ and $E_{n}$ a set of measure less than $\frac{1}{n}$. Hence $f^{-1}(U) - \bigcup_{n\in \mathbb{N}}G_{n}$ is null, hence $f^{-1}(U)$ is measurable.

For the other direction, let $U_{1},U_{2}\dots$ be an enumeration of rational intervals. Let $F_{i}\subseteq f^{-1}(U_{i}) \subseteq G_{i}$ and $\mu(G_{i} - F_{i})\leq \frac{\epsilon}{2^{i}}$. Then $\bigcup_{i}(G_{i} - F_{i})$ has measure less than $\epsilon$. $f$ restricted to $\mathbb{R} - E$ is continuous, as $g^{-1}(U_{i}) = F_{i}$ if $g$ is the restriction.

------



## Reference