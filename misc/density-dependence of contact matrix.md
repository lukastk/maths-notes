### Simple (and rough) method to estimate density-dependence of local contact matrices

Let $C_{ij}$ be the national contact matrix for the UK. We assume that at location $\ell$, the local contact matrix $C^\ell_{ij}$ scales as

$$
C^\ell_{ij} = \frac{\rho^\ell}{\bar{\rho}} C_{ij}
$$

where $\rho^\ell = N^\ell / A^\ell$ is the local population density and $\bar{\rho}$ is a "characteristic" local density yet to be determined.

Recall that $C_{ij}$ is the *average* number of people from age class $j$ that people from $i$ meet during a day. Therefore $C_{ij}$ and $C^\ell_{ij}$ should be related as

$$
C_{ij} = \frac{ \sum_\ell N^\ell_i C_{ij}^\ell}{ N_i}
$$

where $N^\ell$ is the population at $\ell$ and $N$ the total UK population.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU2MjY1ODQwOCwxMDI0NTczMDEyXX0=
-->