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

**Def:** Random variable

### References
- Numerical Solutions of SDEs Through Computer Experiments - Kloeden, Platen, Schurz. Chapter 1.
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDM2OTg1MTc0XX0=
-->