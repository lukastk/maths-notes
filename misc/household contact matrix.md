## Household contact structure

- $\mu^F_i\ \sigma^F_i \sim$ the mean and variance of the number of people of age-bracket $i$ of the average household.
- $(C_H)_{ij} \sim$ the home contact matrix
- $(C_E)_{ij} = C_{ij} - (C_H)_{ij} = (C_W)_{ij} + (C_S)_{ij} + (C_O)_{ij} \sim$ non-home contact matrix.

A tilde over a contact matrix signifies that we are using the symmetrised form: $\tilde{C}_{ij} = N_i C_{ij}$. 

Algorithm:

1. Generate $M$ households, indexed by $\mu = 1,\dots, M$. The number of people of age-group $i$ in household $\mu$ is given by $N^\mu_i$.
	2. $M$ is given by: $M = N_i / \mu_i^F$.
	3. The populations are taken from the distribution. $$ N^\mu_i = \mathcal{N}(\mu_i^F, \sigma_i^F)$$ 
2. FOr
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjAzNTg1MDE1Nl19
-->