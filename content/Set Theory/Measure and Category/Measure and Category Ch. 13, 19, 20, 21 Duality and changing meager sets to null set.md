2024-12-08  21:26
Tags: #measure_and_category  #Measure_Theory  #Duality

We start to investigate some transformastions on the reals that relates meager sets and null sets.

---

First, if $F$ is a closed nowhere dense set of $I = [0,1]$, the following homeomorphism takes $F$ to a null set, $G = I - F$ and $m$ is the Lebesgue Measure:
$$
h(x) = \frac{m([0,x]\cap G)}{m(G)}
$$
This is a strictly increasing continuous map ranging over $[0,1]$, hence it is a homeomorphism. To see $h[F]$ is null, write $G$ as a union of disjoint rational intervals, $\bigcup_{i\in \omega}I_{i}$, then $h(\bigcup_{i\in \omega}I_{i}) = I$ and hence the complement of $G$ is null.

----

The same conclusion holds for meager sets, indeed, meagers sets are topologically equivalent to a special kind of null sets:


**Theorem 13.4 A set $A\subseteq \mathbb{R}$ is meager iff there is a homeomorphism $h$ s.t. $h[A]$ is contained in a $\Sigma^{0}_{1}$ null set.**

To show the conclusion, we apply a categorical argument. A categorical argument establish existence of a certain object by showing that objects with the desired property is dense in a metric space. This is somewhat parallel to Erdős' famous probability arguments in combinatorics.

We need the following theorem, which is from [[Measure and Category Ch. 9, 12 Metric spaces]]. 

**Theorem 9.1 For a topologically complete metric space, the complement of a meager set is dense.**

Consider the set $C_{1}$ of continuous maps of $[0,1]$ to $\mathbb{R}$ fixing $0,1$ and $$
H_{n} = \left\{ f\in C[0,1]\mid f(x)\neq f(y) \text{ if }|x-y|\geq \frac{1}{n} \right\}
$$Let $H = C_{1}\cap \bigcap H_{n}$, then $H$ is complete by Alexandroff theorem in [[Measure and Category Ch. 9, 12 Metric spaces]].

**Theorem 13.1 For any set $A$ that is meager in $I = [0,1]$, there is $h\in H$ s.t. $h(A)$ is null**

Let $A = \bigcup A_{n}$ and $$
E_{n,k} = \left\{ h\in H\mid m(h(\overline{A_{n}})) < \frac{1}{k} \right\}
$$
$E_{n,k}$ are open dense and their intersection satisfies the requirements. 


----

## Erdős-Sierpinski Duality

Now we state and prove the Erdős-Sierpinski Duality.

**Theorem 19.5 If $X$ is a set of cardinality $\aleph_{1}$ and $K$ is a class of subsets of $X$ with the following properties:
1.$K$ is a $\sigma$ ideal whose union is $X$,
2.There is a subclass $G$ of $K$ s.t. $G$ is smaller than $\aleph_{1}$ and every member in $K$ is a subset of some member in $G$.
3.The complement of each member of $K$ contains a set of power $\aleph_{1}$ that belongs to $K$.
Then $X$ can be decomposed into $\aleph_{1}$ many disjoint sets $X_{\alpha}$ s.t. $E\in K$ iff $E$ is a subset of countable union of some collection of $X_{\alpha}$.**

Note that under CH, both the meager ideal and the null ideal satisfies the above condition. To verify point 3, for a null set $A$, its complement contains a positive measure closed set, thus by Lemma 5.1 of [[Measure and Category Ch.5 Non-Measurable Sets]] we are done. For a meager set, its complement is a $\Pi_{1}^{0}$ uncountable set, and by Lemma 5.1 we are done.

Proof. Let $G_{\alpha},\alpha<\omega_{1}$ be an enumeration of elements in family $G$. 

Consider $K_{\alpha} = G_{\alpha} -   \bigcup_{\gamma< \alpha} G_{\gamma}$.

The family $B = \{\alpha\in \omega_{1}\mid K_{\alpha} \text{ is uncountable}\}$. $B$ is unbounded in $\omega_{1}$ as for each $\alpha$, $\bigcup_{{\gamma<\alpha}}G_{\gamma}$ is in $K$ and hence there is $G_{\alpha'}$ containing an uncountable set in $K$ that is disjoint from $\bigcup_{{\gamma<\alpha}}H_{\gamma}$ by condition 2 and 3. Enumerate $B$ as $b_{\alpha},\alpha<\omega_{1}$. Let $$
X_{\alpha} = \bigcup_{\gamma\leq b_\alpha} G_{\gamma} - \bigcup_{\gamma<\alpha} G_{b_{\gamma}}
$$The sets $X_{\alpha},\alpha<\omega_{1}$ form a $\aleph_{1}$ family that is disjoint, each belongs to $K$ and of cardinality $\aleph_{1}$ as $X_{\alpha}\supseteq K_{b_{\alpha}}$.

For each $G_{\alpha}$, $G_{\alpha}\subseteq \bigcup_{\gamma\leq b_\delta} G_{\gamma}\subseteq \bigcup_{\alpha\leq \delta} X_{\alpha}$. Here $b_{\delta}$ is some ordinal greater than $\alpha$.

This finishes the proof. 

**Theorem 19.6 If $X$ is a set of cardinality $\aleph_{1}$, $\mathcal{K}$ and $\mathcal{L}$ be two classes satisfying the conditons  of the previous theorem and $X$ can be writen as the disjoint union of a set $K$ in $\mathcal{K}$ and a set $L$ in $\mathcal{L}$, then there is a bijection $f$ of $X$ s.t. $f = f^{-1}$ and $f(E)\in L$ iff $E\in K$.**

Proof We mat assume $G_{0} = K$ in the application of the above theorem and let $X_{\alpha}$ be the decomposition of $X$ in the above theorem for $\mathcal{K}$ and hence $X_{0} = K$. And $Y_{\alpha}$ be the decomposition in the above theorem for $\mathcal{L}$ and $Y_{0} = L$. 

Then we have $L = Y_{0} = \bigcup_{0<\alpha<\omega_{1}}X_{\alpha}$ and $K = X_{0} = \bigcup_{0<\alpha<\omega_{1}}Y_{\alpha}$.

Let $f_{\alpha}$ be a bijection from $X_{\alpha}$ to $Y_{\alpha}$, then let $f$ be $f_{\alpha}$ on $X_{\alpha}$ and $f_{\alpha}^{{-1}}$ on $Y_{\alpha}$, and we are done. 

Consequently, we have 

**Theorem 19.3(CH) there is a bijection $f$ s.t. $f = f^{{-1}}$ and s.t. $N$ is null iff $f(N)$ is meager.**

Indeed, what the proof above relies on is $add(\mathcal{N}) = add(\mathcal{M}) = 2^{{\omega}}$, here $\mathcal{N},\mathcal{M}$ are the null ideal and the meager ideal respectively, and $\kappa = add(\mathcal{M})$ is the least cardinal s.t. $\kappa$ many meager sets unions up to $\mathbb{R}$. Hence, the duality holds under Martin's Axiom. See [[Project on Forcing]] for a reference.

-----

Can the bijection $f$ have additional desirable properties? We show that it can not be measurable or have the property of Baire: 

We say a function $f$ is ES duality if it is a bijection, $f = f^{{-1}}$ and s.t. $N$ is null iff $f(N)$ is meager.

**Proposition No ES duality can be measurable or Baire**

Proof 
This follows from the theorem of Lusin in [[Measure and Category Ch.7 The Theorems of Lusin and Egoroff]]: if $f$ is a Baire function that is a ES duality, then there is $K$ that is comeager s.t. $f|_{K}$ is continuous. Hence $f$ is a homeomorphism from $K$ to $f(K)$, as subspace of $\mathbb{R}$. We may assume $K$ as null, (by considering the decomposition of $\mathbb{R}$ into a null set and a meager set). Then $f(K)$ is meager, but that is impossible: Let $N_{n},n\in \omega$ be a countable collection of no where dense sets that covers $f(K)$, then $N_{n} \cap f(K)$ is nowhere dense and in $f(K)$. Then $f^{-1}(N_{n} \cap f(K))$ would be nowhere dense and in subspace $N_{n}$. No where dense set in a dense subspace (and of course $K$ is a comeager, thus dense subspace) is no where dense in the full space and hence this leads to a contradiction.

----

## Consequences of Duality

All statements in this section relies on set theoretic assumptions more than ZFC.

**Proposition 20.1 (Lusin set, assuming $add(\mathcal{N}) = add(\mathcal{M}) = 2^{{\omega}}$ and AC) Any set $E\subseteq \mathbb{R}$ that is comeager have a subset $N$ of power $2^{{\omega}}$ s.t. every uncountable subset of it is comeager**

Proof Apply theorem 19.5 to obtain a decomposition of $\mathbb{R}$ into $\omega_{1}$ many disjoint sets $X_{\alpha}$ satisfying $E\in K$ iff there is countable many $X_{\alpha}$ whose union contains $E$.

Since $E$ is comeager, its complement is contained in countably many $X_{\alpha}$, this means that $E$ intersects with continuum many $X_{\alpha}$. Pick a single element from each $X_{\alpha}\cap E$ to form $N$, $N$ is of size continuum. Moreover, each uncountable subset of $N$ cannot be covered by countable subset of $X_{\alpha}$, thus not meager. $\Box$

Dually, 

**Proposition 20.1* (Lusin set, assuming $add(\mathcal{N}) = add(\mathcal{M}) = 2^{{\omega}}$ and AC) Any set $E\subseteq \mathbb{R}$ that is of positive measure have a subset $N$ of power $2^{{\omega}}$ s.t. every uncountable subset of it is has positive measure**

As a corollary, there is a subspace of $\mathbb{R}$ s.t. a set is meager iff it is countable and comeager iff it is uncountable. (Join $N$ from proposition 20.1 with a countable dense set.)

Moreover, it also follows that a comeager set contains continuum many disjoint comeager subsets.

----

Can a ES duality $f$ be a Borel isomorphism? i.e. an map that takes a Borel set to a Borel set. If so, then $f$ would satisfy the property that $E$ is Baire iff $f(E)$ is Lebesgue measurable, as Baire sets are precisely the sets in the sigma algebra containing Borel sets and meager sets, and the dual statement is true for Lebesgue measurable. 

But indeed there could not be a bijection s.t. $f = f^{-1}$ and $E$ is Baire iff $f(E)$ is Lebesgue measurable. 

**Proposition there is no bijection $f$ s.t. $f = f^{-1}$ and $E$ is Baire iff $f(E)$ is Lebesgue measurable.**

Proof. Suppose for contradiction that $f$ is such a map. Let $I = (0,1)$ and $E = f^{-1}(I)$. Let $x_{1},x_{2}\dots$ be a countable dense subset of $E$ (say $\mathbb{Q}\cap E$), and $I_{i}$ be an open interval containing $x_{i}$ s.t. $$
m(f(I_{i})\cap I)< \frac{1}{2^{i+1}}
$$Let $G = \bigcup I_{i}$ and $E\subseteq \overline{G}$
Notice $E\subseteq (G\cap E)\cup (\overline{G}-G)$ and hence$$
I = f(E) \subseteq f(G\cap E)\cup f(\overline{G}-G) \subseteq\bigcup (f(I_{i})\cap I) \cup f(\overline{G} - G)
$$ As $\overline{G} - G$ is no where dense, $f(\overline{G} - G)$ is null, since a set if null iff every subset of it is Lebesgue measurable by theorem 5.5 in [[Measure and Category Ch.5 Non-Measurable Sets]]. $\Box$

Hence $m(I)\leq \sum_{i} \frac{1}{2^{i+1}} = \frac{1}{2}$. This is a contradiction. 

**This leaves questions to be answered:**
1. What is the arithmetic complexity of the function in theorem 19.3? It can't be Borel.
2. What if $f$ is weakened to a one-direction map?

-----

We end a discussion by the interesting parallel of Kolmogoroff zero-one law in the category theory. See [[Kolmogorov 0-1 Law]] for comparision.

**Theorem 21.4 Let $X_{i}, i\in \omega$ be a series of topological spaces and $X$ be the product space. If $E$ is a Baire tail set then $E$ is either meager or comeager**


## Reference