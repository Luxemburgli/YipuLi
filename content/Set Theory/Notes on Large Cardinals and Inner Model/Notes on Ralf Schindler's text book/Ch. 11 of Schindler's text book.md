---
title: Ch. 11 of Ralf Schindler
draft: false
tags: 
date:
---
I currently wish to postpone Solidity and Box principle till later. As I haven't finished section 11.3, the solutions here are incomplete.

---
## Problem 11.1
Step 1: By GCH, show that there is a class function $\varphi: Ord\to V$ satisfying $\varphi|_{\aleph_{\alpha+1}}$ is a surjection from $\aleph_{\alpha+1}\to \mathcal{P}(\aleph_\alpha)$.

This is because under GCH, by an inductive argument, for $\alpha\geq \omega$, $|V_\alpha| = \aleph_\alpha$. 

Step 2: Code the function as a class of ordinals. Consider the following relation corresponding to the class function, $R(\alpha,\beta)\iff \beta\in \varphi(\alpha)$. Let $\Gamma$ be the canonical pairing function $Ord^2\to Ord$ and let $E = \Gamma[R]$. For limit $\gamma$, the canonical pairing satisfy $\Gamma[\gamma^2] = \gamma$.

We argue that $L[E] = V$. We verify that for $X\subseteq Ord$, $X\in V$ iff $X\in L[E]$, and by Problem 5.12 the conclusion follows.
For a set of ordinals $X\in V$, let $X\in \mathcal{P}(\aleph_\alpha)$, then there is $\gamma\in \aleph_{\alpha+1}$ s.t. $\varphi(\gamma) = X$. i.e. $\{\beta\mid R(\gamma,\beta) \} = X$. Now take $\delta$ s.t. $E\cap \delta\supseteq \Gamma[R|_{\aleph_{\alpha+1}}]$, since $\Gamma$ is definable in $L[E]$, and $E\cap \delta\in L[E]$, $R|_{\aleph_{\alpha+1}}\in L[E]$ and hence $X = \{\beta\mid R|_{\aleph_{\alpha+1}}(\alpha,\beta) \}\in L[E]$. This shows that $L[E] = V$.

Next we show that $L[E]$ is acceptable. Let us pick $X\subseteq \mathcal{P}(\delta)$, say $|\delta| = \aleph_\alpha$. By assumption there is $\gamma<\aleph_{\alpha+1}$ s.t. $\varphi(\gamma) = X$, i.e. $\{\beta< \aleph_{\alpha+1}\mid R(\gamma,\beta) \} = X$. We notice that $\{\gamma\}\times X\subseteq \aleph_{\alpha+1}^2$, moreover, since $|\{\gamma\}\times X|<\aleph_{\alpha+1}$ and $\aleph_{\alpha+1}$ is regular, there is some $\beta<\aleph_{\alpha+1}$ s.t. $\beta\geq \sup \Gamma[\{\gamma\}\times X]$. Thus 
$X$ can be recovered from in $E\cap \beta$, i.e. contained in $J_{\beta+1}[E]$. Hence, if $X\in J_{\gamma+\omega}[E]\setminus J_{\gamma}[E]$ for some $\gamma$, $\gamma\leq \beta$ and thus there is surjection from $\delta$ to $\gamma$. $\Box$


---
## Problem 11.2
Failure of acceptability: Say $U$ is a $<\kappa$ complete ultrafilter on $\kappa$, we observe that $L_\kappa[U] = L_\kappa$, as for all $\delta<\kappa$, $x\in L_\delta$, $x\cap U = \emptyset$.

On the other hand, consider the set of countable Silver indiscernibles $I_{\omega_1}^{L[U]}\subseteq \omega_1^{L[U]}$, which exists in $L[U]$ by Lemma 10.31 and Corollary 10.44. Since it can not be in $L_\kappa$, it exists in $L_{\gamma+\omega}[U]\setminus L_{\gamma}[U]$ for some $\gamma\geq \kappa$. But of course there is no surjection $\omega_1^{L[U]}\to \gamma$ in $L[U]$.

Remark: Equivalently, we can work with a subset of $\omega$ that codes the minimal $0$ mouse. But we cannot work with the set of terms of the Silver indiscernibles over $L_{\aleph_\omega^{L[U]}}$, see [this link](https://math.stackexchange.com/questions/1888063/why-is-0-sharp-not-definable-in-zfc) for clarification.

Weak acceptablility:

By the proof of problem 10.5, we know that $L[U]\models o(<_{L[U]}|_{\mathcal{P}(\rho)}) = |\rho|^+$. Assuming $(\mathcal{P}(\rho)\cap J_{\alpha+\omega}[U])J_\alpha[U]\neq \emptyset$, $J_{\alpha+\omega}[U]\models o(<_{L[U]}|_{\mathcal{P}(\rho)^{J_\alpha[U]}}) < |\rho|^+$, and this entails the conclusion. 

---
 
## Problem 11.3
The statement of the Lemma is wrong, according to errata, the additional hypothesis $\forall x\in U' \exists y\in U', x\in y$ is needed.

(a) For a $\Sigma_1$ formula $\exists x \varphi(x,\vec{y})$, the $U$ to $U'$ direction is easy. If $U'\models \exists x \varphi(x,\pi(\vec{b}))$ for some $\vec{b}\in {U'}^{|\vec{b}|}$, say $U'\models  \varphi(a,\pi(\vec{b}))$, take $a_0\in U'$ s.t. $a\in a_0$ by cofinalness there is $a'\in U$ s.t. $a\in a_0\subseteq \pi(a')$. Hence $U'\models \exists x\in \pi(a') \varphi(x,\pi(\vec{b}))$, by absoluteness of $\Delta_0$ formulas, $U\models x\in a' \varphi(x,\vec{b})$ and  the conclusion follows.

(b) Say $\varphi(\vec{x}) = \forall y_1\exists y_2\psi(y_1,y_2,\vec{x})$. For $\vec{b}\in {U'}^{|\vec{b}|}$, if $U'\models \forall y_1\exists y_2\psi(y_1,y_2,\pi(\vec{b}))$, then for all $a\in U$, $U'\models \exists y_2\psi(\pi(a),y_2,\pi(\vec{b}))$ and by $\Sigma_1$ elementariness, $U\models \exists y_2\psi(a,y_2,\vec{b})$ and hence the conclusion holds.

(c) Say $\varphi(\vec{x}) = \forall v_1\exists v_2\supseteq v_1\psi(v_2,\vec{x})$, assume $U\models \forall v_1\exists v_2\supseteq v_1\psi(v_2,\vec{b})$. For all $a\in U'$, let $a\subseteq \pi(a')$ for $a'\in U$ and thus there is $a''\in U$ s.t. $U\models \psi(a'',\vec{b})$. Hence $U\models \psi(\pi(a''), \pi(\vec{b}))$ by upward closedness of $\Sigma_1$ formula, clearly $a\subseteq \pi(a'')$. This concludes the proof.

---
## Problem 11.4

**Claim 11.4.1 Strengthening Claim 11.17. Under the assumption of the problem, if $\varphi(x_1)$ is a $\Sigma_{n+1}$-formula, for $\bar{x_i} = h_{\bar{M}}(n_i,(\vec{\bar{z_i}}, \bar{p}))$ for $0<i\leq l$ and $n_i<\omega$ and $\bar{z_i}\in [\rho_1(M)]^{<\omega}$. Then let $x_i = h_M(n_i,(\vec{z_i},p))$ where $\vec{z_i} = \pi(\vec{\bar{z_i}})$, then**
$$\bar{M}\models \varphi(\bar{x_1},\dots ,\bar{x_l})\iff M\models \varphi(x_1,\dots ,x_l)$$

Proof. I can't find the reference of function $e$ on page 230. But the existence of such $e$ is standard $S^m_n$ argument in recursion theory. Hence we have the existence of function $e$ s.t. for $\Sigma_1$ formula $\varphi_n$, $$\bar{M}\models \varphi_n(h_{\bar{M}}(n_1,(\vec{\bar{z_1}}, \bar{p})),\dots ,h_{\bar{M}}(n_l,(\vec{\bar{z}}_{l+n}, \bar{p})))\iff \bar{M}\models \varphi_{e(n)}(\vec{\bar{z_1}}\dots \vec{\bar{z}}_{l+n}, \bar{p})$$
And similarly for $M$.

For simplicity of notation, we assume that $n$ is odd, we have that $$\begin{align}
\bar{M}\models \varphi(\bar{x_1},\dots ,\bar{x_l}) &\iff\bar{M}\models \exists \bar{z}_{l+1}\dots  \forall \bar{z}_{l+n}\in [\rho_1(\bar{M})]^{<\omega},\varphi_n(h_{\bar{M}}(n_1,(\vec{\bar{z_1}}, \bar{p})),\dots ,h_{\bar{M}}(n_l,(\vec{\bar{z}}_{l+n}, \bar{p}))) \\
&\iff \exists \bar{z}_{l+1}\dots  \forall \bar{z}_{l+n}\in [\rho_1(\bar{M})]^{<\omega}, \bar{M}\models \varphi_{e(n)}(\vec{\bar{z_1}},\dots ,\vec{\bar{z}}_{l+n}, \bar{p})\tag{*}\\
& \iff \bar{M}^{\bar{p}}\models \exists \bar{z}_{l+1}\dots  \forall \bar{z}_{l+n} A^{\bar{p}}_{\bar{M}}(e(n), (\vec{\bar{z_1}},\dots ,\vec{\bar{z}}_{l+n}))
\end{align}$$
Notice here in ($*$) we use the fact that $\bar{p}\in R_{\bar{M}}$. And hence by assumption the same holds for $M$.

Hence by $\Sigma_n$ elementarity of $\pi:\bar{M}^{\bar{p}}\to M^{p}$ the claim is proved. $\Box$

With the claim, we proceed as the proof of Lemma 11.16 and the conslusion follows. $\Box$

----
## Problem 11.5
We the case where ${\kappa^+}^M = \rho_n(M)$ is trivial. Hence we assume $\leq$: Since ${\kappa^+}^M< \rho_n(M)$.

----
## Problem 11.7
First we show that $cf^{V[G]}(\omega_2^V) = \omega$. Similar to the definition in Problem 10.24, we say $s$ is a stem of $T$ if $s$ is the longest node in $T$ s.t. for all $t\in T$, $t\supseteq s$ or $t\subseteq s$.

Since the set $$D_n = \{T\in \mathbb{N}\mid T\text{ has stem }s\text{ longer than }n\}, n\in \omega$$
$$E_{\alpha} = \{T\in \mathbb{N}\mid \text{the stem of }T, s \text{contains}\beta\geq \alpha\}, \alpha\in \omega_2$$
are dense, hence the $\bigcup\{s\mid s\text{ is the stem of }T, T\in G\}$ is a cofinal in $\omega_2$.

Next we show that Namba forcing preserves $\omega_1$. We every  function $\tau:\omega\to \omega_1$ in $V[G]$ is bounded. If $T\Vdash \tau:\omega\to \omega_1$, then we recursively choose $(t_s,T_s,\alpha_s\mid s\in \omega_2^{<\omega})$ s.t. 
1. $T_\emptyset = \emptyset$, $t_\emptyset$
2. $t_s\in T_s$, $s$ is part of the stem of $T_s$, $T_s\Vdash ran(\tau|_{lh(s)})\subseteq \alpha_n$ for $\alpha_n<\omega_1$.
3. $\{t_{s\frown \xi}\mid \xi<\omega_2\}\subseteq T_s$ is a family of extensions of $t_s$ of the same length of size $\aleph_2$.
For $\alpha<\omega_1$, define $$T^\alpha = \bigcap\{\bigcup\{T_s\mid h(s) = n, \alpha_s<\alpha\}\mid n<\omega\}$$

For a tree $T$, define $$T' = \{t\in T\mid \text{there are }\omega_2\text{ many nodes below }t\}$$
Similar to the Cantor Bendixon argument, define $T_{\alpha+1} = T_\alpha'$ and $T_{\lambda} = \bigcap_{\alpha<\lambda}T_\alpha$, $T^* = \bigcap_{\alpha<\omega_3}T_\alpha$. Let $||t||_T = \alpha$ if $t\in T_{\alpha+1} - T_\alpha$, if $t\in T^*$, set $||t||_T = \infty$.

We argue that there is some $\alpha<\omega_1$ s.t. $||\emptyset||_{T^\alpha} = \infty$, otherwise consider the string $c_0: \omega\mapsto 0$, pick $\alpha>\alpha|_{c_0|_n}$ for all $n$. Notice that $T_{c_0|_n}\subseteq T^\alpha$ for all $n$, and thus by construction of $T_s$, $||t_{c_0|_{n+1}}||_{T^\alpha}<||t_{c_0|_n}||_{T^\alpha}$, a contradiction to the well-foundedness of ordinals.

Given there is some $\alpha<\omega_1$ s.t. $||\emptyset||_{T^\alpha} = \infty$, consider $(T^\alpha)^*$, it is a perfect tree, $(T^\alpha)^*\leq T$ and $(T^\alpha)^*\Vdash ran(\tau)\subseteq \alpha$. This shows that $V[G]\models$ $\tau_G$ is bounded in $\omega_1$. 

Finally, we show that the constraint in Jensen's covering lemma cannot be left out. First observe that $|\omega_2^V|^{V[G]} = \omega_1^{V[G]} = \omega_1^V$ as $\omega_2^V<\aleph_\omega\leq \omega_2^{V[G]}$, which is the first uncountable cardinal in $V[G]$ with cofinality $\omega$. This shows that $\omega_V$ is not a cardinal in $V[G]$ and thus $|\omega_2^V|^{V[G]} = \omega_1^{V[G]} = \omega_1^V$. 

Apply Namba forcing to $L$. Since Namba forcing preserves $\omega_1$, a set of ordinals is countable in $L$ iff it is countable in $L[G]$.
Consider the set $\aleph_2^L$ in $L[G]$, take $f$ as its cofinal sequence of type omega, since $L$ thinks that there is no countable sequence cofinal in $\aleph^L_2$, any cover $Y\in L$, $Y\supseteq \{f(n)\mid n\in \omega\}$ would be uncontable in $L$. Thus it would be uncountable in $L[G]$. 

For statement (3), consider in $L[G]$ the club set $C = \{f\in [\omega^L_2]^\omega\mid f\text{ is unbounded in }\omega^L_2\}$. This set does not intersect $[\omega^L_2]^\omega\cap L$
$\Box$

---
## Problem 11.8
This is essentially Claim 10.16.1 in [[Ch. 10 of Schindler's text book]].

Alternatively, suppose there is forcing $\mathbb{P}$ that adds $0^\sharp$, then $Con(ZFC)\to Con(ZFC+0^\sharp\text{ exists })$, which implies $Con(ZFC)\to Con(ZFC+\text{ inaccessible cardinals }\text{ exists })$, this is absurd as $ZFC$ and $ZFC$+inaccessible cardinal is not equiconsistent. $\Box$

---
## Problem 11.9


---
## Problem 11.11

Following the hint of problem 19.12 in Jech, Let $\kappa = \omega_1$.
Since $(\kappa^+)^L\leq \omega_2$, $cf((\kappa^+)^L) \leq (\omega_2)$. But as both $\omega_1$ and $\omega_2$ are singular, $cf(\omega_2) = cf((\kappa^+)^L) = \omega$. We pick $X,Y$ two cofinal set of size $\omega$ for $\kappa = \omega_1$ and $(\kappa^+)^L$ respectively. 

Consider the model $L[X,Y]$, which is a model of ZFC and $\omega_1$ is a singular cardinal in $L[X,Y]$ while $(\kappa^+)^L$ is not a cardinal since models of ZFC thinks successor cardinals are regular. By corollary 11.60 $0^\sharp$ exists in $L[X,Y]$, thus in $V$. 

---
