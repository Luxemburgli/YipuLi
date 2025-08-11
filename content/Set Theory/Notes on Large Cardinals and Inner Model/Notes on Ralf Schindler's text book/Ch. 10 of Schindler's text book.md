---
title: Ch. 10 of Ralf Schindler
draft: false
tags: 
date:
---
## Problem 10.1

**Claim 10.1.1 Let $\pi:\bar{\mathcal{M}} \to \mathcal{M}$ be elementary and $\pi(\bar{U}) = U$. If a putative iteration of $\mathcal{M}$ of length $\alpha+1$ is an iteration, then a putative iteration of $\bar{\mathcal{M}}$ of length $\alpha+1$ is an iteration.**

Proof of claim: We recursively define, for $\xi\leq\alpha + 1$, $\pi_\xi: \bar{\mathcal{M}}_\xi\to \mathcal{M}_\xi$ by setting $\pi_{\xi+1} ([f]_{\bar{U}_\xi})=[\pi_\xi(f)]_{U_\xi}$, $\pi_\lambda$ where $\lambda$ is a limit to be the direct limit map given by $\pi_\lambda(\bar{i}_{\xi,\lambda}(f)) = i_{\xi,\lambda}\cdot \pi_\xi(f)$.

Then the final map $\pi_{\alpha+1}: \bar{\mathcal{M}}_{\alpha+1}\to \mathcal{M}_{\alpha+1}$ witness the wellfoundedness of $\bar{\mathcal{M}}_{\alpha+1}$. $\Box$


Let $\mathcal{T}$ be a putative iteration of $\mathcal{M}$ of length $\alpha + 1$. We pick $\theta$ large enough, $X$ a ctm, and $\pi:X\to V_\theta$ that is elementary w.r.p the language with predicate $\in, \mathcal{T}, \mathcal{M}$. Let $\pi(\bar{\mathcal{T}}) = \mathcal{T}$, $\pi(\bar{\mathcal{M}}) = \mathcal{M}$. 
Then $$X\models \bar{\mathcal{T}}\text{ is a putative iteration of }\bar{\mathcal{M}}$$
This is an absolute statement and hence $\bar{\mathcal{T}}\text{ is a putative iteration of }\bar{\mathcal{M}}$, as $\bar{\mathcal{T}}\in X$, its length is less than $\omega_1$. By Claim 10.1.1 and the assumption in the problem we have $\bar{\mathcal{T}}\text{ is an iteration of }\bar{\mathcal{M}}$, i.e. $\bar{\mathcal{M}}_{\alpha+1}$ is well-founded. Hence $X\models \bar{\mathcal{T}}\text{ is an iteration of }\bar{\mathcal{M}}$. By elementariness and passing to $V_\theta$, $\mathcal{T}\text{ is an iteration of }\mathcal{M}$. This concludes the proof that $\mathcal{M}$ is iterable.

cf. Lemma 2.4, Lemma 2.5 in John Steel's note on Itreated Ultrapowers.

---

## Problem 10.2

(a) We show by an induction on $\alpha\in Ord$ that $$M_\alpha = \{\pi_{0,\alpha}(f)(a)\mid a\in \{\kappa_\beta\mid \beta<\alpha\}^{<\omega}, f:[\kappa]^{|a|}\to M_0\}$$
The base case $\alpha = 0$ is trivial.

Induction step for successor $\alpha+1$: 
$$\begin{align}M_{\alpha+1} &= Ult(M_\alpha, U_\alpha) \\ 
&=\{\pi^{M_\alpha}_{U_\alpha}(g)(\kappa_\alpha)\mid g\in M_\alpha^{\kappa_\alpha}\}\\
& = \text{by IH},  \{\pi_{\alpha,\alpha+1}(\pi_{0,\alpha}(f)(a))(\kappa_\alpha)\mid a\in \{\kappa_\beta\mid \beta<\alpha\}^{<\omega}, f: [\kappa]^{|a|}\to M_0^{\kappa}\}\\
& = \{\pi_{0,\alpha+1}(f')(a\cup\{\kappa_\alpha\})\mid a\in \{\kappa_\beta\mid \beta<\alpha\}^{<\omega}, f': [\kappa]^{|a|+1}\to M_0\}
\end{align}$$
The final equation holds as $\pi_{\alpha,\alpha+1}(a) = (a)$ for $a\subseteq \{\kappa_\beta\mid \beta<\alpha\}$. This equation shows the $\subseteq$ direction of the desired result. The other side is obvious.

Induction step for limit $\lambda$: $$\begin{align}
x\in M_\lambda &\iff \exists \alpha<\lambda, \exists y\in M_\alpha, x = \pi_{\alpha,\lambda}(y) \\
& \iff \exists \alpha<\lambda, \exists a\in \{\kappa_\beta\mid \beta<\alpha\}^{<\omega},\exists f:[\kappa]^{|a|}\to M_0^{\kappa}, (x = \pi_{\alpha,\lambda}(\pi_{0,\alpha}(f)(a)))\\
& \iff \exists \alpha<\lambda, \exists a\in \{\kappa_\beta\mid \beta<\alpha\}^{<\omega},\exists f:[\kappa]^{|a|}\to M_0^{\kappa},(x = \pi_{0,\lambda}(f)(a))
\end{align}$$
This concludes the proof.

This exercise shows that $M_{\alpha} = h_M(ran(\pi_{0,\alpha}), \{\kappa_\beta\mid \beta<\alpha\})$.

(b) As $\kappa_\alpha,\alpha\in Ord$ satisfy $\kappa_\alpha<\kappa_\beta$ if $\alpha<\beta$, it is unbounded in $Ord$.

For arbitrary sequence $(\kappa_{\alpha_\mu}, \mu<\lambda)$ where $\lambda$ is a limit, we show that $\bigcup_{\mu<\lambda} \kappa_{\alpha_\mu} = \kappa_{\bigcup_{\mu<\lambda}\alpha_\mu}$. Let $\theta = \bigcup_{\mu<\lambda}\alpha_\mu$.

$\leq$ is immediate. For the other side, if $\gamma<\kappa_\theta$, then $\gamma = \pi_{\alpha_\mu,\theta}(\gamma')$ for some $\mu<\lambda$ and  by the construction of direct limit. $\gamma'<\kappa_{\alpha_\mu}$ by elementarily. It follows that $\gamma' = \gamma$ and hence $\gamma<\kappa_{\alpha_\mu}$.

(c) For limit ordinal $\lambda$, for arbitrary $X\in \mathcal{\kappa_\lambda}\cap M_\lambda$, we have that there is some $\alpha<\lambda$ s.t. $\pi_{\alpha,\lambda}(Y) = X$ and $Y\in U_\alpha$. We show that for all $\beta$ s.t. $\alpha\leq \beta <\lambda$, we have $\kappa_\beta\in X$. Then $Z : = \pi_{\alpha,\beta}(Y)\in U_\beta$. Hence $\kappa_\beta\in \pi_{\beta,\beta+1}(Z)\subseteq \pi(\beta,\gamma)(Z) = X$ by normality of $U_\beta$. Hence $\kappa_\beta\in X$.

The statement is false for successor ordinals, as in this case the statement we are supposed to prove reduces to $\mathcal{M}_{\alpha+1}\models U_{\alpha+1}$ is principal.

(d) The statement contains an error, $\mu$ should be $\lambda$. 

To see the statement makes sense, it follows from the proof of (b) that $\kappa_\lambda = \lim_{\beta<\lambda}\kappa_\beta$. We have $\kappa_\beta\leq |\beta|\cdot 2^\kappa < \lambda$ by a function counting argument, and hence $\kappa_\lambda  = \lim_{\beta<\lambda}\kappa_\beta\leq \lambda$. This means $\kappa_\lambda = \lambda$.

The fact that $U_\lambda\subseteq F_\lambda\cap \mathcal{M}_\lambda$ follows from (c) and (b). The otherside follows as $U_\lambda$ is an ultrafilter in $\mathcal{M}_\lambda$ $\Box$

---
## Problem 10.3
(a) $L[U] = L[\bar{U}]$ is standard exercise. To verify $L[U]\models \bar{U}$ is a measure on $\kappa$, 

$\kappa\in \bar{U}$ as $\kappa\in L[U]$ and $\kappa\in U$.

If $X_1,X_2\in \bar{U} = L[U]\cap U$, then $X_1\cap X_2\in L[U]\cap U$. Upward closure and the property for complement is similarly verified.

If $(X_\alpha,\alpha<\mu)\in L[U]$ for some $\mu<\kappa$ and $X_\alpha\in L[U]\cap U$, then $\bigcap_{\alpha<\mu} X_\alpha\in U$ and $\bigcap_{\alpha<\mu} X_\alpha\in L[U]$, hence $\bigcap_{\alpha<\mu}\in \bar{U}$.

(b) Same as 10.2 (d), $\mu$ should be $\lambda$. By elementarity $\mathcal{M}_\lambda\models V = L[U_\lambda]$. Hence $\mathcal{M}_\lambda = L[U_\lambda]$. As by 10.2 (d) $U_\lambda= F_\lambda^{L[U]}\cap \mathcal{M}_\lambda = F_\lambda\cap \mathcal{M}_\lambda$, $\mathcal{M}_\lambda = L[F_\lambda]$.

---
## Problem 10.4

(a) Let $\lambda>2^\kappa$ be regular, we show that there is $\delta$ s.t. $\mathcal{M}_\lambda = J_\beta[F_\lambda]$. First $\mathcal{M}_\lambda\models V = L[\pi_{0,\lambda}(U)]$, it must be of the form $J_\beta[\pi_{0,\lambda}(U)]$ for some limit $\beta$. 

Next, notice that problem 10.2 also works for iterable set model $\mathcal{M}$. Hence we have $\pi_{0,\lambda}(U) = F_\lambda\cap \mathcal{M}_\lambda$ and hence $\mathcal{M}_\lambda = J_\beta[F_\lambda]$.

Hence two $L^\mu$ mouse can be coiterated as we can take $\lambda>max\{2^\kappa,2^\lambda\}$ where $\kappa, \lambda$ are the respective largest cardinal in $\mathcal{M},\mathcal{N}$.

(b) Like in the proof of Claim 10.33, we construct the putative iteration of length $\gamma+1$, $(\mathcal{N}_\alpha,\theta_{\alpha,\beta}\mid \alpha\leq\beta\leq\gamma+1)$ of $\mathcal{N}_0 = J_{\bar{\alpha}}[\bar{U}]$ and construct the family of elementary embeddings $\sigma_{\alpha},\alpha\leq\gamma+1$ into the iteration $(\mathcal{M}_\alpha,\pi_{\alpha,\beta}\mid \alpha\leq\beta\leq\gamma+1)$.

For successor step, we set $\sigma_{\alpha+1}(\theta_{\alpha,\alpha+1}(f)(\lambda_\alpha)) = \pi_{\alpha,\alpha+1}(\sigma_{\alpha}(f))(\kappa_\alpha)$. By the fact that $\mathcal{N}_0$ is a model of $ZFC^-$, this map can be elementary instead of just $\Sigma_0$ elementary. The limit case can be defined by commutativity of the diagram.

---
## Problem 10.5
Let $U$ be a normal measure on $\kappa$. We work in this inner model. 


First we show the case for $\lambda<\kappa$:
It suffice to show that for each $\lambda$ and $X\in \mathcal{P}(\lambda)$, $$|\{Y\in \mathcal{P}(\lambda)\mid Y\subseteq X\land Y<_{L[U]}X\}|\leq \lambda$$
Then we would have $o(<_{L[U]}|_{\mathcal{P}(\lambda)^2})\leq \lambda^+$, this validates the conclusion.

Take $J_\alpha[U]$ large enough s.t. $\kappa, \lambda\in J_\alpha[U]$.

Consider the Skolem closure of $\lambda\cup \{\lambda\}$ w.r.t. the language with constant $c_X$ for $X$, and collapse it to form $J_\beta[U']$ by condensation. Then $\pi:J_\beta[U']\to J_\alpha[U]$ is elementary, $U' = \pi^{-1}[U]$, $|J_\beta[U']| = \lambda$, $\pi|_{\lambda+1} = id$ and $X = \pi(X')$ for some $X'\in J_\beta[U']$, we notice that actually $X = \pi(X)$ and thus $X\in J_\beta[U']$ as $\pi|_{\lambda+1} = id$.

Now we want to show that, assuming for $x,y\subseteq \lambda$, $x<_{L[U']}y$ iff $x<_{L[U]}y$, it holds that $\{Y\in \mathcal{P}(\lambda)\mid Y\subseteq X\land Y<_{L[U]}X\}\subseteq J_\beta[U']$, which finishes the proof. If $Y<_{L[U]}X$, there is $\gamma$ s.t. $J_\alpha[U]\models rank_{<_{L[U]}}(Y) = \gamma$, then $J_\beta[U']\models \exists Y'\subseteq X, rank_{<_{L[U']}}(Y') = \gamma$. By elementarity and the fact that $\pi|_{\lambda+1} = id$, such $Y'$ is $Y$ and hence $Y\in J_\beta[U']$.

Finally, we verify that for $x,y\subseteq \lambda$, $x<_{L[U']}y$ iff $x<_{L[U]}y$. By theorem 10.3 and Problem 10.4(b), $\mathcal{N}_0 = J_{\beta}[U']$ and $\mathcal{M}_0 = J_{\alpha}[U]$ are $L^\mu$ mice and hence by 10.4(a) they can be co-iterated, i.e. there is $\gamma,\gamma'$ s.t. $\mathcal{M}_\lambda = J_\beta[F_\lambda], \mathcal{N}_\lambda =J_{\beta'}[F_\lambda]$. And hence $\mathcal{M}_0 \models x<_{L[U']}y$ iff $J_{\beta'}[F_\lambda],J_{\beta}[F_\lambda]\models x<_{L[F_\lambda]}y$ iff $\mathcal{N}_0 \models  x<_{L[U]}y$ by elementariness and the fact that elements under $\lambda$ are fixed under iteration.

**Remark**: In general, when we collapse the structure $(N,N\cap U)$, we can't make sure that the collapsed structure is $(N',N'\cap U)$, i.e. not necessarily elementary to $(L[U],U)$ for the predicate. Hence the condensation does not apply and though $N'$ would be some $J_\beta[U']$, we have no idea about whether $U' = U\cap N'$. But in the case when $U$ is a normal measure on $\kappa$, coiteration argument fits the gap.  

The case when $\lambda\geq\kappa$ is similar to Godel's argument that $V = L$ implies $GCH$, for $x\subseteq \lambda$, the fact that $\lambda>\kappa$ means the collapsed structure of $(N = h_{L[U]}(\lambda\cup \{x,U\}), U\cap N)$ to be elementary at the predicate as the collapsing map would be constant on $\kappa<\lambda$. Hence the condensation applies, this is not true for $\lambda< \kappa$.

---
## Problem 10.6

The proof of Claim 10.22 is standard.

For 10.21 (d), we prove a more general theorem
**Claim 10.6.1 If $M_0,M_1\models ZFC^-$ and $j:M_0\to M_1$ is $\Sigma_1$ elementary and cofinal in $M_1$, then actually $j$ is elementary**

Proof of claim cf. Prop 5.1 in Kanamori: We show by an induction on the Levy hierarchy of formulas. Suppose $M_0\prec_{\Sigma_n} M_1$, we show $M_0\prec_{\Sigma_{n+1}}M_1$. It suffice to show that for $\Pi_1$ formula $\psi(x,\vec{y})$ and $\vec{a}\in M_0$, if $M_1\models \exists x\psi(x,j(\vec{a}))$ then there is $b\in M_0$ s.t. $M_0\models \psi(b,\vec{a})$.

By cofinalness, we find $c\in M_0$ s.t. $M_1\models \exists x\in j(c)\psi(x,j(\vec{a}))$, by replacement (this is where $M_1\models ZFC^-$ is used), $\exists x\in j(c)\psi(x,j(\vec{a}))$ is equivalent to a $\Pi_n$ formula an hence $M_0\models \exists x\in c\psi(x,\vec{a})$. We are done. $\Box$

I don't really understand why in the text book, the language in (c) and (d) is different. 

---
## Problem 10.7

We say a real $x$ codes a structure $(M,\in, A)$ iff for $o(x):n\mapsto 2n+1$ and $e(x):n\mapsto 2n$ $\pi(\omega,E_{o(x)},A_{e(x)})\cong (M,\in,A)$ where $E_{o(x)}$ denotes the standard coding of $o(x)$ as a well-founded relation and $n\in A_{e(x)}\iff e(x)(n)\neq 0$. $\pi$ is the transitive collapse.

**Claim 10.12.1 The following relation is $\Delta^1_2$: $$(x,y)\in A\iff x\text{ codes a premouse and its iteration up to }||y||.$$ In the sense that for all $n$, $(x)_n:m\mapsto x(\Gamma(n,m))$ codes a premouse and**$$n_1E_y n_2\iff (x)_{n_2}\text{ codes an ultrapower of }(x)_{n_1}$$
Proof. First we show that $x$ codes a premouse is $\Pi^1_1$. $x$ codes a premouse iff $o(x)\in \mathsf{WF}$ and $(\omega,E_{o(x)})\models ZFC^- + V = L+\text{there is a largest cardinal}$ and say $n_\kappa$ is the largest cardinal in $(\omega,E_{o(x)}$ $(\omega,E_{o(x)},U_{e(x)})\models U_{e(x)} \text{ is a non-trivial normal } <\kappa\text{ complete ultrafilter on }\kappa$. 

$(\omega,E_{o(x)})\models ZFC^- + V = L + \text{there is a largest cardinal}$ is arithmetical since the relation $(\omega,E_{o(x)})\models \varphi(n_1\dots n_m)$ is arithmetical. To analyze $(\omega,E_{o(x)},U_{e(x)})\models U_{e(x)} \text{ is a non-trivial normal } <\kappa\text{ complete ultrafilter on }\kappa$, for instance $(\omega,E_{o(x)},U_{e(x)})\models U_{e(x)} \text{ is }<\kappa\text{ complete.}$ iff $$\forall n (\pi_x(n)\in \pi_x(n_\kappa)\to \forall X\in [\omega]^\omega(\forall m\in X(m\in U_{e(x)}\land \pi_x(m)\in \pi_x(n))\to \exists l\in U_{e(x)}(\bigcap\pi_x[X] = \pi_x(l)))$$
Where $\pi_x$ is the Mostowski collapse. This is a $\Pi^1_1$ property, for the Mostowski collapse part see for instance Jech Proof of Lemma 25.25.

Next consider the following relation:$$(x,y)\in Ult\iff y,x\text{  both code premice and } y\text{ codes the ultrapower of }x$$
First we notice the ultrapower equivalence relation for $x$ is given by, for $n_1,n_2$ that are functions with domain $\omega$ in $(\omega,E_{o(x)})$ collapsed, $$n_1\equiv n_2\iff \exists m(m\in U_{e(x)}\land \forall l(\pi(l)\in \pi(m)\to \pi(n_1)(\pi(l))\in \pi(n_2)(\pi(l)))) \tag{*}$$

We have $y$ codes the ultrapower of $x$ iff there is $\equiv_x\subseteq \omega^2,f\in \omega^\omega$ s.t. $\equiv_x$ is an equivalent relation satisfying $*$, $f$ respects $\equiv_x$ and is bijective $\omega\to \{n\in\omega\mid \pi_x(n)\text{ is a function with domain }\omega\} / \equiv_x$, $$n_1E_{e(y)}n_2\iff \exists m(m\in U_{e(x)}\land \forall l(\pi(l)\in \pi(m)\to \pi(n_1)(\pi(l))\in \pi(n_2)(\pi(l))))$$
and 
$$n_1\in U_{e(y)}\iff m(m\in U_{e(x)}\land \forall l(\pi(l)\in \pi(m)\to l\in U_{e(x)}))$$
And hence $Ult$ is a $\Sigma^1_1$ relation.

Hence, let $(x)_n:m\mapsto x(\Gamma(n,m))$,  $(x,y)\in A\iff \forall n_1,n_2(n_2 \text{ is the }E_y \text{ successor of }n_1\to ((x)_{n_1},(x)_{n_2})\in Ult)$, and thus is $\Delta^1_2$. Moreover, the shows that the section of $A$ along $y$ is also $\Delta^1_2$. $\Box$ 

Thus $x$ codes a $z$-mouse is a $\Pi^1_2(z)$ property.


---
## Problem 10.8
Let $x^\sharp = (J_\alpha[x],U)$, then $\omega^\omega\cap x^\sharp = \omega^\omega\cap L[x]$ by a condensation argument as in Problem 10.10. Hence by Corollary 7.21 the conclusion follows.

---
## Problem 10.9
**Claim 10.9.1 For $J_\alpha[x],J_\beta[x]$, if $j:J_{\alpha}[x]\to J_{\beta}[x]$ is an elementary embedding which has critical point $\gamma<|\alpha|$, then $x^\sharp$ exists.**
Proof of claim: Let $U$ be the ultrafilter defined on $\gamma$ with $j$. Since $\gamma<|\alpha|$, $J_\alpha[x]$ and $L[x]$ agrees on $\mathcal{P}(\gamma)$ and hence $L[x]$ also thinks $U$ is a $\gamma$ complete ultrafilter on $\gamma$. It suffice to show that $Ult(L[x],U)$ is well-founded. Thus $Ult(L[x],U) = L[x]$ and the ultrapower map is an non trivial elementary embedding from $L[x]$ to itself. 

Suppose for contradiction that $\dots [f_1]\in [f_0]$, let $J_\theta[x]$ be such that $f_n\in J_\theta[x]$. Take:
$$\pi: J_{\delta}[x]\cong h_{J_\theta[x]}(\gamma\cup \{f_n\mid n\in \omega\})\prec J_\theta[x]$$
Then we assume $\pi(g_n) = f_n$ and $\delta<\alpha$ since $|J_{\delta}[x]|= \gamma<\alpha$. Thus $g_n\in J_\delta[x]\subseteq J_\alpha[x]$, since $\pi$ is elementary and is constant on $\gamma$, we have that $\{\xi\mid g_n(\xi)\in g_m(\xi)\}\in U$ iff $\{\xi\mid f_n(\xi)\in f_m(\xi)\}\in U$. This means that $[g_0],[g_1]\dots$ would be an ill-founded chain in $Ult(J_\alpha[x],U)$, but this model embeds into $J_\beta[x]$, a contradiction. $\Box$

**Claim 10.9.2 Let $\kappa$ be $\omega_1$-Erdos, then $\kappa\to [\omega_1]_{2^\omega}^{<\omega}$.**

See for instance Jech Lemma 17.29$\Box$

(i) Now for the $\omega_1$ Erdos cardinal $\kappa$, we consider the model $J_\kappa[x]$. Define the map $F:[\omega]^{<\omega}\to 2^\omega$ by the following, for $n,m\in \omega$, $\lambda_1<\dots <\lambda_n<\kappa$: $$F(\lambda_1\dots \lambda_n) = \{n\mid J_\kappa[x]\models \varphi_n(\lambda_1\dots \lambda_n)\}$$ Then by the Claim 10.9.2 we obtain there is $X\subseteq \kappa$ of size $\omega_1$ s.t. $X$ is a set of indiscernibles for $J_\kappa[x]$, i.e. for any $\lambda_{i_1}<\dots <\lambda_{i_n}\in X$ and $\lambda_{j_1}<\dots <\lambda_{j_n}\in X$ and any $\varphi$, $$J_\kappa[x]\models \varphi(\lambda_{i_1}\dots \lambda_{i_n})\iff J_\kappa[x]\models \varphi(\lambda_{j_1}\dots \lambda_{j_n})$$
We consider the model $$\pi:J_\alpha[x]\cong h_{J_\kappa[x]}(X) \prec J_\kappa[x]$$
We write $\pi(\xi_\alpha) = \lambda_\alpha$ for . Then in $J_\alpha[X]$, every $a\in J_\alpha[x]$ is of the form $h_{J_\alpha[x]}(n,\xi_{\alpha_1}\dots \xi_{\alpha_n})$ for some $n$ and $\xi_{\alpha_i}$ and $\{\xi_{\alpha}\mid \alpha<\omega_1\}$ is indiscernibles for $J_\alpha[x]$. 
Then for arbitrary $e:\omega_1\to \omega_1$ that is order preserving, it induces an elementary embedding $J_\alpha[x]\to J_\alpha[x]$ by the following map: $$\pi_e: h_{J_\alpha[x]}(n,\xi_{\alpha_1}\dots \xi_{\alpha_n})\mapsto h_{J_\alpha[x]}(n,\xi_{e(\alpha_1)}\dots \xi_{e(\alpha_n)})$$
Moreover, the first ordinal moved will be less than $|\alpha|$ since it is countable, while $\alpha\geq \omega_1$ as $|h_{J_\kappa[x]}(X)|\geq \omega_1$. By Claim 10.9.1 $x^\sharp$ exists.  $\Box$



---
## Problem 10.10 
(a) We first show that for all ordinal $\delta\in J_\alpha[x]$, we have $\pi^{J_\alpha[x]}_U(\delta) = \pi^{L[x]}_U(\delta)$. It suffice to show that $\delta^\kappa\cap J_\alpha[x] = \delta^\kappa\cap L[x]$.

$\subseteq$ is obvious. For the other side, if $f\in \delta^\kappa\cap L[X]$, we take $\gamma$ large enough s.t. $f\in J_\gamma[x]$ and: $$\pi:(J_\beta[x], x)\cong (Hull_{L[x]}(TC(f)), x) \prec_{\Sigma_1} (L[x],x)$$
where $|J_\beta[x]|\leq max\{\delta,\kappa\}\leq {\kappa^+}^{L[x]} = \alpha$. Hence $\beta\leq \alpha$ and thus $f\in J_\alpha[x]$. 

**Note**: Here the condensation always applies as $x\subseteq \omega$, hence the structures are always elementary w.r.t. the predicate.

Now given $\pi^{J_\alpha[x]}_U(\delta) = \pi^{L[x]}_U(\delta)$ for all ordinal $\delta\in J_\alpha[x]$, we show that $\pi^{J_\alpha[x]}_U = \pi^{L[x]}_U|_{J_\alpha[x]}$. For arbitrary $a\in J_\alpha[x]$, we have $\delta<{\kappa^+}^{L[x]}$ s.t. $L[x]\models rank_{<_{L[x]}} (a) = \delta$. By $\Sigma_1$ elementariness of ultrapower embedding,  $Ult(L[x],U)\models rank_{<_{L[x]}} (\pi^{L[x]}_U(a)) = \pi^{L[x]}_U(\delta)$. Hence $L[x]\models rank_{<_{L[x]}} (\pi^{L[x]}_U(a)) = \pi^{L[x]}_U(\delta) = \pi^{J_\alpha[x]}_U(\delta)$. This shows that $\pi^{L[x]}_U(a) = \pi^{J_\alpha[x]}_U(a)$.

(b) As for $f:\kappa\to J_\alpha[x]$ that is $\in J_\alpha[x]$, $\pi^\mathcal{M}_U(f)(\kappa) = \pi^{L[x]}_U(f)(\kappa)$ by (a). This shows that $Ult_0(\mathcal{M})\subseteq Ult(L[x],U)$. Hence $Ult_0(\mathcal{M})$ is transitive.

$J_{\alpha'}[x] = \{\pi^\mathcal{M}_U(f)(\kappa)\mid f\in  J_\alpha[x]^\kappa\cap J_\alpha[x]\} =\{\pi^{L[x]}_U(f)(\kappa)\mid f\in  J_\alpha[x]^\kappa\cap L[x]\} = \pi^{L[x]}_U(J_\alpha[x])$.
For the last equation, the $\subseteq$ side is easy. For the other side, if $a\in \pi^{L[x]}_U(J_\alpha[x])$, assume $a = \pi^{L[x]}_U(f)(\kappa)$ where $f\in L[x]^\kappa\cap L[x]$, we can alter $f$ to $g$ s.t. $g\in J_\alpha[x]^\kappa\cap L[x]$ and $a = \pi^{L[x]}_U(f)(\kappa) = \pi^{L[x]}_U(g)(\kappa)$.

(c) by induction.

(d) For $\alpha<\pi(\xi)$, we show that there is $\eta<\xi$ s.t. $\alpha<\pi(\eta)$, which concludes the proof. Let $\alpha = [f]_U\in Ult(L[x],U)$, we may assume $f:\kappa\to \xi$. But as $cf(\xi)>cf(\kappa)$, $supf = \delta<\xi$.Hence $\alpha\leq\pi(\delta)<\pi(\delta+1)$. 



By induction we show that $\pi_{0,\alpha}(\xi) = \xi$ and $cf(\xi)>({2^{Card(\kappa)}}^+)$, the successor case: since $|\kappa_{\alpha+1}|<{2^{Card(\kappa_\alpha)}}^+$, we have by the above conclusion $\pi_{0,\alpha+1}(\xi) = \pi_{0,\alpha}(\xi) = \xi$. 

For the limit case since $\xi$ is a limit and $\gamma\leq {2^{Card(\kappa_\alpha)}}^+$, we have $cf(\xi)>({2^{Card(\kappa)}}^+)$. $\pi_{0,\gamma}(\xi) = \xi$ since if $\pi_{0,\gamma}(\alpha)\leq\bigcup_{\beta<\gamma}m_\beta$ where $m_\beta$ is taking $\beta$ many power for $|\alpha|$, e.g. $m_1 = 2^{|\alpha|}$, $m_1 = 2^{2^{|\alpha|}}$ ... Which is still less than $\xi$ since $\xi$ is strong limit. $\Box$

---
## Problem 10.11

Let $\mathcal{M}_0 = x^\sharp$ and $I = \{\kappa_\alpha\mid \alpha<\omega_1\}$ be the set of countable silver indiscernibles. We aim to show that for each $X\in \mathcal{P}(\omega_1)\cap L[x]$, there is $\alpha$ s.t. either $$\{\kappa_\beta\mid \alpha<\beta\}\subseteq X\text{ or }\{\kappa_\beta\mid \alpha<\beta\}\subseteq \omega_1\setminus X$$
And the conclusion follows from 10.2 (b).

Take the $\omega_1$ itreration of $x^\sharp$, we have that $$X\in \mathcal{P}(\omega_1)\cap L[x]\Rightarrow X\in \mathcal{M}_{\omega_1}$$
since $\omega_1$ is the largest cardinal in $\mathcal{M}_{\omega_1}$ and thus we know that $\mathcal{P}(\omega_1)\cap L[x] = \mathcal{P}(\omega_1)\cap \mathcal{M}_{\omega_1}$ by the argument in 10.10 (a).

Hence, $X = \pi_{\alpha,\omega_1}(Y)$ for some $\alpha<\omega_1$ and $Y\in \mathcal{P}(\kappa_\alpha)\cap \mathcal{M}_\alpha$. We show that if $X\in U_\alpha$ then $\{\kappa_\beta\mid \alpha<\beta\}\subseteq X$ and the other case is similar.

The proof mirrors the argument in Lemma 10.9. For arbitrary $\beta>\alpha$, we consider the function for all $\xi\in \omega_1$, $$\varphi(\xi) = \begin{cases}
\xi &\text{if }\xi\leq \alpha \\
\xi + \beta - (\alpha+1) &\text{if }\xi>\alpha
\end{cases}$$
By the Shift lemma, we have $$Y\in U_\alpha\iff \kappa_{\alpha+1}\in \pi_{\alpha\alpha+1}(Y) \iff \pi_{0\alpha+1}(\kappa)\in X\iff \pi_{0\beta}(\kappa) = \pi^\varphi_{\omega_1\omega_1}(\pi_{0\alpha+1}(\kappa))\in \pi^\varphi_{\omega_1\omega_1}(X) = X$$
$\Box$

---
## Problem 10.12
We say a real $x$ codes a structure $(M,\in, A)$ iff for $o(x):n\mapsto 2n+1$ and $e(x):n\mapsto 2n$ $\pi(\omega,E_{o(x)},A_{e(x)})\cong (M,\in,A)$ where $E_{o(x)}$ denotes the standard coding of $o(x)$ as a well-founded relation and $n\in A_{e(x)}\iff e(x)(n)\neq 0$. $\pi$ is the transitive collapse.

**Claim 10.12.1 The following relation is $\Sigma^1_2$: $$(x,y)\in A\iff x\text{ codes a premouse and its iteration up to }||y||.$$ In the sense that for all $n$, $(x)_n:m\mapsto x(\Gamma(n,m))$ codes a premouse and**$$n_1E_y n_2\iff (x)_{n_2}\text{ codes an ultrapower of }(x)_{n_1}$$
Proof. First we show that $x$ codes a premouse is $\Pi^1_1$. $x$ codes a premouse iff $o(x)\in \mathsf{WF}$ and $(\omega,E_{o(x)})\models ZFC^- + V = L+\text{there is a largest cardinal}$ and say $n_\kappa$ is the largest cardinal in $(\omega,E_{o(x)}$ $(\omega,E_{o(x)},U_{e(x)})\models U_{e(x)} \text{ is a non-trivial normal } <\kappa\text{ complete ultrafilter on }\kappa$. 

$(\omega,E_{o(x)})\models ZFC^- + V = L + \text{there is a largest cardinal}$ is arithmetical since the relation $(\omega,E_{o(x)})\models \varphi(n_1\dots n_m)$ is arithmetical. To analyze $(\omega,E_{o(x)},U_{e(x)})\models U_{e(x)} \text{ is a non-trivial normal } <\kappa\text{ complete ultrafilter on }\kappa$, for instance $(\omega,E_{o(x)},U_{e(x)})\models U_{e(x)} \text{ is }<\kappa\text{ complete.}$ iff $$\forall n (\pi_x(n)\in \pi_x(n_\kappa)\to \forall X\in [\omega]^\omega(\forall m\in X(m\in U_{e(x)}\land \pi_x(m)\in \pi_x(n))\to \exists l\in U_{e(x)}(\bigcap\pi_x[X] = \pi_x(l)))$$
Where $\pi_x$ is the Mostowski collapse. This is a $\Pi^1_1$ property, for the Mostowski collapse part see for instance Jech Proof of Lemma 25.25.

Next consider the following relation:$$(x,y)\in Ult\iff y,x\text{  both code premice and } y\text{ codes the ultrapower of }x$$
First we notice the ultrapower equivalence relation for $x$ is given by, for $n_1,n_2$ that are functions with domain $\omega$ in $(\omega,E_{o(x)})$ collapsed, $$n_1\equiv n_2\iff \exists m(m\in U_{e(x)}\land \forall l(\pi(l)\in \pi(m)\to \pi(n_1)(\pi(l))\in \pi(n_2)(\pi(l)))) \tag{*}$$

We have $y$ codes the ultrapower of $x$ iff there is $\equiv_x\subseteq \omega^2,f\in \omega^\omega$ s.t. $\equiv_x$ is an equivalent relation satisfying $*$, $f$ respects $\equiv_x$ and is bijective $\omega\to \{n\in\omega\mid \pi_x(n)\text{ is a function with domain }\omega\} / \equiv_x$, $$n_1E_{e(y)}n_2\iff \exists m(m\in U_{e(x)}\land \forall l(\pi(l)\in \pi(m)\to \pi(n_1)(\pi(l))\in \pi(n_2)(\pi(l))))$$
and 
$$n_1\in U_{e(y)}\iff m(m\in U_{e(x)}\land \forall l(\pi(l)\in \pi(m)\to l\in U_{e(x)}))$$
And hence $Ult$ is a $\Sigma^1_1$ relation.

Hence, let $(x)_n:m\mapsto x(\Gamma(n,m))$,  $(x,y)\in A\iff \forall n_1,n_2(n_2 \text{ is the }E_y \text{ successor of }n_1\to ((x)_{n_1},(x)_{n_2})\in Ult)$, and thus is $\Delta^1_2$. Moreover, the shows that the section of $A$ along $y$ is also $\Delta^1_2$. $\Box$ 

Thus given the claim, we can already prove that for any $\beta<\omega_1^L$ there is $\beta'>\beta$, $\alpha$ s.t. the there is premouse $(J_\alpha,\in ,U)\in L$ and the putative iteration of length $\beta'+1$ whose last model is ill-founded. For each $\beta<\omega_1^L$, pick $y\in \omega^\omega\cap L$ s.t. $||y|| = \beta$, since by Claim the section $A_y = \{x\mid (x,y)\in A\}$ is $\Delta^1_2$. $0^\sharp$ witnesses its non-emptiness in $V$, by Shoenfield absoluteness Cor 7.21 $A_y$ is non-empty in $L$. say $x\in A_y$. But the minimal premouse coded in $x$ cannot be iterable since otherwise $0^\sharp\in L$, which is nonsense, hence some step of the iteration greater than $\beta$ must fail.

Next we show that for any $\beta<\omega_1^L$ there is $\alpha$ s.t. there is premouse $(J_\alpha,\in ,U)\in L$ and the putative iteration of length $\beta+1$ whose last model is ill-founded. Pick the $L$ least element $J_\alpha,\in,U$ s.t. there is $x\in A_y$ s.t. $(x)_{n^*}$ codes $J_\alpha,\in ,U$ where $n^*$ is the least element in the order coded by $y$. We build a tree of attempts to find elementary embeddings from the $\beta+1$ th iterate of $J_\alpha,\in,U$ into some large enough model. 


---
## Problem 10.13
We use the fact that $Col(\omega,<\kappa) = \prod^{fin}_{\lambda<\kappa}Col(\omega,\lambda)$. Let $(\kappa_\alpha,\alpha<\omega_1)$ be the countable Silver indiscernibles, as discussed in problem 10.11. Let $(\mathcal{M}_\alpha,\pi_{\alpha\beta},\alpha\leq \beta<\omega_1)$ be the iteration of $x^\sharp$ up to $\omega_1$.

We prove by induction that $\alpha<\omega_1$, there is $G_\alpha\in V$ s.t. that is $Col(\omega,<\kappa_\alpha)$-generic over $L[x]$. And if $\alpha<\beta$, then $G_\alpha,G_\beta$ are consistent in the sense that if $p\in Col(\omega,<\kappa_\beta)$ has support contained $\kappa_\alpha$, it holds true that $p\in G_\alpha\iff p\in G_\beta$

The base case: $\kappa_0$ is countable in $V$ and all dense sets in $Col(\omega,<\kappa_0)$ that is in $L[x]$ is already contained in $\mathcal{M}_0$, thus is countable. By the generic filter theorem there is $Col(\omega,<\kappa_0)$ generic $G_0$ over $L[x]$.

The successor case: $Col(\omega,<\kappa_{\alpha+1}) = Col(\omega,<\kappa_{\alpha})\times \prod^{fin}_{\kappa_\alpha\leq\lambda<\kappa_{\alpha+1}}Col(\omega,\lambda)$, by a similar argument to the base case, we have $\prod^{fin}_{\kappa_\alpha\leq\lambda<\kappa_{\alpha+1}}Col(\omega,\lambda)$ generic $H$ over $L[x]$ in $V$. Let $G_{\alpha+1} = G_\alpha\times H$ and by Lemma 6.65 this satisfies the requirement.

The limit case: Define $q\in G_\gamma \iff \text{the support of }q\text{ is contained in }\kappa_\alpha, q\in G_\alpha$.
We have that $G_\gamma$ is generic as suppose $A$ is an antichain of $Col(\omega,<\kappa_\gamma)$, by the fact that $\omega_\gamma$ is inaccessible in $L[x]$, by Lemma 6.44 $L[x]$ thinks $|A|<\kappa_\gamma$, thus for some $\alpha<\gamma$, and thus $A$ can be considered as an antichain in $Col(\omega,<\kappa_\alpha)$. By the consistency of $G_\gamma$ w.r.t. $G_\alpha$, it intersects $A$. 

Next, we consider the filter $G$ on $Col(\omega,<\omega_1)$ defined by $$p\in G\iff\text{suppose the support of }q\text{ is contained in }\kappa_\alpha, \text{then }p\in G_\alpha$$
By the exact same argument as the limit case, we have that $G$ is generic. $\Box$

---
## Problem 10.14
**Claim 10.14.1 A remarkable cardinal is inaccessible.**
Proof. To show it is regular, pick arbitrary function $f:\delta\to \kappa$ where $\delta<\kappa$. We pick $\alpha>\kappa$ s.t. $f$ exists in $V_\alpha$. In the generic extension, there is $\sigma:V_\beta\to V_\alpha$ with critical point $\mu,\sigma(\mu) = \kappa$. Since $V_\beta\models \mu$ is inaccessible, $V_\alpha\models\kappa$ is inaccessible, contradicting the existence of $f$. The proof for strong limit is similar. $\Box$ 

**Claim 10.14.2 For regular $\kappa$, $\kappa$-c.c. forcing preserves stationary in $[\lambda]^{<\kappa}$**

Proof. For arbitrary $\dot{C}$ s.t. $p\Vdash \dot{C}$ is club, we pick $\tau$ s.t. $p\Vdash \tau\in \dot{C}$. We subsequently pick nice name $\tau_n$, $X_n\in V$ s.t. $p\Vdash \tau_n\in \dot{C}$, $p\Vdash \check{X_n}\subseteq \tau_n$, $X_n\in [\lambda]^{<\kappa}$ and $ran(\tau_n)\subseteq X_n\in [\lambda]^{<\kappa}$. The final requirement is doable by $\kappa$-c.c. forcing. The sequence is definable in $V$, and thus we take $\bigcup_n X_n$, which is in $V$ and $p$ forces it to be in $\dot{C}$. 
This argument shows that the limit point of $\dot{C}_G$ is a club set in $V$. This entails that the forcing preserves stationary in $[\lambda]^{<\kappa}$. $\Box$

(a) For arbitrary $\alpha$, pick $\sigma:V_\beta\to V_\alpha$  in $V[G]$ s.t. $crit(\sigma) = \mu$ and $\sigma(\mu) = \kappa$. The idea is to show that in, $S = \{X\in [V_\beta]^\omega\mid X\prec V_\beta, X\cap \mu\in \mu, \exists \beta'X\cong V_{\beta'}\}$ is stationary and lift this statement via $\sigma$, then use the stationary preservation.

Now by the proof of Madgidor's characterisation of supercompact cardinal problem 4.29 and problem 4.30, we have that there is a normal $V$-ultrafilter $U$ on $([V_\beta]^{<\mu})^V$ generated by $$X\in U\iff \sigma[V_\beta]\in \sigma(X)$$
Hence we obtain that the set $S$ is in $U$ as of course $\sigma[V_\beta]\in \sigma(S) = \{X\in [V_\alpha]^\omega\mid X\prec V_\alpha,X\cap \kappa\in \kappa, \exists \beta X\cong V_\beta\}$. This means that $S$ intersects all $V$ club in $[V_\beta]^{<\mu}$. Lift this up and hence $\{X\in [V_\alpha]^{<\kappa}\mid X\prec V_\alpha, X\cap \kappa\in \kappa, \exists \beta'X\cong V_{\beta'}\}$ intersects all $V$ club in $[V_\alpha]^{<\kappa}$. Since $Col(\omega,<\kappa)$ is $\kappa$- c.c., stationary set of $[V_\alpha]^{<\kappa}$ is preserved and hence it is stationary in $[V_\alpha]^\omega$ in V[G]. $\Box$

(b) If $0^\sharp$ exists, for Silver indiscernible 

(c) If $\kappa$ is a remarkable cardinal in $V$, then for arbitrary $\alpha$ there is in $V[G]$ an elementary embedding $\sigma:V_\beta\to V_\alpha$ with $crit(\sigma) = \mu$ and $\sigma(\mu) = \kappa$. It suffice to argue that some embedding $\sigma':(V_\beta)^L\to (V_\alpha)^L$ exists in $L[G]$. 

**Claim 10.14.3 If $j:M\to N$ is an elementary embedding in $V$ and $M$ is countable, then for any transitive model $H$ that knows enough ZFC so that well-foundedness is absolute s.t. $M,N\in H$ and $M$ is countable in $H$, then there is elementary embedding $j':M\to N$ in $H$**

Proof. Define the following tree of partial elementary map: Fix an enumeration $m_i,i\in \omega$ of elements in $M$. $p\in T$ is a partial elementary map from $M$ to $N$ with finite domain. $p_1\leq p_2$ if $p_1$ is an end extension of $p_2$. Then we have $$T\text{ is ill-founded}\iff \exists j:M\to N\text{ elementary }$$
By the assumption that ill-foundedness is absolute between $M$ and $N$, we obtain the desired result.

Now $\sigma|_{(V_\beta)^L}$ is an elementary map from countable structure $V_\beta^L$ to $V_\alpha^L$. $V_\beta^L$ is still countable in $L[G]$ as $\beta<\kappa$. By the claim 10.14.3 we thus obtain that such an elementary map exists in $L[G]$. $\Box$

---
## Problem 10.16
**Claim 10.16.1 If V is closed under sharps then for all $X\subseteq Ord$ and $X\in V$, $X^\sharp$ exists.**
This is essentially Jech Exercise 18.2

Proof of Claim:  We take $\kappa>|X|$ and take $H$ generic over $Col(\omega,\kappa)$, then $X$ is countable in $V[G]$ and hence $X^\sharp$ exists. But the statement that  $X^\sharp$ exists is equivalent to the statement that $L[X]$ has a proper class of Silver indiscernibles. Take $\{\kappa_\alpha\mid \alpha>\beta\}$ be the class of cardinals in $V[G]$ greater than $|\mathbb{P}|$, they are also cardinals in $V$. Notice $L\models \varphi(\kappa_{\alpha_1}\dots \kappa_{\alpha_n})$ iff $L\models \varphi(\kappa_{\alpha_1'}\dots \kappa_{\alpha_n'})$, is absolute for $V[G]$ and $V$ and hence $\{\kappa_\alpha\mid \alpha>\beta\}$ is a proper class of  Silver indiscernibles in $V$. This shows that $X^\sharp$ exists in $V$. $\Box$

Let $G$ be generic over $\mathbb{P}$. Let $A$ be such that $V[G]\models x\in A\iff \exists y\varphi(x,y,z)$ for some $\varphi$ that is $\Sigma^1_2(z)$. We take $X\in V$ s.t. $\mathbb{P}\in X^\sharp = (J_\alpha[X],\in,U)$ and $\mathbb{P}\in J_\kappa[X]$, where $\kappa$ is the largest cardinal in $J_\alpha[x]$. Say $$p\Vdash \varphi(\tau_1,\tau_2,z)$$
We take $\pi:N\to X^\sharp$ elementary be s.t. $N$ countable transitive, $\pi(q) = p$ and $\pi(\mathbb{Q}) = \mathbb{Q}$, $\pi(\sigma_1) = \tau_1$ and  $\pi(\sigma_2) = \tau_2$. Hence $$N\models q\Vdash \varphi(\tau_1,\tau_2,z)$$
By assumption that $\mathbb{P}\in J_\kappa[X]$, $\mathbb{Q}$ is contained in the part that is not moved by iteration.

By Claim 10.1.1, we may iterate $N$ up to $\omega_1$, call it $N_{\omega_1}$, then $\omega_1\subseteq N_{\omega_1}$ and $q,\mathbb{Q}, \sigma_1,\sigma_2$ is unchanged under the iteration. Notice that the subsets of $\mathbb{Q}$ in $N_{\omega_1}$ are already appearing in $N$, which is countable.  Hence, there is a $\mathbb{Q}$ generic $g\in V$ over $N_{\omega_1}$, and we have $$N_{\omega_1}[g]\models \varphi({\sigma_1}_g,{\sigma_2}_g,z)$$
As ${\sigma_1}_g,{\sigma_2}_g\in V$ by Shoenfield absoluteness, $$V\models \exists x,y\varphi(x,y,z)$$
Concluding the proof. $\Box$

---
## Problem 10.17
**Right to Left:** Assume for contradiction that $\dots\in[a_2,f_2]\in[a_1,f_1]$.

By Lemma 10.64, we may have $$h_{Ult_0(V;E)}(\{ [a_n,f_n]\mid n\in \omega\})\prec_{\Sigma_0}Ult_0(V;E)$$
and $\Sigma_0$ elementary map $$\varphi:h_{Ult_0(V;E)}(\{ [a_n,f_n]\mid n\in \omega\})\to V$$This leads to the non well-foundedness of $V$, a contradiction.

**Left to Right:** Assume $Ult(V,E)\cong M$ is well founded. Let $j_E$ be the extender embedding. Consider the tree $$U: = \{s\mid \exists k\in \omega(s:\bigcup_{i\leq k}a_i\to \kappa\land s\text{ is order preserving }\land \forall i\leq k, s[a_i]\in X_i)\}$$
where the order is $s_1\prec s_2\iff s_2\subset s_1$. The inverse of $j|_{\bigcup_{i\in \omega}a_i}$ witnesses that $j(U)$ is not a well-founded tree as for each $k$, $$(j|_{\bigcup_{i\leq k}j(a_i)})^{-1}:\bigcup_{i\leq k}j(a_i)\to j(\kappa)\text{ is order preserving and }\forall i\leq k(j|_{\bigcup_{i\leq k}j(a_i)})^{-1}(j(a_i)) = a_i\in X_i$$
By the absoluteness of well-foundedness, $j(U)$ is not well-founded in $M$, and thus $U$ is not well-founded in $V$ by elementarity. This gives the desired map. $\Box$

---
### Problem 10.18
(1) For $cf(\alpha)<\kappa$, the argument is exactly the same as Lemma 4.52 (c).

For $cf(\alpha)>\kappa$, let $\beta_\gamma\to \alpha,\gamma\to cf(\alpha)$. Of course $\bigcup_{\gamma\to cf(\alpha)}\pi_E\beta_\gamma \leq \pi_E\alpha$. For arbitrary $\xi<\pi_E\alpha$, $\xi = [a,f]$ for some $a\in [\nu]^{<\omega},f:[\mu_a]^{|a|}\to \alpha$. By the fact that $E$ is a short extender, we have $|\mu_a|\leq \kappa$, then $f$ has to be bounded by some $\pi_E\beta_\gamma$, hence $\xi<\pi_E\beta_\gamma$.

(2) Pick a cofinal sequence $\beta_\gamma\to \lambda,\gamma\to cf(\lambda)$. By (1) we thus have $sup_{\gamma\to cf(\lambda)}\pi_E\beta_\gamma = \pi_E\lambda$. We show that $\pi_E\beta_\gamma<\lambda$ and this concludes the proof. Since each $\xi<\pi_E\beta_\gamma$ is of the form  $\xi = [a,f]$ for some $a\in [\nu]^{<\omega},f:[\mu_a]^{|a|}\to \beta_\gamma$, and as $E$ is a short extender, we have $|\mu_a|\leq \kappa$. We have that $|\pi_E\beta_\gamma|\leq |\nu\times \beta_\gamma^\kappa|<\lambda$. This concludes the proof. $\Box$

---
### Problem 10.19
**Ultrafilter Property**: For $\alpha<\kappa$, $(Y_i\mid i<\alpha)\in V[G]\cap {E_a^*}^\alpha$. Let $p\in G$. Let $A_i$ be a maximal antichain, definable in $V$, of elements $p\leq q$ s.t. $\exists X_{q, i}, q\Vdash X_{q,i}\subseteq \dot{Y}_\alpha$. Then since $|\mathbb{P}|<\kappa$, $|A_i|<\kappa$ and hence $$\bigcap_{i<\alpha}Y_i \supseteq\bigcap_{i<\alpha,q\in A_i}X_{i,q} \in E_a$$
To Checking that this is an ultrafilter, upward closedness is easy. For $Y\in [\mu_a]^{|a|}\cap V[G]$, consider the following sets, definable in $V$: $D_{u}: =\{p\mid p\Vdash u\in \dot{Y}\}, F_u = \{u\mid p\Vdash u\not\in \dot{Y}\}$. By the fact that $\kappa$ is inaccessible in $V$, $\{D_u\mid u\in [\mu_a]^{|a|}\}\subseteq \mathcal{P}(|\mathbb{P}|)$ and thus is of cardinality less than $\kappa$. Hence there is $X\in E_a$ s.t. $D_u = D_{u'}, F_u = F_{u'}$ for all $u,u'\in X$. Now $D_u\cup F_u$ is dense in $\mathbb{P}$ and hence $G$ intersects elements of it, but it can't intersect element from both $D_u$ and $F_u$. If $G\cap D_u$ is not empty, then $Y\supseteq X$ and hence $Y\in E_a^*$, the other side is similar.

Remark:If we naively take $(X_i\mid i<\alpha)$ subsets of $(Y_i\mid i<\alpha)$, the sequence might not be in $V$. We circumvent this by considering all possible subsets of $Y_i$ in $U$. 

We notice that ($*$) for all ordinal $\mu$, $[\mu]^{|a|}\in E_a\iff [\mu]^{|a|}\in E_a^*$ and hence $\mu_a$ is the smallest $\mu$ s.t. $[\mu]^{|a|}\in E_a\iff [\mu]^{|a|}\in E_a^*$.

**Coherence**: For $Y\in E^*_a$ and $b\supseteq a$, we have that $Y\supseteq X$ for some $X\in E_a$ and thus $X^{ab}\in E_b$. Since $X^{ab}\subseteq Y^{ab}$, $Y^{ab}\in E^*_b$. 

The other side follows from the fact that if $Y\not\in E^*_a$, then $[\mu_a]^|a|-Y\in  E^*_a$ but ${[\mu_a]^|a| - Y}^{ab}\cap Y^{ab} = \emptyset$.

**Uniformity** follows from ($*$).

**Normality**: 
Take $f:[\mu_a]^{|a|}\to \mu_a$ with $f\in V[G]$, $$p\Vdash \exists X,X\subseteq \{u\mid \dot{f}(u)<max(u)\}$$

**Case 1**: $\mu_a<\kappa$.
We have $p\Vdash \bigcup_{g:[\mu_a]^{|a|}\to \mu_a}\{u\mid g(u) = \dot{f}(u)\} = [\mu_a]^{|a|}$ since $p\Vdash \exists g:[\mu_a]^{|a|}\to \mu_a, g(u) = \dot{f}(u)$ for all $u$. Since there are at only $|\mu_a|^{\mu_a}$ many such functions $g:[\mu_a]^{|a|}\to \mu_a$, $p\Vdash \exists g, \{u\mid g(u) = \dot{f}(u)\}\in E_a$. Since we have $\{u\mid g(u)<max(u)\}\in E_a$, we obtain by normality that there is $\beta$ s.t. $\{u\mid g^{a,a\cup\{\beta\}}(u)<max(u)\}\in E_{a\cup \{\beta\}}$. The conclusion follows as $$\{u\mid g^{a,a\cup\{\beta\}}(u)<max(u)\}\cap\{u\mid g^{a,a\cup\{\beta\}}(u) = \dot{f}^{a,a\cup\{\beta\}}(u)\}\subseteq \{u\mid \dot{f}^{a,a\cup\{\beta\}}(u)<max(u)\}$$

**Case 2**: $\mu_a\geq \kappa$. Idea: $<\kappa$ forcing should preserve stationary sets for $[\mu_a]^{<\omega}$, $\mu_a>\kappa$. 

**Claim 10.19.1 For $\kappa$ regular, forcing of size $<\kappa$ preserves stationary sets on $\mu$ where $\mu\geq \kappa$.**

Proof of Claim. It suffice to show that if $p\Vdash \dot{C}$ is a club, then $p\Vdash \{\alpha\mid \alpha\in \dot{C}\}$ is a club. That $p\Vdash\{\alpha\mid \alpha\in \dot{C}\}$ is closed is easy. For $\alpha_0$ s.t. $p\Vdash \alpha_0\in \dot{C}$, we have a name $\dot{\gamma_0}$ for an ordinal s.t. $p\Vdash \alpha_0<\dot{\gamma_0}\in \dot{C}$. Pick a maximal antichain $A$ under $p$ where $q\in A$ entails $q\Vdash \dot{\gamma_0} = \gamma_q$. By the fact that the forcing is of size $<\kappa$, we have $\alpha_1 = sup\{\gamma_q\mid q\in A\}<\kappa$ and thus $$p\Vdash \exists \dot{\gamma_0}\in \dot{C}, \alpha_0<\dot{\gamma_0}<\alpha_1$$
Repeat this process to find $\alpha_n,n\in \omega$ s.t. $$p\Vdash \exists \dot{\gamma_n}\in \dot{C}, \alpha_n<\dot{\gamma_n}<\alpha_{n+1}$$
Of course, $p$ thinks $\dot{\gamma_n}$ and $\alpha_n$ shares a limit, and by closedness of $\dot{C}$, $\lim_{n\in \omega}\alpha_{n}\in \{\alpha\mid \alpha\in \dot{C}\}$. $\Box$

Remark: The argument actually works for $\kappa$ c.c. posets, and is the argument used to show that c.c.c. forcing is proper.

Proof of case 2: Fix an enumeration $\Gamma:[\mu_a]^{|a|}\to \mu_a$ satisfying $\Gamma(u)>max(u)$. And consider the induced map $\Gamma: \mathcal{P}([\mu_a]^{|a|})\to \mathcal{P}(\mu_a)$

Then, the normality of $E_a$ is equivalent to saying that $\{\Gamma(X)\mid X\in E_a\}$ contains all closed sets in $\mu_a$ (normal as an ultrafilter on $\mu_a$). Then the conclusion follows by Claim 10.19.1. $\Box$

Next, we show that the two large cardinals are preserved under small forcing.

**Claim 10.19.2 For forcing $\mathbb{P}$ of size $<\kappa$, the extender elementary embedding $\pi_E:V\to Ult(V,E)$ extends to elementary $\pi_{E^*}:V[G]\to Ult(V[G],E^*)$, satisfying**
$$\pi_{E^*}:\tau_G\mapsto \pi_E(\tau)_G = [\emptyset, c_{\tau_G}]_{E^*}$$
**And consequently, $Ult(V[G],E^*) = Ult(V,E)[G]$.**

Proof. To show that $\pi_{E^*}$ is elementary, it suffice to show that $\pi_E(\tau)_G = ([\emptyset, c_{\tau}]_{E})_G = [\emptyset, c_{\tau_G}]_{E^*}$. We prove by an induction on the well-foundedness of elements in $Ult(V[G],E^*)$ that $$[a,\dot{f}_G]_{E^*} = ([a,\dot{f}]_E)_G$$ Notice as the domain $[\mu_a]^{|a|}$ is absolute, here we can slightly abuse the notation, by $\dot{f}$ refers to both the function from $[\mu_a]^{|a|}$ to names and a name of the function from $[\mu_a]^{|a|}$ to elements in $V[G]$.

Say for $[b,\dot{g}_G]_{E^*}\in [a,\dot{f}_G]_{E^*}$, by IH we have $[b,\dot{g}_G]_{E^*} = ([b,\dot{g}]_E)_g$.

$$\begin{align}
[b,\dot{g}_G]_{E^*}\in [a,\dot{f}_G]_{E^*} & = \exists X\in E_{a\cup b}, X\subseteq\{u\in [\mu_{a\cup b}]^{|a\cup b|}\mid \dot{g}_G^{b,a\cup b}(u)\in \dot{f}_G^{a,a\cup b}(u)\}\\
& \iff \exists X\in E_{a\cup b}, X\subseteq\{u\in [\mu_{a\cup b}]^{|a\cup b|}\mid\exists p\in G,p\Vdash  \dot{g}^{b,a\cup b}(u)\in \dot{f}^{a,a\cup b}(u)\} \\
& \iff \exists p\in G, p\Vdash \{u\in [\mu_{a\cup b}]^{|a\cup b|}\mid \dot{g}^{b,a\cup b}(u)\in \dot{f}^{a,a\cup b}(u)\}\in E_{a\cup b}\tag{*}\\
& \iff ([b,\dot{g}]_E)_G\in ([a,\dot{f}]_E)_G
\end{align}$$
Here the only non trivial step is ($*$), where left to right is by the fact that $|G|<\kappa$ and $E_{a\cup b}$ is $<\kappa$ complete.$\Box$

Proof of the preservation of large cardinals. 

For $\kappa$ a strong cardinal, we take arbitrary $\alpha\geq \kappa+2$, and show that there is $j: V[G]\to M$ elementary with $crit(j) = \kappa$, $(V_\alpha)^{V[G]}\subseteq M$. 

Let $E$ be the $\kappa,\nu$-extender obtained in Lemma 10.58 where $\alpha<\nu$. For $x\in (V_\alpha)^{V[G]}$, as $|\mathbb{P}|<\kappa$ we may assume $\mathbb{P}\in V_\kappa$, we have $\dot{x}\in V_\alpha$ thus in $Ult(V,U)$. By Claim 10.19.2 $Ult(V[G],E^*) = Ult(V,E)[G]$ computes the name correctly and thus $x=\dot{x}_G\in Ult(V[G],E^*)$. Hence $(V_\alpha)^{V[G]}\subseteq Ult(V,E^*)$. This concludes the proof that $\kappa$ is strong in $V[G]$.

For $\kappa$ a supercompact cardinal, similarly, let $E$ be given by Lemma 10.61 and we aim to show that $Ult(V[G],E^*)^\lambda\subseteq Ult(V[G],E_*)$. 

For $\{[a_i,{\dot{f}_i}_G]_{E^*}\mid i<\lambda\}\subseteq Ult(V[G],E^*)$, we have by Claim 10.19.2 that $\{([a_i,{\dot{f}_i}]_E)_G\mid i<\lambda\}\subseteq Ult(V,E)[G]$. This shows that $\{[a_i,{\dot{f}_i}]_E\mid i<\lambda\}\subseteq Ult(V,E)$. By $\lambda$ closedness of $Ult(V,E)$ and pass it back to $Ult(V[G],E^*)$, we are done. $\Box$

---
## Problem 10.20
This is similar to preservation of strongness. Given $\delta$ Woodin in $V$, it suffice to show for $A\subseteq (V_\delta)^{V[G]}$ there is $\kappa$ s.t. for any $\alpha<\kappa$ there is elementary $\pi:V[G]\to M$ s.t. $crit(\pi) = \kappa$, $(V_\alpha)^{V[G]}\subseteq M$ and $\pi(A)\cap (V_\alpha)^{V[G]} = A\cap (V_\alpha)^{V[G]}$.

Fix $A\subseteq (V_\delta)^{V[G]}$, $\mathbb{P}$ being small, we may assume in the similar fashion as in proof of preservation of strongness that $\dot{A}$, the name of $A$, to be a subset of $V_\delta$. We apply Lemma 10.77 and pick $\kappa$ satisfying the for all $\alpha<\kappa$ there is certified $E$ s.t. $\pi_E:V\to M$ is elementary and $crit(\pi) = \kappa$, $V_\alpha\subseteq M$ and $\pi_E(\dot{A})\cap V_\alpha = \dot{A}\cap V_\alpha$.

It suffice to show that for any $\alpha> |\mathbb{P}| + 2$, the corresponding $E$ satisfies: $\pi_{E_*}(A)\cap (V_\alpha)^{V[G]} = A\cap (V_\alpha)^{V[G]}$. We have by claim 10.19.2, $$
\begin{align}
\tau_G\in (V_\alpha)^{V[G]}\cap A &\iff  \exists p\in G, p\Vdash \tau \in \dot{A}\cap V_\alpha\\
&\iff\exists p\in G\exists B\text{ a maximal antichain under }p, B\times \{\tau\}\subseteq \dot{A}\cap V_\alpha\\
&\iff \exists p\in G \exists B\text{ a maximal antichain under }p, B\times \{\tau\}\subseteq \pi_E(\dot{A})\cap V_\alpha\\
&\iff  \exists p\in G, p\Vdash \tau \in \pi_E(\dot{A})\cap V_\alpha\\
&\iff \tau_G\in (V_\alpha)^{V[G]}\cap (\pi_E(\dot{A}))_G = (V_\alpha)^{V[G]}\cap \pi_{E_*}(A)
\end{align}
$$
This concludes the proof. $\Box$

---
## Problem 10.21 
Don't know how to argue via extenders, don't know how to show the derived extender is $\lambda$ closed. We solve this probem by proving the equivalence of Problem 10.22 first, and using Problem 10.22, 

Assume for contradiction that $\kappa$ is not supercompact, then let $\lambda\geq \kappa$ be the least cardinal s.t. there is no ultrafilter $U$ on $\mathcal{P}_\kappa(\lambda)$ witnessing $\kappa$ is not $\lambda$ supercompact. This is a first order property. 

Pick $\alpha$ s.t. $V_\alpha^\lambda \subseteq V_\alpha$, any limit $\alpha$ s.t. $cf(\alpha)>\lambda$ would satisfy the property.
Then by assumption there is $\mu<\beta<\kappa\leq \lambda<\alpha$ s.t. there is $\sigma:V_\beta\to V_\alpha$ elementary, with $crit(\sigma) = \mu$. Notice $V_\beta\models$ there is least $\delta$ s.t. there is no ultrafilter $U$ on $\mathcal{P}_\kappa(\lambda)$ witnessing $\mu$ is not $\delta$ supercompact. Say $\delta$ is a witness of this statement, then by elementarity $\sigma(\delta) = \lambda$. 

But deriving an ultrafilter $U$ on $\mathcal{P}_\kappa(\lambda)$ from $\sigma$ satisfying the conditions in 4.30, by Problem 10.22 the ultrafilter $U$  in $V_\beta$ witnesses the $\sigma^{-1}(\xi) = \delta$ supercompactness of $\mu$ in $V_\beta$. This is a contradiction.$\Box$

The use of ultrafilter turns the second-order property supercompactness to a first order property. cf. problem 10.23

---
## Problem 10.22
For $U$ a $<\kappa$ complete ultrafilter on $[\lambda]^{<\kappa}$, we show that the map $\pi_U:V\to Ult(V,U)$ witnesses that $\kappa$ is $\lambda$ supercompact. Here $Ult(V,U)$ is the ordinary ultrapower construction, adapted to $U$ and $[\lambda]^{<\kappa}$. We omit the proof of Los theorem.

**Step 1 $[id]_U = \pi_U[\lambda]$.**

$\supseteq$ is by the first property and Los theorem: For $\alpha\in \lambda$, $\{a\in [\lambda]^{<\kappa}\mid\alpha\in a \}\in U$ and thus $\pi_U(\alpha)\in [id]_U$.

$\subseteq$ is by the second property, which is clearly the analogue of normality. Suppose $[f]_U\in [id]_U$, then we have $\{a\mid f(a)\in a\}\in U$, let $X_\alpha: = \{a\mid f(a)= \alpha\}$. Suppose for contradiction that $X_\alpha\not\in U$ for all $\alpha<\lambda$, then by the second property of the ultrafilter, there is $X\in U$ s.t. if $\alpha\in a\in X$, then $a\not\in X_\alpha$, i.e. $f(a)\neq \alpha$. This set must be disjoint from $\{a\mid f(a)\in a\}$. This is a contradiction. Hence some $X_\alpha\in U$, entailing $[f]_U = \pi_U(\alpha)\in \pi_U[\lambda]$.

**Step 2 $M^\lambda\subseteq M$.**

Say $\{[f_\alpha]\mid \alpha<\lambda\}\subseteq M$. Let $g:[\lambda]^{<\kappa}\to V$ be s.t. $g(a)$ is a function $a\to V$, $g(a)(\alpha) = f_{\alpha}(a)$.

By Los theorem, $[g]_U$ is a function from $\pi_U[\lambda]\to Ult(V,U)$ and  for every $\alpha\in \lambda$, $[g](\pi_U(\alpha)) = [f_{\alpha}]$. Hence $ran([g]) = \{[f_\alpha]\mid \alpha<\lambda\}\in M$.

**Step 3 $crit(\pi_U) = \kappa$, $\lambda<\pi_U(\kappa)$**.

$crit(\pi_U)\geq \kappa$ holds by $<\kappa$-completeness and the standard argument. We have $ot([id]_U)<\pi_U(\kappa)$ as $\{a\in [\lambda]^{<\kappa}\mid ot(a)<\kappa\} = [\lambda]^{<\kappa}\in U$. Moreover for arbitrary $\gamma<\kappa$, $\gamma\leq ot([id]_U)$ since  $$\{a\in [\lambda]^{<\kappa}\mid \gamma\leq ot(a)\}\supseteq \bigcap_{\alpha<\gamma}\{a\mid \alpha\in a\}\in U$$
By the first property and $<\kappa$ completeness. This shows that $\kappa\leq ot([id]_U)<\pi_U(\kappa)$ and thus $crit(\pi_U) = \kappa$.

Finally, $\lambda = ot(\pi_U[\lambda]) = ot([id]_U) <\pi_U(\kappa)$.

This concludes the proof. $\Box$

---
## Problem 10.23
**Claim 10.23.1 Every subcompact cardinal is inaccessible.**
$\Box$

For arbitrary $A\subseteq V_\delta$, $A\subseteq H_{\delta^+}$. We find $\sigma:(H_{\lambda^+},B)\to (H_{\delta^+},A)$. For $crit(\sigma) = \mu$, $\sigma$ satisfy for arbitrary $\beta<\lambda$, $V_\beta\subseteq H_{\delta^+}$ and $\sigma(B)\cap V_\beta = B\cap V_\beta$. 

Work as the proof of Claim 10.79 in $H_{\lambda^+}$ and extract an $(\mu,\lambda)$ extender $E$ witnessing $\pi_E(B)\cap V_\beta = B\cap V_\beta$, the extender is in $H_{\lambda^+}$. 

Pass the statement to $H_{\lambda^+},A$ and hence for all $\alpha<\delta$ there is $\sigma(\mu)$, there is $\sigma(E)$ a $(\sigma(\mu),\delta)$ extender on $\sigma(\mu)$, witnessing $A\cap V_\alpha = \pi_{\sigma(E)}(A)\cap V_\alpha$. $\Box$

---
## Problem 10.24
Let $x: = \bigcup\{s\mid \exists T\in G, s\text{ is the stem of }T\}$.
For arbitrary $\delta\in [\kappa,\lambda]$ s.t. $cf(\delta)\geq \kappa$, we show that $\{\sup (a\cap \delta)\mid a\in x\}$ is unbounded in $\delta$. And the conclusion $cf^{V[G]}(\delta) = \omega$ follows.

To that end, it suffice to show that $$\{T\mid s\text{ is the stem of }T, \exists a\in s, \gamma\leq \sup a, a\cap[\gamma,\delta)\neq \emptyset\}\tag{*}$$ is dense. Such $a$ satisfying the property above would have $\gamma\leq\sup(a\cap \delta)<\delta$ by $cf(\delta)\geq \kappa$.

For arbitrary $T$ in the forcing with stem $s$, we notice that $\{a\mid s\frown a\in T\}\in U$ contains a set $a^*$ that contains $\gamma$, that's because $\{a\mid \gamma\in a\}\in U$. Let $T'$ be the subtree of $T$ with stem $s\frown a^*$. This tree witnesses ($*$) property.

**Claim 10.24.1 (Analogue of Prikery Lemma for supercompact tree forcing)**
**For all $T$ and formula $\varphi(\tau_1\dots \tau_n)$, there is $T'\leq T$ with the same stem that decides the formula.**

Proof of Claim, For a tree $T$ in the forcing with stem $s$, we use the notation $(s,T)$ to make explicit its stem. For condition $(s,T)$, define as in proof of Claim 10.7 $F:[X]^{<\omega}\to 3$ as follows: $$F(s') = \begin{cases}
0 & \text{if there is no }T' \text{ s.t. }(s\cup s',T') \text{ decides }\varphi\\
1 & \text{if there is }T' \text{ s.t. }(s\cup s',T') \text{ forces }\varphi\\
2 & \text{if there is }T' \text{ s.t. }(s\cup s',T') \text{ forces }\neg\varphi
\end{cases}
$$
By definability of forcing, $F\in V$ and thus by Rowbottom's theorem there is $Y\in U$ s.t. for each $n\in \omega$, $F$ is constant on $[Y]^{n}$.

Let $(s,T')$ be the subtree of $(s,T)$ defined recursively satisfying if $a\in succ_T(b)$, then $$a\in T'\iff a\in succ_{T'}(b)\cap Y$$ 
$(s,T')$ is the subtree of $(s,T)$ slimed at every node by $Y$. 

We show that $(s,T')$ decides $\varphi$. If not, then there is $(b_1,T_1),(b_2,T_2)\leq (s,T')$ s.t. $(b_1,T_1)\Vdash \varphi$ while $(b_2,T_2)\Vdash \neg\varphi$. May assume $|b_1| = |b_2| = |a|+n$. But by design $b_1\setminus a,b_2\setminus a\in [Y]^n$ while $F(b_1\setminus a)\neq F(b_2\setminus a)$. This is a contradiction. $\Box$

**Proof of $V_\kappa= V_\kappa^{V[G]}$:** This is similar to Lemma 10.6. In the final step we take $q = (a,\bigcap_{\xi<\lambda}T_\xi)$, $\bigcap_{\xi<\lambda}T_\xi$ is still a valid tree by $<\kappa$ completeness of the ultrafilter. $\Box$


---
## Problem 10.25
Assume for contradiction that $E_0>_ME_1>_ME_2\dots$. Consider the following iteration tree where $<_T: = \{0\}\times \mathbb{N}^+$, $M_0 = V$, $M_{n+1} = Ult(M_0,E_n)$. As $E_n\in M_n$ by definition of Mitchell order, this is a one-level, infinitely branching iteration tree. This contradicts Theorem 10.74 as there is no infinite branch in this tree. $\Box$