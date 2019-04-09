# Basic Probability

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

for continuous random variables. We often denote $\mu = \mathbb{E}[X]$ and $\sigma^2 = \text{Var}[$

### References
- Numerical Solutions of SDEs Through Computer Experiments - Kloeden, Platen, Schurz. Chapter 1.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY2OTkwMjk0NV19
-->