# Derivation of the Fokker-Planck on the sphere

For any given Ito diffusion of the form

$$
d X = a(X, t) dt + \sigma(X, t) dW \quad (1)
$$

we have the corresponding Fokker-Planck equation

$$
\frac{\partial P(x, t)}{\partial t} = - \nabla_i [ a_i(x, t)P(x,t) ] + \nabla_i \nabla_j [D_{ij}(x,t)P(x,t)] .\quad (2)
$$

where $D = \frac{1}{2} \sigma \sigma^T$. Eq. 2 will hold regardless of the form of $a$ and $\sigma$ (given that they satisfy certain regularity conditions). Consider the SDE for inertial Brownian motion on a sphere

$$\begin{aligned}
I \dot \omega & = - \gamma \omega + T(p) + \sigma \dot{W} \\
\dot{p} & = \omega \times p 
\end{aligned}$$

where $W$ is the Wiener process. Taking the overdamped limit, we get

$$
\dot{p} = \frac{1}{\gamma} T \times p - \frac{1}{\gamma}[p_\times]\sigma \dot{W} \quad (3)
$$

where $[p_\times]$ is the matrix-version of the cross-product. Let $a=\frac{1}{\gamma} T \times p$ and $\Sigma = -\frac{1}{\gamma} [p_\times] \sigma$. Eq. (3) has the conserved quantity $|p| =  1$, which in geometric terms means that the system is defined on the 2-sphere. On the other hand, the explicit manifold we are working in is $\mathbb{R}^3$, so we are clearly working with an embedding of $S^2$ in Euclidean space. In the language of [Van Kampen](https://link.springer.com/content/pdf/10.1007/BF01010902.pdf), we have an *implicit* mathematical constraint.

Complications arise when trying to go from the coordinate system in the embedded space, into local coordinates on the manifold itself. Instead of doing that, we remain in the Euclidean space, and simply work with the Fokker-Planck (2) as we know it.

Consider the first term in (2):

$$\begin{aligned}
\nabla_i [ a_i(x, t)P(x,t) ] & = \frac{1}{\gamma} \nabla_i [ \epsilon_{ijk} T_j p_k P ] \\
& = \frac{1}{\gamma} \epsilon_{ijk} T_j p_k \nabla_i P + \frac{1}{\gamma} \epsilon_{ijk} (\nabla_i T_j) p_k P \\
& = a \cdot \nabla P + \frac{1}{\gamma} \epsilon_{ijk} (\nabla_i T_j) p_k P
\end{aligned}$$

Define $B_{ab} = \sigma \sigma^T P$, and consider the 2nd term in (2):

$$\begin{aligned}
\nabla_i \nabla_j (D_{ij} P) & = \nabla_i \nabla_j \left[ \frac{1}{2 \gamma^2} ([p_\times]\sigma \sigma^T [p_\times]^T)_{ij} P \right] = \frac{1}{2 \gamma^2} \nabla_i \nabla_j \left( [p_\times]_{ia} [p_\times]_{cj} B_{ab} \right) \\
= \frac{1}{2 \gamma^2} & \bigg[ 
\cancel{\nabla_i \nabla_j [p_\times]_{ia} [p_\times]_{cj} B_{ac}} + \nabla_j [p_\times]_{ia} \nabla_i [p_\times]_{cj} B_{ac} + \nabla_j [p_\times]_{ia} [p_\times]_{cj} \nabla_i B_{ac} \\
&+ \cancel{ \nabla_i [p_\times]_{ia} \nabla_j [p_\times]_{cj} B_{ac}} + \cancel{[p_\times]_{ia} \nabla_i \nabla_j [p_\times]_{cj} B_{ac}} + \cancel{[p_\times]_{ia} \nabla_j [p_\times]_{cj} \nabla_i B_{ac} }\\
& + \cancel{\nabla_i [p_\times]_{ia} [p_\times]_{cj} \nabla_j B_{ac}} + [p_\times]_{ia} \nabla_i [p_\times]_{cj} \nabla_j B_{ac} + [p_\times]_{ia} [p_\times]_{cj} \nabla_i \nabla_j B_{ac} \bigg]
\end{aligned}$$

where some terms cancel due to $\nabla_i [p_\times]_{ij} = 0$. We now consider each term separately.

$$ \begin{aligned}
\nabla_j [p_\times]_{ia} \nabla_i [p_\times]_{cj} B_{ac}  & = (\nabla_j \epsilon_{ika} p_k)(\nabla_i \epsilon_{c lj} p_l) B_{ac} \\
& = \epsilon_{aij} \epsilon_{cij} B_{ac} = 2 \delta_{ac} B_{ac} \\
& = 2 \text{Tr} [B] = 2 P\text{Tr}[\sigma \sigma^T]
\end{aligned}$$

$$ \begin{aligned}
[p_\times]_{ia} \nabla_i [p_\times]_{cj} \nabla_j B_{ac} & = \epsilon_{ika} \epsilon_{cij} p_k \nabla_j B_{ac} \\
& = (\delta_{kj} \delta_{ac} - \delta_{kc} \delta_{aj} ) p_k \nabla_j B_{ac} \\
& = p_j \nabla_j B_{aa} - p_c \nabla_a B_{ac} \\

\end{aligned}$$
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNDg0ODA3NjEsLTkxNDM4MTQ5MCwzMj
E5MjIyMThdfQ==
-->