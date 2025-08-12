---
title: Ch. 12 of Ralf Schindler
draft: true
tags: 
date:
---
 
## Problem 12.1
Let $(x_i,i<\theta)$ be a sequence of different elements of $\mathcal{P}(\omega)$, we proceed as hinted and take $U$ to be a measure on $\omega_1$ by theorem 12.18. By Problem 10.3 a, $\omega_1$ is measurable in $L[U,(x_i,i<\theta)]$, thus $\theta\leq |\mathcal{P}(\omega)|^{L[x]}<\omega_1$ since $L[U]$ is a model of ZFC. $\Box$

---
## Problem 12.2
Failure of AD trivially implies the conclusion. So we assume AD. 

Consider the following game: player I plays an ordinal $\alpha\in \omega_1$ and player II plays ordinal $n_m\in \omega$ for $m\in \omega$ many times. II wins iff the consequence of the game $x$ satisfies $||x|| = \alpha$. 

Then I does not have a winning strategy, but a winning strategy for II would be an injection $\omega_1\to \omega^\omega$, contradicting the conclusion of problem 12.1. $\Box$

---
## Problem 12.3 
For each formula without parameters $\varphi(x,y,z)$, the set $$\{a\in \omega^\omega\mid \exists \alpha(x\in a\iff \varphi(x,\alpha,A))\}$$
must be countable as otherwise by replacement this induces an injection $\omega_1\to \omega^\omega$, contradicting 12.1. Thus since there are only countably many formulas, by AC$_\omega$ on reals, OD$_{\{A\}}\cap \omega^\omega$ is countable.

Let $f:\omega^\omega\to \omega^\omega$ be in OD$_{\omega^\omega\cup\{A\}}$, then there is formula $\varphi$ s.t. there is $\alpha_i\in Ord$, $z_j\in \omega^\omega$,  for all $x,y\in \omega^\omega$ $$f(x) = y\iff \varphi(x,y, z_1\dots z_n, A,\alpha_1\dots \alpha_m)$$
Let $z$ be $\oplus_{1\leq i\leq n} z_i$, then $$a\in f(z)\iff \exists y (a\in y\land \varphi'(y, z, A,\alpha_1\dots \alpha_m))$$
for some proper $\varphi'$ constructed from $\varphi$. This shows that  $f(z)\in$OD$_{\{z,A\}}$. 

For the final conclusion, just take $A_x = \omega^\omega\setminus \mathsf{OD}_{\{x,A\}}$. $\Box$

---
## Problem 12.4
Let $f$ be given by $x\mapsto Th_{\Sigma_1}(x^\sharp)$. The function is ordinal definable as $$n\in Th_{\Sigma_1}(x^\sharp)\iff L_{\aleph_\omega}[x]\models \varphi_n$$And $Th_{\Sigma_1}(x^\sharp)$ cannot be in $L[x]$ by indefinability of truth.

Since $\mathbb{C}$ is contained in $L_{\kappa_0}[x]$ where $\kappa_0$ is the first Silver indiscernible and $L[x]$ deem $\kappa_0$ as inaccessible, all the dense set in $L[x]$ of $\mathbb{C}$ must already be contained in $x^\sharp$ as $\mathcal{P}(\mathbb{C})^{x^\sharp} = \mathcal{P}(\mathbb{C})^{L[x]}$. Thus for each $x\in \omega^\omega$ the dense sets in $L[x]$ must be countable.

Now by $AC_\omega$, there is $\Phi$ be a function s.t. $\Phi(n,x)$ is the $n$-th dense set in $L[x]$ and $\{\Phi(n,x)\mid n\in \omega\}$ enumerates the dense sets in $L[x]$. Fix a canonical enumeration of conditions in $\mathbb{C} = \{s_n\mid n\in \omega\}$. Now we run a generic filter existence argument (Lemma 6.4) in a definable way:

We enumerate $\mathcal{D}_x = \{\Phi(n,x)\mid n\in \omega\}$ and at each step we add the smallest condition in $\mathbb{C}$ that is in $\Phi(n,x)$ to the filter base. Let the consequent generic filter be $G_x$. 

Then $x\mapsto G_x$ is the desired function. $\Box$

Remark: It seems the countability of $\mathbb{C}$ is crucial.

---
## Problem 12.5 
(a) As hinted, consider the game $G_{Wadge}(A,B)$ where I plays $x_n$ and II plays $y_n$ and I wins iff $x\in B\iff y\in A$.

If $\tau$ is a winning strategy for I then $x\in B\iff e(\tau* x)\in A$, here $e:\omega^\omega\to \omega^\omega$ is the map taking a real and forming a new real from the even indices. Since the operation $\tau *$ is continuous and taking the even is continuous, this shows that $A\leq_{Wedge}B$.
If $\sigma$ is a winning strategy for II then $o(\sigma * y)\not\in A\iff y\in B$ where $o$ is taking the odd indices. $\Box$

 Identity function witnesses reflexivity and composition of continuous functions entail transitivity.

$\emptyset$ and a set $\emptyset\subsetneq X\subsetneq \omega$ witnesses the failure of symmetry.

(b)We proceed as hinted. Let $A_0>_{Wadge}A_1>_{Wadge}\dots$, we show that I has a winning strategy for both $G_{Wadge}(A_{n+1},A_n)$ and $G_{Wadge}(\omega^\omega - A_{n+1},A_n)$ for all $n$. Since otherwise by the argument in (a) and determinacy, $A_{n+1}\leq_{Wadge}A_n$, contrary to assumption. Let $\sigma^0_n,\sigma^1_n$ be the respective winning strategy for the two games.

For $z\in 2^\omega$, we define $x^z_n$ recursively by $$x^z_n(2m+2)= \sigma_n^{z(n)}(x^z_n(0),x^z_{n+1}(0),\dots x^z_{n+1}(2m) , x^z_{n+1}(2m))$$ and $$x^z_n(2m+1) = x^z_{n+1}(2m)$$ for all $n$. 

The picture visualizes what's going on:
![[Hamkins-3.jpg]]

If follows that $x^z_n = \sigma^{z(n)}_n*x^z_{n+1}$. And it is easy to check that $\{z\in 2^\omega\mid x^z_0\in A_0\}$ is a flip set and by Problem 8.3 is not Lebesgue measurable, thus contradicting Theorem 12.13. $\Box$

(c) The constant function is an injection from $\omega^\omega$ to the continuous functions. 
Pick a countable dense set $D$ in $\mathbb{R}$, then a continuous function $f$ is determined by $f|_D$, since the set $\{f:D\to \omega^\omega\}\cong \{f:D\times \omega\to \omega\}\cong \{f:\omega\to \omega\}$, there is injection from the continuous functions to $\omega^\omega$. 
By Cantor-Berstein, there is a bijection from $x\in \omega^\omega$ to $f_x$ continuous. Consider the set $J(A):= \{x\mid f_x(x)\not\in A\}$, we show that $A<_{Wadge}J(A)$.

First $A\not \geq_{Wadge}J(A)$ as if there is continuous $g$ s.t. for all $x$, $g(x)\in A\iff x\in J(A)$, say $g = f_x$ then $f_x(x)\in A\iff x\in J(A)\iff f_x(x)\not\in A$, a contradiction.

Hence by (a) $A \leq_{Wadge}J(A)$ and we are done. $\Box$

(d) $\leq$: Let $x\mapsto g_x$ as the bijection given above. For $A$ s.t. its Wedge rank is $\alpha$, then $f:x\mapsto ||g_x^{-1}(A)||_{<_{Wadge}}$ is a surjection $\omega^\omega\to \alpha+1$.

$\geq$: If $f:\omega^\omega\to \alpha$ is a surjection, as hinted, inductively define
$A_{\nu}: = J(\{x\oplus y\mid f(x)<\nu,y\in A_{f(x)}\})$ for limit $\nu$ and $A_{\alpha+1}: = J(A_\alpha)$

It suffice to show that if $\nu<\xi$, then $A_\nu<_{Wadge }A_\xi$, this is by an induction and the successor case is easy. If $\xi$ is limit, $A_\nu\leq_{Wadge}\{x\oplus y\mid f(x)<\xi,y\in A_{f(x)}\}<_{Wadge}A_\xi$. 

---

## Problem 12.6
(a) Consider the simple game where I plays a real $x$ and II plays a real $y$, II wins iff $y\in A_x$. Then the winning strategy for $II$ is such a choice function.

(b) We proceed as hinted. Let $$A\in U\iff \text{I has a winning strategy in }G(\{f\in (\omega^\omega)^\omega\mid ran(f)\in A\})$$
This $U$ of course is upward closed and contains $[\omega^\omega]^{\aleph_0}$. For any $A$, I has a winning strategy in $G(\{f\mid ran(f)\in A\})\iff G(\{f\mid ran(f)\in A^c\})$. By $AD_\mathbb{R}$ $U$ thus contains exactly one of an element and its complement. If there is $A_n,n\in \omega$ s.t. $A_n\in U$

To show that $U$ is countably complete, let $A_n,n\in \omega$ be a sequence of sets in $U$, by (a) we may have $\tau_n$ winning strategy for I in game $G(\{f\mid ran(f)\in A_n\})$. We consider the following winning strategy $\tau$ for I in $G(\{f\mid ran(f)\in \bigcap_nA_n\})$. 

Let $(-,-):\omega^2\to \omega$ be a bijection such that $(n,m)<(n,m+1)$. At step $(n,m+1)$ for I, given previous plays $n_i$, I plays what $\tau_n$ yields on the play $$(n_{(n,0)}, \oplus_{(n,0)<i<(n,1)}n_i ,\dots ,n_{(n,m)},\oplus_{(n,m)<i<(n,m+1)}n_i )$$
i.e. I plays $\tau_n$ viewing the previous plays intermediate $(n,i),(n,i+1)$ as a single move by his opponent at move $i$.

Then since $\tau_n$ wins I $G(\{f\mid ran(f)\in A_n\})$, $\tau * x\in \{f\mid ran(f)\in A_n\}$ for all $n$ and thus $\tau$ is a winning strategy for I. 

$\{a\in [\omega^\omega]^{\aleph_0}\mid x\in a\}\in U$ is obvious: I wins by playing $x$ at his first move.

Finally, let $A_x\in U$ for $x\in \omega^\omega$. Let $\tau_x$ be a winning strategy for the game on $A_x$. The strategy is similar to countable closedness. For each existing play $x_n$, I makes sure to apply $\tau_{x_n}$ infinitely often in the future, regarding intermediate plays between two application of $\tau_{x_n}$ as a single move by his opponent. $\Box$

---
## Problem 12.7
(a) First we observe that for each continuous function $f$ is $OD_{\omega^\omega}$, as the bijection developed in Problem (c) is $OD_{\omega^\omega}$. 

Next, for arbitrary $\alpha = ||A||_{<_{Wadge}}<\Theta_0$, pick $f:\omega^\omega\to \alpha+1$ in $OD_{\omega^\omega}$ and we define $A_\nu,\nu\leq\alpha$ as in Problem 12.5. Then the sequence $||A_\alpha||\geq \alpha$ and thus there is $g$ continuous $A = g^{-1}(A_\alpha)$. Thus $$x\in A\iff g(x)\in A_\alpha$$
This means that $A\in OD_{\omega^\omega}$ $\Box$

(b) This is the exact same argument parametrized by $B$ $\Box$.

---
## Problem 12.8
Assume AD$_\mathbb{R}$, we argue that for every $B\subseteq \omega^\omega$, $\mathcal{P}(\omega^\omega)\not\subseteq \mathsf{HOD}_{\{B\}\cup\omega^\omega}$. Since by Problem 12.3 there is non-empty $(A_x,x\in \omega^\omega)\in \mathsf{HOD}_{\{B\}\cup\omega^\omega}$ without choice function. But working in $V$, by AD$_\mathbb{R}$ and Problem 12.6 there is a choice function $\omega^\omega\to \omega^\omega$ in $V$, since being a choice function for a given family of sets is absolute, hence $\mathcal{P}(\omega^\omega)\not\subseteq \mathsf{HOD}_{\{B\}\cup\omega^\omega}$. By Problem 12.7 this means that the length of the Solovay sequence is not a successor.

Since assuming AD, the model $\mathsf{HOD}_{\{B\}\cup\omega^\omega}$ is a model of AD there is non-empty $(A_x,x\in \omega^\omega)\in \mathsf{HOD}_{\{B\}\cup\omega^\omega}$ without choice function, by Problem 12.6 it is not a model of AD$_\mathbb{R}$, this concludes the proof.

---
## Problem 12.10
(a) Let $\alpha$ be an ordinal countable in $L$ s.t. $J_\alpha\models ZFC^-$. Work in $L$ and since $L$ knows $J_\alpha$ is countable, $L$ can add a Cohen generic real into $J_\alpha$ to form $M$. Then $Ord(M) = \alpha$ and $(M\cap L\cap \mathcal{P}(\omega))\setminus J_\alpha\neq \emptyset$.

(b) Assume for contradiction that $\alpha$ is not an $L$-cardinal, then there is $\kappa$ an $L$-cardinal s.t. $\kappa<\alpha<(\kappa^+)^L$. Pick $f:\kappa\to J_\alpha$ in $L$ surjective, define $E\subseteq \kappa^2$ s.t. $\xi_1 E\xi_2$ iff $f(\xi_1)\in f(\xi_2)$ where $E\in L$. By the assumption $\mathcal{P}(\kappa)\cap L\subseteq M$, $E\in M$ and we apply Mostowski Collapse in $M$ to $\kappa,E$ and obtain that $J_\alpha\in M$. This contradicts the fact that $\alpha = M\cap Ord$. $\Box$

---
## Problem 12.11
Since $\alpha\geq \kappa+\omega$ is $x$-admissible, by Problem 5.28 $J_\alpha[x]$ does transitive collapse correctly. Hence the $\kappa$th iterate of $0^\sharp$ exists in $J_\alpha[x]$, as well as the $\kappa+1$th iterate of $0^\sharp$, call them $\mathcal{M}_\kappa,\mathcal{M}_{\kappa+1}$ respectively. Since $\kappa\in \mathcal{M}_\kappa$, $\mathcal{P}(\kappa)$ is the same in $\mathcal{M}_{L}$ as in $L$. Hence $\mathcal{P}(\kappa)^L\subseteq J_\alpha[x]$.

That $\alpha$ is an $L$ cardinal follows directly from Problem 12.10 (b). $\Box$

---
## Problem 12.12      
We argue as in the proof of theorem 10.11. Consider the similar game $G_s$ but instead played on $[\omega]^{<\omega}$ and $\omega$ repectively. Similarly, we show that:

**Claim 12.12.1 I does not have a winning strategy for $G_t$ in $M$.**
Proof. We work in $M$. Say $\sigma$ is a winning strategy for I. Notice that by how the game is played, a winning strategy of I would not depend on his previous move, and hence $\sigma$ can be viewed as a function taking input from $[\omega]^{<\omega}$. As $\sigma(t \frown s)\in U$ for all $s\in [\omega]^{<\omega}$, by selectivity of $U$, by problem 9.3 (b), we thus have $Y\in U$ s.t. for all strictly increasing $s\in \omega^{<\omega}$, if $ran(s)\subseteq Y$ then $s(n)\in \sigma(t\frown s|n)$. We say that $Y$ selects the system $\sigma(t\frown s)$. We pick $(t',Y')\leq (t,Y\setminus max(t))$ where $(t',Y')\in D$. We have $t' - t\subseteq Y$. 

We argue that by playing as $II$ the moves $t'-t$ in the first few rounds, he defeats the strategy $\sigma$. Let $t'- t = \{n_m\dots n_l\}$. As $\sigma$ would respond to the play $t\frown \{n_m\dots n_{m+i}\}$ with $\sigma(t\frown \{n_m\dots n_{m+i}\})$, thus $n_{m+i+1} = t'(m+i+1) = (t'-t)(i+1)\in \sigma(t\frown \{n_m\dots n_{m+i}\})$ and hence II's next move is still legit. Argue inductively in the above way, II can play $t'-t$ in the first $l$ rounds and since $(t',Y')\in D$, she wins the game. $\Box$

Hence, as $G_t$ is a closed game, $II$ has a winning strategy in $M$. This is a winning strategy in $V$ also as all the plays legit by I in $V$ are already in $M$. Let $\tau$ be such a winning strategy.

Similarly, we have that 
**Claim 12.12.2 If $t$ is realizable, then there is $Y^t_s\in U$ s.t. for all $\lambda\in Y^t_s$ there is $X$ s.t. playing $\lambda,X$ as the respective next move of II,I, $X\in U$ and II played according to $\tau$.**
The aim of this claim is to enable us to design a sequence of plays by II so that the consequence lands in $G$, while the plays respects $\tau$ and thus the consequence lands in $D$.

Associate $Z_s$ to $s$ if $(s,Z_s)\in D$ and otherwise $Z_s = \omega$. Let $Y^*_t$ be the the intersection of $Y^t_s,s\subseteq t$. Finally let $W_0$ select $Z_s$ and $W_1$ select $Y^*_t$. Then the set $W_0\cap W_1$ and thus agrees with $x$ after some $m$. Say $x = \{x_n,n\in \omega\}$ and $W_0\cap W_1\supseteq \{x_m,x_{m+1}\dots\}$. Then in the game $G_{s}$ where $s = \{x_0\dots x_m\}$, any initial $\{x_0,\dots ,x_n\}$ is realizable. Thus by the same argument as in the book, there is $)\{x_0\dots x_n\},Z_{x|_n})\in D\cap G$. $\Box$

---
## Problem 12.13

**Claim 12.13.1 Mathias forcing has pure decision: For any formula $\varphi(\vec{\tau})$ and condition $(s,A)$, there is $B\subseteq A$ s.t. $(s,B)$ decides $\varphi(\vec{\tau})$**

See for instance Jech Lemma 26.34. I don't see a proof in the style of Claim 10.7. Though we have that for selective ultrafilter $U$ the following property holds: for each $n,k$ and $F:[\omega]^n\to k$ there is $X\in U$ homogeneous. However, this does not seem strong enough to allow us to run the proof of Claim 10.7.

We show that if $A$ is Solovay over $M[s]$ then $A$ is Ramsey for $s\in Ord^\omega$. Say $$x\in A\iff V[s][x]\models \varphi(x)$$
Consider Mathias forcing $\mathbb{M}$ in $M[s]$ and pick $(\emptyset , X)$ deciding $\varphi(\dot{x})$ by Claim 12.13.1, here $\dot{x}$ is the canonical name of the generic real. Say $(\emptyset,X)\Vdash \varphi(\dot{x})$. As $\kappa$ is still inaccessible in $V[s]$, there is $\mathbb{M}$ generic $G$ over $V[s]$.  we argue that $[\dot{x}_G]^\omega\subseteq A$, for arbitrary $y\subseteq \dot{x}_G$, $y\subseteq X$ and the filter corresponding to $y$ contains $(\emptyset,X)$, thus $V[s][y]\models\varphi(y)$, i.e. $y\in A$. $\Box$ 