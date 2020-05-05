### Simple ad-hoc way to estimate the density-dependence of local contact matrices

Let $C_{ij}$ be the national contact matrix for the UK. Let $\ell=1,\dots,L$ be an index over all geographical locations of the UK, and let $C^\ell_{ij}$ be a local contact matrix.

Let $C_i^\ell$ be the total number of people that people of age-class $i$ at location $\ell$ meet any other age-class per day. In other words $C^\ell_i = \sum_j C^\ell_{ij}$. Let us assume that this rate is proportional to the population density of $\ell$, in other words

$$
C_i^\ell = \frac{\rho^\ell}{f_i} C_i
$$

where $\rho^\ell = N^\ell / A^\ell$ is the local population density and $f_i$ is a local density characteristic to $i$ yet to be determined. We

We assume that at location $\ell$, the local contact matrix $C^\ell_{ij}$ scales as

$$
C^\ell_{ij} = \frac{\rho_i^\ell}{\bar{\rho}_i} C_{ij} \quad (1)
$$

where $\rho_i^\ell = N_i^\ell / A^\ell$ is the local population density of age group $i$ and $\bar{\rho}_i$ is a "characteristic" local density yet to be determined. We've made the assumption that the rate at which 

Recall that $C_{ij}$ is the *average* number of people from age class $j$ that people from $i$ meet during a day. Therefore $C_{ij}$ and $C^\ell_{ij}$ should be related as

$$
C_{ij} = \frac{ \sum_\ell N^\ell_i C_{ij}^\ell}{ N_i} \quad (2)
$$

where $N^\ell_i$ is the population of age class $i$ at $\ell$ and $N_i$ the total UK population of age class $i$.

Eq. 1 and 2 are compatible with each other iff

$$
\bar{\rho}_i = \frac{1}{N_i} \sum_\ell N_i^\ell \rho_i^\ell
$$
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE3MTUzMjc1MSw2ODAzMjE3ODIsODcyOD
I2ODUyLC0yNjcxMjU2NjgsLTEzNzk3NDY4MTgsNTcyNzY5Nzg3
LDEwMjQ1NzMwMTJdfQ==
-->