Dear Ronojoy and all,

The paper is indeed quite interesting. In terms of my perspective, I would note that the final result of the $\Gamma$-limit $F$ of $F_\epsilon$ seems to amount to a sort of modified Freidlin-Wentzell action.

Eq. 4.14 of the paper gives the $\Gamma$-limit

$$
F[m, \mathbf{A}] = E[m] + \frac{1}{4} \int_0^1 (D^2 V(m(t)) - \mathbf{A}(t))^2 : \mathbf{A}^{-1} dt \quad(1)
$$

where $E[m]$ (Prop 4.3) is similar to the quasi-potential, differing only by a constant, and requires $m$ to start and end at fixed point. Given $m(t)$, the second term is minimised by setting $\mathbf{A}(t) = |D^2 V(m(t))$, where the matrix norm is defined as $|C| = P^T |D| P$ and $$D$ is the diagonalisation of $C$. So we can re-write (1) as

$$
F[m] = E[m] + \frac{1}{4} \int_0^1 (D^2 V(m(t)) - |D^2 V(m(t))|)^2 : |D^2 V(m(t))|^{-1} dt \quad(2)
$$

Let $\lambda^{(-)}_i(m(t))$ be the negative eigenvalues of $D^2 V(m(t))$, then the second term in (2) can be shown to simplify to

$$
F[m] = E[m] + \int_0^1 \sum_i |\lambda^{(-)}_i(m(t))| dt. \quad(3)
$$

Finally, consider the following modified FW functional:

$$
\begin{aligned}
\bar{S}[m] & = S_\text{FW}[m] + \int_0^1 \sum_i |\lambda^{(-)}_i(m(t))| dt\\
& = \int_0^1 \left( \frac{1}{2} |\dot{x} + \nabla V|^2 + \sum_i |\lambda^{(-)}_i(m(t))| \right) dt
\end{aligned}\quad(4)
$$

Since $E[m]$ is the quasi-potential ($\pm$ some constants), the two functionals share minimisers $\arg \inf \bar{S}[m] = \arg \inf F[m]$. So we see that the result of the paper is equivalent to a modified Freidlin-Wentzell action. The second term in (4) has the clear interpretation of discouraging paths that lingers in maxima or saddle-points.

It's important to note that all of this is only valid for equilibrium systems, where the drift is a gradient of some potential. In terms of future applications of this, it could be used to compute corrections to instantons of gradient-systems like the Muller-Brown.

Best,

Lukas
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk0NDcyNzU3Ml19
-->