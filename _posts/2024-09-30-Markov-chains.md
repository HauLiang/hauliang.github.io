---
title: 'Summary of Markov Chains (2024)'
date: 2024-09-30
excerpt: "Here’s a summary of key points about <b>Markov Chains</b>."
permalink: /read-list/2024/markov-chains/
tags:
  - Stochastic Process
  - Markov Chains
---

# Markov Chains

> [1] Ross S M. Stochastic processes[M]. John Wiley & Sons, 1995.
>
> [2] 张波, 商豪. 应用随机过程 (第四版)[M]. 中国人民大学出版社, 2016.
>
> [3] Levin D A, Peres Y. Markov chains and mixing times[M]. American Mathematical Soc., 2017.

<!-- <hr style="height:0px;border:none;border-top:3px solid #555555;" />

Emm... It seems that this Markdown file isn't displaying correctly on this GitHub.io Pages. You can download it from the "./_posts/" folder and view it locally using a Markdown reader.

<hr style="height:0px;border:none;border-top:3px solid #555555;" /> -->

## 1. Preliminary

**(1) Markov chain (马尔可夫链):**

Consider a stochastic process $$\begin{equation*}\left\{X_n,n=0,1,2,...\right\}\end{equation*}$$ that takes on a finite or countable number of possible values. If such a stochastic process is a Markov chain, then for all $n\ge0$ and all states $i_0,i_1,...,i_{n-1},i,j$, 

$$
\begin{equation*}
\begin{aligned}
&P\left\{X_{n+1}=j \mid X_n=i, X_{n-1}=i_{n-1}, \cdots, X_1=i_1, X_0=i_0\right\}\\
=&P\left\{X_{n+1}=j \mid X_n=i\right\}
\end{aligned}
\end{equation*}
$$

**(2) Transition probability (转移概率)**

The condition probability, $$\begin{equation*}
P\left\{X_{n+1}=j \mid X_n=i\right\}\end{equation*}$$, is called the (one-step) transition probability, denoted as $p_{ij}$. The value $p_{ij}$ represents the probability that the process will, when in state $i$, next make a transition into state $j$.

**(3) Time homogeneity (时齐性)**

If the transition probability depends only on $i$ and $j$, and not on $n$, it is called a time-homogeneous Markov chain. Otherwise, it is called non-time-homogeneous.

**(4) Finite chain (有限链)**

When the Markov chain has a finite number of states, it is called a finite chain.

**(5) The matrix of transition probabilities $\pmb{P}$ (转移概率矩阵)**

$$
\begin{equation*}
P = \left[\begin{array}{cccc}
p_{00} & p_{01} & p_{02} & \cdots \\
p_{10} & p_{11} & p_{12} & \cdots \\
\vdots & \vdots& \vdots& \vdots\\
p_{i0} & p_{i1} & p_{i2} & \cdots \\
\vdots & \vdots & \vdots& \vdots
\end{array}\right]
\end{equation*}
$$

We have: 

(i) $p_{ij}\ge0, \ i,j\ge0$, 

(ii) $\sum_{j=0}^\infty p_{ij}=1,\ i=0,1,...$


## 2. Chapman-Kolmogorov Equations

**(1) $n$-step transition probability ($n$步转移概率)**

The probability

$$
\begin{equation*}
p_{ij}^{(n)} = P\left\{X_{m+n}=j \mid X_m=i\right\}, \ i,j\ge 0, \ m\ge 0, \ n\ge 1
\end{equation*}
$$

is called the $n$-step transition probability of the Markov chain, and $P^{(n)}=(p_{ij}^{(n)})$ is called the matrix of $n$-step transition probabilities.

Additionally, it is stipulated that

$$
\begin{equation*}
p_{ij}^{(0)} =\begin{cases}0, & i \neq j \\ 1, & i=j\end{cases}
\end{equation*}
$$

The $n$-step transition probability refers to the probability that the system transitions from state $i$ to state $j$ after $n$ steps, without any requirements on the states passed during the intermediate $n-1$ steps.

**(2) C-K equations**

For all $n,m\ge0$, $i,j\ge 0$, we have
(i) $p_{ij}^{(m+n)}=\sum_{k=0}^{\infty} p_{ik}^{(m)} p_{kj}^{(n)}. $
(ii) $P^{(n)}=P\cdot P^{(n-1)}=P\cdot P\cdot P^{(n-2)}=\cdots=P^{n}.$



## 3. Classification of States

### Outline:

$$
\begin{cases} \text{Reducible (可约)/Irreducible (不可约)} \\ \text{Periodic (周期)/Aperiodic (非周期)} \\ \text{Recurrent (常返)/ Transient(非常返)} \begin{cases} \text{Positive recurrent (正常返)} \\ \text{Null recurrent (零常返)} \end{cases} \end{cases}
$$

$$
\text{Positive recurrent (正常返)}+\text{Aperiodic (非周期)}\rightarrow \text{Ergodic (遍历)}
$$

**(1) Communicate (互通)**

State $j$ is said to be accessible (可达) from state $i$ if for some $n\ge0$, $p_{ij}^{(n)}>0$. Two states $i$ and $j$ accessible to each other are said to communicate, and we write $i\leftrightarrow j$.

- Communication is an equivalence relation, that is 

  $$
  \begin{cases}
  (i) \ \ \ 自返性:  i\leftrightarrow i\\
  (ii)\ \ \ 对称性: \text{If } \  i \leftrightarrow j, \text{ then } j\leftrightarrow i   \\
  (iii) \ \  \ 传递性:\text{If } \ i \leftrightarrow j \text{ and } j \leftrightarrow k, \text{ then } i\leftrightarrow k
  \end{cases}
  $$

**(2) Class (类)**

Two states that communicate are said to be in the same class, and any two classes are either disjoint or identical.

**(3) Reducible/ Irreducible (可约/不可约)**

We say that the Markov chain is irreducible if there is only one class, that is, if all states communicate with each other.

**(4) Periodic/Aperiodic (周期/非周期)**

The greatest common divisor, $d=d(i)$, of the set, $\{n:n\ge1,p_{ii}^{(nd)}>0\}$, is the period.

$$
\begin{cases}
\text{If this set is equal to } \varnothing \text{ , then } d(i)=+\infty \text{ (aperiodic)}\\
\text{If this set is not equal to } \varnothing \begin{cases} d=1, i \text{ is aperiodic}\\ d>1, i \text{ is periodic with period } d(i)\end{cases}
\end{cases}
$$

- The periodicity is a class property, which means that if $i\leftrightarrow j$, then $d(i)=d(j)$.

**(5) First transition probability (首达概率)**

For any states $i$ and $j$ define $f_{ij}^{(n)}$ to be the probability that, starting in $i$, the first transition into $j$ occurs at time $n$, i.e.,

$$
\begin{equation*}
\begin{aligned}
f_{ij}^{(0)} &= \delta_{ij} = \begin{cases}0, & i \neq j \\ 1, & i=j\end{cases} \\
f_{ij}^{(n)} &= P\{X_n = j, X_k \neq j, k=1,2,\cdots,n-1|X_0=i\}, \ n\ge1
\end{aligned}
\end{equation*}
$$

**(6) Recurrent/ Transient (常返/非常返)**

Let $f_{ij}=\sum_{n=1}^\infty f_{ij}^{(n)}, n\ge 1$, it means that the probability of reaching state $j$ starting from state $i$.

$$
\begin{cases}
\text{If } f_{jj} = 1 \text{ , then state $j$ is said to be recurrent}\\
\text{If } f_{jj} < 1 \text{ , then state $j$ is said to be transient}
\end{cases}
$$

**(7) Positive recurrent/ Null recurrent (正常返/零常返)**

For the recurrent state, we define $\mu_i=\sum_{n=1}^{\infty}nf_{ii}^{(n)}$.

Notes: Let $T_i$ denote the number of steps required to return to $i$ for the first time, starting from $i$, then  $\mu_i=E[T_i]$.

The $\mu_i$ means the average number of steps (time) required to return to $i$ starting from $i$ / the mean first return time.

$$
\begin{cases}
\text{If } \mu_{i} < +\infty \text{ , then state $i$ is said to be positive recurrent}\\
\text{If } \mu_{i} = +\infty \text{ , then state $i$ is said to be null recurrent (shares many similar properties with transient states)}
\end{cases}
$$

**(8) Ergodic (遍历)**

Ergodic state 
$$
\begin{equation*}
\begin{cases}
\text{Positive recurrent}\\
\text{Aperiodic}
\end{cases}
\end{equation*}
$$

If state $i$ is an ergodic state and $f_{ii}^{(1)}=1$, then $i$ is called an absorbing state, in which case it is clear that $\mu_i=1$.



## 4. Properties of States

- The state $i$ is recurrent $\iff$ $\sum_{n=0}^\infty p_{ii}^{(n)}=\infty$ (average round trips occur an infinite number of times)

  If a state $i$ is transient, then  $\sum_{n=0}^\infty p_{ii}^{(n)}=\frac{1}{1-f_{ii}}$

- The relationship between transition probability, $p_{ij}^{(n)}$, and the first transition probability, $f_{ij}^{(n)}$:

  For any states $i$, $j$, and $1\le n\le +\infty$, we have

  $$
  \begin{equation*}
  p_{ij}^{(n)}=\sum_{l=1}^{n}f_{ij}^{(l)}p_{jj}^{(n-l)}
  \end{equation*}
  $$

- If $i\leftrightarrow j$ and $i$ is recurrent, then $f_{ji}=1$.

- If $i$ is recurrent and $i\leftrightarrow j$, then $j$ is recurrent.

  Positive/Null recurrent is also a class property.



## 5. Limit Theorems

**(1) A basic limit theorem of the Markov chain:**

$$
\begin{equation*}
\lim_{n\rightarrow\infty} p_{ii}^{(nd)} = \begin{cases}
d/\mu_i, \text{ if $i$ is positive recurrent}\\
0, \text{ if $i$ is null recurrent ($\mu_i=\infty$)}   \\
0, \text{ if $i$ is tranisent}
\end{cases}
\end{equation*}
$$

**(2) The limiting property of $p_{ij}^{(n)}$:**

(i) If $j$ is null recurrent or transient, then for any $i\ge 0$, we have

$$
\begin{equation*}
\lim_{n\rightarrow\infty} p_{ij}^{(n)} = 0
\end{equation*}
$$

(ii) If $j$ is positive recurrent with period $d$, then for any $i\leftrightarrow j$, $i\ge0$, we have

$$
\begin{equation*}
\lim_{n\rightarrow\infty} p_{ij}^{(n)} = d/\mu_j 
\end{equation*}
$$

(iii) For any $i,j\ge0$, we have

$$
\begin{equation*}
\lim_{n\rightarrow\infty} \frac{1}{n}\sum_{k=1}^n p_{ii}^{(k)} = \begin{cases}
0, \text{ if $i$ is null recurrent or transient}   \\
d/\mu_i, \text{ if $i$ is positive recurrent}
\end{cases}
\end{equation*}
$$

**(3) Condition of positive recurrent:**

In a Markov chain with a finite number of states, it is not possible for all states to be transient, nor can there be any null recurrent states.

$$
\begin{equation*}
\text{A Markov chain with a finite number of states } \begin{cases}
\text{ not possible to have a null recurrent state}\\
\text{ may have a transient state}   \\
\text{ must have a positive state}
\end{cases}
\end{equation*}
$$

$\Rightarrow$ An irreducible finite Markov chain is positive recurrent.

​     If a Markov chain has one null recurrent state, then it must have infinitely many null recurrent states.



## 6. Stationary and Limiting Distribution

**(1) Stationary distribution**

A probability distribution $\{p_j,j\ge0\}$ is said to be stationary for the Markov chain if

$$
\begin{equation*}
p_j = \sum_{i=0}^\infty p_i\cdot p_{ij}
\end{equation*}
$$

**(2) Limiting distribution**

Markov chain is ergodic 

$$\begin{equation*}\begin{cases}
\text{ All states are communicating} \\
\text{ Aperiodic}   \\
\text{ All states are positive recurrent}
\end{cases}\end{equation*}$$

For an ergodic Markov chain, the limit

$$
\begin{equation*}
\lim_{n\rightarrow\infty}p_{ij}^{(n)}=\pi_j,j\ge0 \text{ (note that $\pi_j=1/\mu_j$)}
\end{equation*}
$$

is called its limiting distribution.

**(3) The relationship between these two distributions**

An irreducible aperiodic Markov chain belongs to one of the following two classes:

(i) Either the states are all transient or all null recurrent, in this case, there exists no stationary distribution

(ii) Or else, all states are positive recurrent (here this Markov chain is ergodic). Then, the limiting distribution

$$
\begin{equation*}
\pi_j=\lim_{n\rightarrow\infty}p_{ij}^{(n)}>0
\end{equation*}
$$

is a stationary distribution and there exists no other stationary distribution (unique).

**(4) Summary**

- finite + irreducible $\Rightarrow$ positive recurrent

- finite + aperiodic + irreducible $\Rightarrow$ ergodic

- ergodic $\Rightarrow$ unique stationary distribution = limiting distribution

  

## 7. Mixing Times

It is useful to introduce a parameter that measures the time required by a Markov chain for the distance to stationarity to be small. The mixing time is defined by

$$
\begin{equation*}
t_{\text {mix }}(\varepsilon):=\min \{t: d(t) \leq \varepsilon\},
\end{equation*}
$$

where

$$
\begin{equation*}
d(t):=\max _{x \in \mathcal{X}}\left\|P^t(x, \cdot)-\pi\right\|_{\mathrm{TV}} 
\end{equation*}
$$


## 8. Hitting Times

Given a Markov chain ($X_t$) with state space $\mathcal{X}$, it is natural to define the hitting time $\tau_A$ of a subset $A ⊆ \mathcal{X}$ by

$$
\begin{equation*}
\tau_A:=\min \left\{t \geq 0: X_t \in A\right\}
\end{equation*}
$$

We will often find it useful to estimate the worst-case hitting times between states in a chain. Define

$$
\begin{equation*}
t_{\text {hit }}:=\max _{x, y \in \mathcal{X}} \mathbf{E}_x\left(\tau_y\right)
\end{equation*}
$$


## 9. Cover Times

Let ($X_t$) be a finite Markov chain with state space $\mathcal{X}$. The cover time variable $\tau_{\text{cov}}$ of ($X_t$) is the first time at which all the states have been visited. More formally, $\tau_{\text{cov}}$ is the minimal value such that, for every state $y\in\mathcal{X}$, there exists $t \le \tau_{\text{cov}}$ with $X_t = y$.

We also define the cover time as the mean of $\tau_{\text{cov}}$ from the worst-case initial state

$$
\begin{equation*}
t_{\mathrm{cov}}=\max _{x \in \mathcal{X}} \mathbf{E}_x \tau_{\mathrm{cov}}
\end{equation*}
$$















