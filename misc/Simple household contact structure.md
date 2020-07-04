### Simple inter-household contact structure

Let $N_i^\mu$ be the number of people of age-group $i$ in household $\mu$.

The simplest form of the contact structure would be the following:

$$
\dot{S}^\mu_i = - \beta S_i^\mu \sum_{j} C^H_{ij} \frac{I_j^\mu}{N_j^\mu} \quad - \beta S_i^\mu \sum_j ( C_{ij}^W + C_{ij}^S + C_{ij}^O)  \frac{ \sum_{\nu\neq\mu} I_j^\nu}{ \sum_{\nu\neq\mu} N_j^\nu}
$$

The first term describes contacts within the house-hold, and the latter contacts with other households. A household interacts with a single mean-field household $\frac{ \sum_{\nu\neq\mu} I_j^\nu}{ \sum_{\nu\neq\mu}N_j^\nu}$, via the social contact matrix $C_{ij}^W + C_{ij}^S + C_{ij}^O$.

The above equation can be cast in the usual form

$$
\dot{S}^\mu_i = - \beta S_i^\mu \sum_{j, \nu} C_{ij}^{\mu \nu} \frac{ I_j^\nu}{N_j^\nu}
$$

by constructing the inter-household contact matrix $C_{ij}^{\mu \nu}$ as follows:

For $\mu = \nu$

$$
C_{ij}^{\mu \mu}  = C^H_{ij} 
$$

and for $\mu \neq \nu$

$$
\begin{aligned}
C_{ij}^{\mu \nu} & = ( C_{ij}^W + C_{ij}^S + C_{ij}^O) \frac{ N^\nu_j }{N_j}
\end{aligned}
$$

Such that

$$
\sum_{j, \nu} C_{ij}^{\mu \nu} \frac{ I_j^\nu}{N_j^\nu} = \sum_{j} C^H_{ij} \frac{I_j^\mu}{N_j^\mu} \quad +\sum_j ( C_{ij}^W + C_{ij}^S + C_{ij}^O)  \frac{ \sum_{\nu\neq\mu} I_j^\nu}{ \sum_{\nu\neq\mu} N_j^\nu}
$$

## Simplification

Let's make the MFT approximation that

$$
S_i^\mu \approx \bar{S}_i.
$$

In other words, we replace the dynamics of the individual households with that of the mean household. We also set all household sizes to be the same: $N^\mu_i = \bar{N}_i$.

We get

$$
\dot{\bar{S}}_i = - \beta \bar{S}_i \sum_{j} C^H_{ij} \frac{\bar{I}_j}{\bar{N}_j} \quad - \beta \bar{S}_i \sum_j ( C_{ij}^W + C_{ij}^S + C_{ij}^O)  \frac{I_j}{N_j}
$$

where $I_j = M \bar{I}_j$, and $M$ is the number of households.

We multiply by $M$ on both sides, to get

$$
\dot{S}_i = -\beta S_i \sum_j (C_{ij}^H + C_{ij}^W + C_{ij}^S + C_{ij}^O)  \frac{I_j}{N_j}
$$

we get exactly the usual expression.

Why do we get this? This exercise shows us that the over-estimation of home-contacts come from 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYyODAyODM5OSwxMTA3MTM1NTkzLDE5MD
IxODIxXX0=
-->