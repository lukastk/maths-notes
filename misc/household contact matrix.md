## Household contact structure

- $\mu^F_i\ \sigma^F_i \sim$ the mean and variance of the number of people of age-bracket $i$ of the average household.
- $(C_H)_{ij} \sim$ the home contact matrix
- $(C_E)_{ij} = C_{ij} - (C_H)_{ij} = (C_W)_{ij} + (C_S)_{ij} + (C_O)_{ij} \sim$ non-home contact matrix.

A tilde over a contact matrix signifies that we are using the symmetrised form: $\tLilde{C}_{ij} = N_i C_{ij}$. 

Algorithm:

1. Generate $M$ households, indexed by $\mu = 1,\dots, M$. The number of people of age-group $i$ in household $\mu$ is given by $N^\mu_i$.
	1. $M$ is given by: $M = N_i / \mu_i^F$.
	2. The populations are taken from the distribution. $$ N^\mu_i = \mathcal{N}(\mu_i^F, \sigma_i^F)$$ 
2. Construct the household contact matrix $C_{ij}^{\mu \nu}$. For each household $\mu$:
	1. Decide the number of interactions of age-group $i$ in household $\mu$ between age-group $j$ in other households:
		- Let $m =  (\tilde{C}_E)_{ij} - \sum_{\nu\neq\mu} \tilde{C}_{ij}^{\mu \nu}$, which is the number of contacts that age-group $i$ in household $\mu$ have with people in age-group $j$ in other households. 
		- Draw a number $n = \mathcal{N}( m, \sigma)$.
		- Randomly pick $n$ households $\{\nu_1, \dots \nu_n\}$ (duplicates are allowed). To promote social clustering, we can increase the probability that a household $\nu$ is chosen, if $\mu$ and $\nu$ have shared contacts already.
		 - Generate the random probability vector $\mathbf{p}$ of length $n$, which satisfies $\sum_k p_{\nu_k} = 1$ and where each element is picked from a uniform distribution over $[0,1]$.
		 - Update $\tilde{C}^{\mu \nu}_{ij}$ as follows: $$ \tilde{C}_{ij}^{\mu \nu_k} := \tilde{C}_{ij}^{\mu \nu_k}+ m p_{\nu_k}  $$ 
	2. For $\mu = \nu$, we set $C_{ij}^{\mu \mu}$ equal to the home contact matrix, adjusting the matrix elements such that consistency relations are satisfied.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgzMDY2MjYxOSwtOTM0MzU5NTM3LC0xNj
U3MjIyODA0LC0xOTcyMjMyNDM4LC0xOTc5ODc3MTgyXX0=
-->