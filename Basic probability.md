# Basic Probability

## Basic definitions

**Def:** A *probability space* is a triplet $(\Omega, \mathcal{A}, P)$ where $\Omega$ is the sample space, $\mathcal{A}$ is $\sigma$-algebra of events (en *event* is a subset of $\Omega$). $P$ is a probability measure on $\mathcal{A}$.

**Def:** A set $\mathcal{A}$ is a $\sigma$-algebra of $\Omega$ if

1. $\Omega \in \mathcal{A}$
2. $A^c = \Omega  / A \in \mathcal{A} \quad \text{if}\ A \in \mathcal{A}$
3. $\cup_{n=1}^\infty A_n \in \mathcal{A} \quad \text{if}\ A_n \in \mathcal{A}$

**Def:** A function $P: \mathcal{A} \to [0,1]$ is a *probability measure* if

1. $P(\Omega) = 1$
2. $P(A^c)=1 - P(A)$
3. $P\left(\cup_{n=1}^\infty A_n \right) = \sum_{n=1}^\infty P(A_n) \quad \text{if}\ A_i \cap A_j = \emptyset\ \text{for}\ i = \not j$

If $P(A) =1$ for some $A \in \mathcal{A}$, then we say that the event $A$ occurs *almost surely* (a.s).

**Def:** Conditional probability

$$P(A|B) = \frac{P(A \cap B)}{P(B)}$$

**Def:** A function $X : \Omega \to \mathbb{R}$ is a *random variable* of the triplet $(\Omega, \mathcal{A}, P)$ if its information content is appropriately restricted, that is if

$$ \{ \omega \in \Omega : X(\omega) \leq a \} $$

is an event for each $a \in \mathbb{R}$. Then we call the function $F_X : \mathbb{R} \to \mathbb{R}$

$$ F_X(x) = P_X( (-\infty, x)) = P( \{ \in \Omega : X(\omega) \leq x\} ) $$

the *distribution function* of $X$.

**Def:** The indication function $I_A$ of an event $A$ is defined as

$$ I_A (\omega) = \begin{cases} 0 & : & \omega = \not A \\
1  & : & \omega \in A \end{cases} $$

and its distribution function is then

$$ F_{I_A} (x) = \begin{cases} 
0 & : & x < 0 \\
P(A) & : & 0 < x < 1 \\
1 & : & 1 < x
 \end{cases} $$

**Def:** $X$ is a *continuous random variable* if $P(\{\omega \in \Omega : X(\omega) = x\})=0$ for each $x \in \mathbb{R}$. In this case $F_X$ is often differentiable, and there exists a density function $p$ s.t

$$ F_X(x) = \int_{-\infty}^x p(s) ds \quad \forall x \in \mathbb{R} $$

**Def:** The *mean* is defined as

$$ \mathbb{E}[X] = \sum_i p_i x_i \quad \text{where}\ p_i = P(X= x_i)$$

or 

$$ \mathbb{E}[X] = \int_{-\infty}^\infty p(x) x\ dx$$

for continuous random variables. We often denote $\mu = \mathbb{E}[X]$ and $\sigma^2 = \text{Var}[X] = \mathbb{E}[ (X - \mu)^2 ]$.

**Def:** The *p*th moment of a random variable is $\mathbb{E}[X^p]$.

**Def:** The *p*th central moment of a random variable is $\mathbb{E}[(X-\mu)^p]$.

For a Gaussian random variable, we have

$$
\begin{aligned}
& \mathbb{E}[ (X - \mu)^{2k+1}]  = 0 \\
& \mathbb{E}[ (X - \mu)^{2k}] = \sigma^{2k} (2k-1)!!
\end{aligned}
$$

for all $k \in \mathbb{Z_+}$. So a Gaussian random variable is completely determined by $\mu$ and $\sigma$.

**Def:** The *covariance* of two random variables $X_1$ and $X_2$ is

$$\text{Cov}[X_1, X_2] = \mathbb{E}[X_1 X_2]$$

**Def:** $X_1$ and $X_2$ are *independent* if

$$
\begin{aligned}
& \text{Cov} = \mathbb{E}[X_1 X_2] = \mathbb{E}[X_1] \mathbb{E}[X_2] \\
& \text{Var}(X_1 + X_2) = \text{Var}(X_1) + \text{Var}(X_2)
\end{aligned}
$$

## Convergence of random sequences

We often have an infinite sequence $X_1, X_2, \dots, X_n, \dots$ of random variables, and are interested in its asymptotic behaviour. That is, we are interested in the existence of a random variable $X$ which is the limit of $X_n$ for $n\to \infty$, in some sense.

### Types of convergences

There are several different ways in which such a convergence can be defined. Roughly, these fall into a *weak* and a *strong* class of convergences. The latter requires $X_n$ so converge onto $X$ in some sense, and the former only their probability distributions do.

#### Strong class of convergences

**Def:** *Convergence with probability one* (or *almost sure convergence*):

$$P\left(
\left\{ \omega \in \Omega : \lim_{n\to\infty} | X_n(\omega) - X(\omega) | = 0 \right\}
\right) = 1$$

**Def:** *Mean-square convergence*: $\mathbb{E}[|X_n|^2] < \infty$ for $n = 1,2,\dots$, $\mathbb{E}[|X|]^2 < \infty$ and

$$ \lim_{n\to\infty} \mathbb{E} [ |X_n - X|^2 ] = 0 $$

**Def:** *Strong convergence*: $\mathbb{E}[|X_n|] < \infty$ for $n = 1,2,\dots$, $\mathbb{E}[|X|] < \infty$ and

$$ \lim_{n\to\infty} \mathbb{E} [ |X_n - X|] = 0 $$


By the Lyapunov inequality

$$ \mathbb{E}(|Y|) \leq \sqrt{\mathbb{E}(|Y|^2)}$$

we see that mean-square convergence implies strong convergence. 

#### Weak class of convergences

For the class of weaker convergences we do not need to know the actual random variables, just their distribution functions.

**Def:** *Convergence in distribution* (or *convergence in law*):

$$ \lim_{n \to \infty} F_{X_n}(x) = F_X(x) \quad \text{at all continuity points of}\ F_X $$

**Def:** *Weak convergence*:

$$ \lim_{n\to\infty} \int_{-\infty}^\infty f(x) dF_{X_n}(x) = \int_{-\infty}^\infty f(x) dF(x) $$

for all *test functions* $f : \mathbb{R} \to \mathbb{R}$.

### Law of large numbers

Given a sequence of independent identically distributed (i.i.d) random variables $X_1, X_2, \dots$, satisfying $\mu = \mathbb{E}[X_n]$ and $\sigma^2 = \text{Var}[X_n]$. From independence the averaged random variables

$$A_n = \frac{1}{n} S_n = \frac{1}{n} \sum_{i=1}^n X_i$$

also have mean $\mathbb{E}[A_n] = \mu$ and variance $\text{Var}[A_n] = \sigma^2 / n$. The *Law of Large Numbers$ say that

$$ A_n \to \mu \quad \text{as} \quad n \to \infty$$

with the convergence taken in the *mean-square* sense.

### Central limit theorem



## References
- Numerical Solutions of SDEs Through Computer Experiments - Kloeden, Platen, Schurz. Chapter 1.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjI1NjY0MTc5XX0=
-->