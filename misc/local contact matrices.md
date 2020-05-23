# Local contact matrices

Here we consider a method by which to construct local contact matrices from national contact matrices. Let $C_{ij}$ be the contact matrix for the UK, and $C_{ij}^\ell$ the contact matrix for place $\ell$ in the UK.

For both contact matrices the consistency relation

$$
\begin{aligned}
N_{i} C_{ij} & = N_j C_{ji} \\
N_i^\ell C^\ell_{ij} & = N_j^\ell C_{ij}^\ell
\end{aligned} \quad (1)
$$

must be satisfied. We also must have that the local contact matrices correspond to the national one via the averaging procedure:

$$
C_{ij} = \frac{1}{N_i} \sum_\ell N^\ell_i C_{ij}^\ell \quad (2)
$$

There are three things we want to consider in the construction of $C_{ij}^\ell$:

1. Eq. 1 must hold for all $\ell$.
2. 2.
3. Contact should scale with population density.

### 1. Satisfying the local consistency relations

We let

$$
C^\ell_{ij} = \frac{f_j^\ell}{f_j} C_{ij} \quad (3)
$$

where $f_j = N_j / N$ and $f_j^\ell = N^\ell_j / N$.

Eq. (3) is consistent with Eq. (1):

$$
\begin{aligned}
N_i^\ell C^\ell_{ij} & = N_j^\ell \frac{f^\ell_i}{f_i} C_{ji} \\
& = N_j^\ell C_{ji}^\ell
\end{aligned}
$$

where we used (1) and (3).

Eq. 3 is easy to interpret. For example if the proportion of children in London is twice as many as in the UK overall, then Eq. 3 says that all age groups will have twice as many contacts with children in London.

### 2. Density-dependence of the contact matrix

Let $g(\rho^\ell)$ be a function of the local population density $\rho^\ell = N^\ell / A^\ell$.

We let all contacts scale with $g$:

$$
C^\ell_{ij} = g(\rho^\ell) \frac{f_j^\ell}{f_j} C_{ij} \quad (4)
$$

as $g$ is a scalar, Eq. 1 remains satisfied. Although the scaling must be chosen such that Eq. 2 is satisfied as well.

Let's assume a linear density-dependence $g(\rho^\ell) = \rho^\ell / a$, and use Eq. 2 to find $a$.

$$
\begin{aligned}
& C_{ij} = \frac{1}{N_i} \sum_\ell N_i^\ell C_{ij}^\ell  = \frac{1}{N_i} \sum_\ell N_i^\ell \frac{\rho^\ell}{a} \frac{f_i^\ell}{f_i} C_{ij} \\
\Rightarrow\ & \sum_{\ell} \left[ N_i^\ell \rho^\ell \frac{f_i^\ell}{f_i} - a N_i^\ell \right] = 0 \\
\Rightarrow\ & a = \frac{1}{N_i} \sum_\ell  N_i^\ell  \rho^\ell \frac{f_i^\ell}{f_i}
\end{aligned}
$$

We get

$$
a = \rho \left( \frac{1}{N_i^2} \sum_\ell {N_i^\ell}^2 \right)
$$
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQwMDI0MzY1NCw5MTQ5NDEyLC0yMTI2Mj
UwNTMsLTIwNTk4NjM1MzYsNzI5MzMzMDQ3XX0=
-->