### Simple/simplistic method to estimate density-dependence of local contact matrices

Let $C_{ij}$ be the national contact matrix for the UK. Let $\ell=1,\dots,L$ be an index over all geographical locations of the UK. We assume that at location $\ell$, the local contact matrix $C^\ell_{ij}$ scales as

$$
C^\ell_{ij} = \frac{\rho_i^\ell}{\bar{\rho}_i} C_{ij} \quad (1)
$$

where $\rho_i^\ell = N_i^\ell / A^\ell$ is the local population density of age group $i$ and $\bar{\rho}_i$ is a "characteristic" local density yet to be determined.

Recall that $C_{ij}$ is the *average* number of people from age class $j$ that people from $i$ meet during a day. Therefore $C_{ij}$ and $C^\ell_{ij}$ should be related as

$$
C_{ij} = \frac{ \sum_\ell N^\ell_i C_{ij}^\ell}{ N_i} \quad (2)
$$

where $N^\ell_i$ is the population of age class $i$ at $\ell$ and $N_i$ the total UK population of age class $i$.

Eq. 1 and 2 are compatible with each other iff

$$
\bar{\rho} = 
$$

so we set

$$
C^\ell_{ij} = \frac{\rho^\ell}{L} C_{ij}
$$
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTIxNzc0NzgzNiwtMjY3MTI1NjY4LC0xMz
c5NzQ2ODE4LDU3Mjc2OTc4NywxMDI0NTczMDEyXX0=
-->