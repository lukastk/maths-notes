# Derivation of the Fokker-Planck on the sphere

For any given Ito diffusion of the form

$$
d X = a(X, t) dt + \sigma(X, t) dW \quad (1)
$$

we have the corresponding Fokker-Planck equation

$$
\frac{\partial p(x, t)}{\partial t} = - \nabla_i [ a_i(x, t)p(x,t) ] + \nabla_i \nabla_j [D_{ij}(x,t)p(x,t)] .\quad (2)
$$

Eq. 2 will hold regardless of the form of $a$ and $\sigma$ (given that they satisfy certain regularity conditions). Consider the SDE for inertial Brownian motion on a sphere

$$\begin{aligned}
I \dot \omega & = - \gamma \omega + T(p) + \sigma \dot{W} \\
\dot{p} & = \omega \times p 
\end{aligned}$$

where $W$ is the Wiener process. Taking the overdamped limit, we get

$$
\dot{p} = \frac{1}{\gamma} T \times p - \frac{1}{\gamma}[p_\times]\sigma \dot{W} \quad (3)
$$

where $[p_\times]$ is the matrix-version of the cross-product. Let $a=\frac{1}{\gamma} T \times p$ and $\Sigma = -\frac{1}{\gamma} [p_\times] \sigma$. Eq. (3) has the conserved quantity $|p| =  1$, which in geometric terms means that the system is defined over the 2-sphere. This is an *implicit(*
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzQwNzM5MTUyLDMyMTkyMjIxOF19
-->