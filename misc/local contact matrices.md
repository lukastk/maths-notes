# Local contact matrices

Here we consider a method by which to construct local contact matrices from national contact matrices. Let $C_{ij}$ be the contact matrix for the UK, and $C_{ij}^\ell$ the contact matrix for place $\ell$ in the UK.

For both contact matrices the consistency relation

$$
\begin{aligned}
N_{i} C_{ij} & = N_j C_{ji} \\
N_i^\ell C^\ell_{ij} & = N_j^\ell C_{ij}^\ell
\end{aligned} \quad (1)
$$

must be satisfied.

There are two things we want to consider in the construction of $C_{ij}^\ell$:

1. Eq. 1 must hold for all $\ell$.
2. Contact should scale with population density.

### 1. Satisfying the local consistency relations

We let

$$
C^\ell_{ij} = \frac{f_j^\ell}{f_j} C_{ij} \quad (2)
$$

where $f_j = N_j / N$ and $f_j^\ell = N^\ell_j / N$.

Eq. (2) is consistent with Eq. (1):

$$
\begin{aligned}
N_i^\ell C^\ell_{ij} & = N_j^\ell \frac{f^\ell_i}{f_i} C_{ji} \\
& = N_j^\ell C_{ji}^\ell
\end{aligned}
$$

where we used (1) and (2).

Eq. 2 is easy to interpret. For example if the proportion of children in London is twice as many as in the UK overall, then Eq. 2 says that all age groups will have twice as many contacts with children in London.

### 2. Density-dependence of the contact matrix

Let $g(\rho^\ell\ |\ \rho)$ be a function of the local population density $\rho^\ell = N^\ell / A^\ell$, where $\rho = N / A$ is the UK population density. From now on we will suppress the $\rho$ parameter in $g$.

We let all contacts scale with $g$:

$$
C^\ell_{ij} = g(\rho^\ell) \frac{f_j^\ell}{f_j} C_{ij}
$$



If we assume a linear density-dependence $g

$$
C_{ij} = \frac{1}{N_i} \sum_\ell N^\ell_i C_{ij}^\ell \quad (2)
$$


$$
g(\rho^\ell) = \frac{\rho^\ell}{\rho}
$$


<!--stackedit_data:
eyJoaXN0b3J5IjpbNjYxMzk2MTI0LC0yMTI2MjUwNTMsLTIwNT
k4NjM1MzYsNzI5MzMzMDQ3XX0=
-->