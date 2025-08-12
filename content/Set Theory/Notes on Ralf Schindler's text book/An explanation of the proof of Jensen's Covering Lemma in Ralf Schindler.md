---
title: An explanation of the proof of Jensen's Covering Lemma in Ralf Schindler
draft: false
tags: 
date:
---
Here we try to make explicit some skipped details in the proof of theorem 11.56 on page 264 - 268.

---
#### Why it suffice to prove that for arbitrary $\pi:\bar{H}\to H_\mu$ where $\mu\geq \theta$, it holds that $ran(\pi)\cap \mu\in L$.

We show that if for arbitrary $\pi:\bar{H}\to H_\mu$ where $\mu\geq \theta$, it holds that $ran(\pi)\cap \mu\in L$, then $L\cap [\theta]^\kappa$ is stationary in $[\theta]^\kappa$.

Notice the subtle difference between the definition of stationary set on $[\theta]^{\kappa}$ in this book (Definition 4.39 page 45) and the standard definition like in Jech Definition 8.21. We have $S\subseteq [\theta]^{\kappa}$ is stationary in $[\theta]^\kappa$ in the sense of this book iff $S$ meets every closed unbounded set in $[\theta]^{<\kappa^+}$.

Pick arbitrary club $C\subseteq [\theta]^{<\kappa^+}$ where $\theta\geq \kappa$ and $\kappa\geq \aleph_1$. We argue that $C\cap L\neq \emptyset$. 
Pick some $X\in C$, we subsequently define $X_n$ where $X_0 = X$, $X_{n+1} \supseteq h_{H_\mu}(X_n)\cap \mu$ s.t. $X_{n+1}\in C$. We take $X = \bigcup_n X_n$ and $N = \bigcup h_{H_\mu}(X_n)$. We have by the the regularity of $\kappa\geq \aleph_1$, $X\in C$ and $N\prec H_\mu$.

It turns out that $$N = h_{H_\mu}(X)$$
If $x\in h_{H_\mu}(X_n)$ for some $n$, then $x\in X_{n+1}\subseteq X\subseteq h(X)$. On the other hand, if $x\in h_{H_\mu}(X)$, let $F$ be the Skolem function s.t. $h_{H_\mu}(X) = \bigcup_n F^n[X]$, then it is easy to show that $F^n[X]\subseteq N$ for all $X$ since every element in $F^n[X]$ depends on only finitely many elements in $X$ and thus is already included in some $h_{H_\mu}(X_m)$.

Moreover it follows that $$X = h_{H_\mu}(X)\cap \mu$$
and let $\pi:\bar{H}\to h_{H_\mu}(X)$ be the inverse of the collapse and it follows that $X = h_{H_\mu}(X)\cap \mu = ran(\pi)\cap \mu\in L$. And thus $L\cap C\neq \emptyset$. $\Box$


---
#### Page 264
**The first formula:** Here the superscript $\pi$ and the subsequent superscripts $\pi$ are intended to indicate that the $\kappa^\pi_i$, $\alpha^\pi$ etc. here depend on the map $\pi$. And $\pi$ is arbitrary.

**Line 5 If $\beta_i<\infty$, then $\rho_\omega(J_{\beta_i})<\kappa_i$ and $\rho_\omega(J_{\beta})\geq \kappa_i$ for all $\beta\in [\kappa_\alpha,\beta_i)$**
If $\kappa_i$ ceases to be a cardinal in $J_{\beta_i+\omega}$, then there is $\delta<\kappa_i$, $f:\delta\to \kappa_i$ surjective added to $J_{\beta_i+\omega}$. The function can be definably coded as a subset of $\kappa_i$, hence $$\mathcal{P}(\kappa_i)\cap J_{\beta_{i}+\omega} \setminus J_{\beta_{i}}\neq \emptyset$$This entails  and Lemma 5.15 and Lemma 11.27 that $\boldsymbol{\Sigma}^{J_{\beta_i}}_n\not\subseteq J_{\beta_i}$, by soundness of $J_\beta$,  $\kappa_i\geq \rho_\omega(J_{\beta_i})$. If $\kappa_i = \rho_\omega(J_{\beta_i})$, then $\kappa_i = \rho_{n}(J_{\beta_i})$ for any $n$ large enough, by generalizing Lemma 11.5, there is no $\boldsymbol{\Sigma}^{J_{\beta_i}}_\omega$ partial map from from $\gamma<\kappa_i$ onto $\kappa_i$. by Lemma 5.15 there is no such map in $J_{\beta_i+\omega}$. This concludes the proof that $\rho_\omega(J_{\beta_i})<\kappa_i$.

If $\beta<\beta_i$, then $\kappa_i$ is still a cardinal in $\beta+\omega$.

**Line 7 If $i\leq j$ then $\beta_i\leq \beta_j$.**

It suffice to show that in $J_{\beta_{i}+\omega}$, $\kappa_j$ is not a cardinal. Since a function $f:\delta\to \kappa_i$ for $\delta<\kappa_i$ can be coded as a subset of $\kappa_i$, we have $\mathcal{P}(\kappa_i)\cap J_{\beta_{i}+\omega} \setminus J_{\beta_{i}}\neq \emptyset$, this means that there is surjective $g:\kappa_i\to \beta_i$ in $J_{\beta_i+\omega}$ by acceptability, thus $|\kappa_i|^{J_{\beta_i+\omega}} = |\kappa_j|^{J_{\beta_i+\omega}} = |\beta_i|^{J_{\beta_i+\omega}}$. This concludes the proof.


