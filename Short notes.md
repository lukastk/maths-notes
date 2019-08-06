## Nice mathsy derivation of the Fokker-Planck equation

Consider the Langevin equation of a system with macroscopic variables $q^\nu$.

$$ \dot q^\nu = f^\nu(q) + g_i^\nu \xi^i (t)  \quad (1)$$

We have that Greek indices $\nu=1, \dots, n$ number the macroscopic variables, and $i=1, \dots, m$ number the fluctuating forces.

For every path-realisation of the noise $\xi$ we have a probability density $P_\xi(q,t)$, satisfying the continuity equation

$$\frac{\partial P_\xi}{\partial t} + \frac{\partial}{\partial q^\nu} \dot q^\nu P_\xi = 0 \quad (2) $$

where $\dot q^\nu$ is given by (1). It can be rewritten as

$$\begin{aligned}
\frac{\partial P_\xi}{\partial t}  & = L P_\xi \\
L & = - \frac{\partial}{\partial q^\nu} \dot q^\nu 
\end{aligned}$$

The formal solution to (2) is

$$ \begin{aligned}P_\xi(q,t) & = T \left[ \exp \left\{ - \int_{0}^t d\tau L^\dagger \right\} \right] P(q, 0) \\
& = T \left\{ \exp\left[ \int_0^t d\tau \left(  \right) \right] \right\} P(q,0) \end{aligned}$$

#### Reference

See the introduction (Section 1) of *Covariant Formulation of Non-Equilibrium Statistical Thermodynamics* by *Robert Graham*.

Link: [https://link.springer.com/content/pdf/10.1007%2FBF01570750.pdf](https://link.springer.com/content/pdf/10.1007%2FBF01570750.pdf)

## Multiple-scale analysis

Standard perturbation techniques involve expanding the solution of an equation in a power series in some "small parameter". So for the Duffing equation

$$ \frac{d^2 y}{dt^2} + y + \epsilon y^3 = 0, \quad y(0) =1, \quad \frac{dy}{dt}(0) = 0 $$

we would expand the solution as

$$ y(t) = Y_0(t) + \epsilon Y_1(t) + O(\epsilon^2). $$

This leads to

$$ y(t) = \cos (t) + \epsilon \left[ \frac{1}{32} \cos(3t) - \frac{1}{32} \cos (t) - \frac{3}{8} t \sin (t) \right] + O(\epsilon^2) $$

The last term in the square braces is secular: it grows without bound for large $t$. Specifically, for $t = O(\epsilon^{-1})$ we have that the term is $O(1)$, and has the same order of magnitude as the leading-order term. Since the terms have become disordered, the series is no longer an asymptotic expansion of the solution.

The method of multiple scales involves separating the short and long-term behaviours of the system, and assuming that they are independent variables. For example, it might help us locate the periodic and secular components of the evolution of the solution.

We introduce the slow scale

$$ t_1 = \epsilon t $$

and assume that the solution is a perturbation series dependent on both $t$ and $t_1$,

$$ y(t) = Y_0(t, t_1) + \epsilon Y_1(t, t_1) + O(\epsilon^2 ) $$ 

This type of perturbation leads to a solution that is valid for $t=O(\epsilon^{-2})$.

Another example is the simpler equation

$$ \frac{d^2 y}{dt^2} + y = \cos(t) $$

which has the analytical solution

$$ y(t) = A \cos t + B \cos t + \frac{1}{2} t \sin t. $$

The third term is a secular term. In general, the appearance of a secular term signals the nonuniform validity of perturbation expansions for large $t$.

#### References

- Advanced Mathematical Methods for Scientists and Engineers I - C. Bender and S. A. Orszag
- [https://en.wikipedia.org/wiki/Multiple-scale_analysis#cite_note-5](https://en.wikipedia.org/wiki/Multiple-scale_analysis#cite_note-5)- 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk3OTU4MjcxMiwxMjYzMzU2NzgwLC0xMz
c4MTIyNDQ1LDg1MDg2NDI2LDEwMDcwNjExMzVdfQ==
-->