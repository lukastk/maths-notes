We have a contact matrix $C_{ij}$, satisfying

$$
N_i C_{ij} = N_j C_{ji} \quad (1)
$$

 from which we want to construct local contact matrices $C^\ell_{ij}$, which in turn must satisfy

$$
N_i^\mu C^\ell_{ij} = N_j^\ell C^\mu_{ji}, \quad (2)
$$

where $N^i_{\ell}$ is the population of age-group $i$ at location $\ell$. Furthermore, $C_{ij}$ and $C^\ell_{ij}$ must satisfy the consistency relation

$$
C_{ij} = \frac{1}{N_i} \sum_\ell N_i^\ell C_{ij}^\ell. \quad (3)
$$

In other words, the local contacts $C^\ell_{ij}$ must add up to the national contacts $C_{ij}$.

Let's define the symmetric contact matrix as $\tilde{C}_{ij} = N_i C_{ij}$, and $\tilde{C}^\ell_{ij} = N^\ell_i C^\ell_{ij}$, in which case (1) and (2) simply becomes symmetry conditions $\tilde{C}_{ij} = \tilde{C}_{ji}$ and $\tilde{C}^\ell_{ij} = \tilde{C}^\ell_{ji}$, and (3) becomes

$$
\tilde{C}_{ij} = \sum_\ell \tilde{C}^\ell_{ij}.
$$

The interpretation of $\tilde{C}_{ij}$ is the *total* number of contacts between age-group *i* and *j*. Eq. (3) is the statement that the total local contacts must add up to the total national contacts.

We now construct local contact matrices $\tilde{C}^\ell_{ij}$ such that (2) and (3) are satisfied. Note that (2) will remain satisfied as long as $\tilde{C}^\ell_{ij}$ is symmetric. How to do construct $\tilde{C}^\ell_{ij}$  is of course a matter of debate. We chose to make the ansatz that local contacts scale with local population density.
 We set

$$
\tilde{C}^\ell_{ij} = \frac{1}{a_{ij}} (\rho_i^\ell \rho_j^\ell)^b \tilde{C}_{ij}
$$

where $\rho_i^\ell = \frac{N^\ell_i}{A_i}$ is the local population density of age-group $i$, and where $A_i$ is the area of location $\ell$. $b$ is a scaling factor that should be determined from inference. $a_{ij}$ is a normalisation matrix that is determined by Eq. (3):

$$
a_{ij} = \sum_\ell (\rho_i^\ell \rho_j^\ell)^b
$$

Reverting back to the normal contact matrix form, we get

$$
C^\ell_{ij} = \frac{1}{a_{ij}} (\rho^\ell_i \rho^\ell_j)^b \frac{N_i}{N^\ell_i} \tilde{C}_{ij} (4)
$$

In Eq. (4) we see two different scalings: The $(\rho^\ell_i \rho^\ell_j)^b$ factor that scales contacts according to local population density, and $\frac{N_i}{N^\ell_i}$ that scales the contacts such that the consistency relation (2) is maintained.

It should be noted that the density scaling $(\rho_i^\ell \rho_j^\ell)^b$ could easily be replaced by another function. The same goes for 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTA4NzI1OTcyMV19
-->