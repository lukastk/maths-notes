# Bayesian estimation in differential equation models

Ref: [https://www4.stat.ncsu.edu/~ghosal/papers/BayesODEspline.pdf](https://www4.stat.ncsu.edu/~ghosal/papers/BayesODEspline.pdf)

Notation:

- $C^m(E)$ is the set of functions on $E$ with first $m$ continuous partial derivatives with respect to its arguments.

Model:

$$
\frac{ d f_{j \boldsymbol{\theta}}}{d t} = F_j(t, \mathbf{f}_{\boldsymbol{\theta}}(t), \boldsymbol{\theta}),\quad t \in [0,1],\ j=1,\dots, d
$$

where $\mathbf{f}_\boldsymbol{\theta} (\cdot) = ( f_{1\boldsymbol{\theta}}(\cdot), \cdot, f_{d  $\boldsymbol{\theta} \in \boldsymbol{\Theta}$, where $\boldsymbol{\Theta}$ is some compact subset of $\mathbb{R}^p$. For fixed $\boldsymbol{\theta}$, $\mathbf{F} \in C^{m-1}( (0,1), \mathbb{R}^d )$. Thus, by successive differentiation, we get that $\mathbf{f}_\boldsymbol{\theta} \in C^m( (0,1) )$.
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTE3NjE2MzAxLC0xMTUzNjcxOTAzLC0xND
E0MDA2MzQwXX0=
-->