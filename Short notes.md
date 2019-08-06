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
& = T \left[ \exp\left\{ \int_0^t d\tau \left( - \frac{\partial}{\partial q^\nu(\tau)} f^\nu (q(\tau)) \right) - \frac{\partial}{\partial q^\nu(\tau)} g_i^\nu(q(\tau)) \xi^i(\tau) \right\} \right] P(q,0) \end{aligned}$$

and can be expanded in the form (by simply expanding the Dyson series)

$$ \begin{aligned}P_\xi(q,t) & = T \bigg\{ \exp\left[ \int_0^t d\tau \left( - \frac{\partial}{\partial q^\nu(\tau)} f^\nu (q(\tau)) \right) \right] \\
& \times  \sum_{n=0}^\infty  \frac{(-1)^n}{n!} \int_0^t d\tau_1 \dots d\tau_n \frac{\partial}{\partial q^{\nu_1} (\tau_1)} g_{i_1}^{\nu_1}  \dots \frac{\partial}{\partial q^{\nu_n} (\tau_n) } g_{i_n}^{\nu_n} \xi^{i_1}(\tau_1) \dots \xi^{i_n}(\tau_n) \bigg\} P(q,0) \end{aligned} \quad (3)$$

Now (3) can be averaged over all possible path-realisation of the noise $\xi$. We get $\langle P_\xi (q, t) \rangle_\xi = P(q,t)$, the probability to observe $q$ at time $t$. Now recall Isserlis' theorem:

**Theorem:** <i>(Isserlis) If $(X_1, \dots, X_{2n})$ is a zero-mean multivariate normal random vector, then</i>

$$\begin{aligned}
\mathbb{E}[ X_1 X_2 \dots X_{2n} ] & = \sum \prod \mathbb{E} [X_i X_j] = \sum \prod \text{Cov}(X_i, X_j) \\
\mathbb{E}[X_1 X_2 \dots X_{2n-1}] & = 0
\end{aligned}$$

<i>where $\prod \sum$ means summing over distinct ways of partitioning $X_1 \dots X_{2n}$ into pairs $X_i X_j$, and each summand is the product of the $n$ pairs. This yields $(2n)! / (2^n n!) = (2n - 1)!!$ terms in the sum.</i>

Now we can safely assume that $\langle \xi^i \xi^j \rangle = 0$ for $i\neq j$, and we know that the self-correlation of the noise is a delta function. We have

$$\langle \xi^i (t_1) \xi^j (t_2) \rangle = \delta^{ij} \delta(t_2 - t_1)$$

So

$$
\langle \xi^{i_1} (\tau_1) \dots \xi^{i_n}(\tau_n)\rangle = \langle \xi^{i_1} (\tau_1) \xi^{i_2} (\tau_2) \rangle \dots \langle \xi^{i_{n-1}} (\tau_{n-1}) \xi^{i_n} (\tau_n) \rangle + \dots \quad (4)
$$

Consider some factor of one of the terms in (4), inserting it into the time integral we get:

$$ \begin{aligned}
& \int_0^t d \tau_a d\tau_b  \frac{\partial}{\partial q_{\nu_a}(\tau_a) } g_{i_a}^{\nu_a} \frac{\partial}{\partial q_{\nu_b}(\tau_b) } g_{i_b}^{\nu_b} \langle \xi^{i_a}(\tau_a) \xi^{i_b}(\tau_b) \rangle \\
& = \int_0^t d\tau_a \frac{\partial}{\partial q_{\mu}(\tau_a) } g_{i}^{\mu} \frac{\partial}{\partial q_{\nu}(\tau_a) } g_{j}^{\nu} \delta^{ij}
\end{aligned} $$

So regardless of the pairing, we get the same result. Thus the sum in $\prod \sum$ will only lead to a factor of the total number of possible combinations $\frac{n!}{(n/2)! 2^{n/2}} = (n-1)!!$. Only the even terms will survive the mean, so let $m=n/2$, then

$$\begin{aligned}
& \int_0^t d\tau_1 \dots d\tau_{2m} \frac{\partial}{\partial q^{\nu_1} (\tau_1)} g_{i_1}^{\nu_1}  \dots \frac{\partial}{\partial q^{\nu_{2m}} (\tau_{2m}) } g_{i_{2m}}^{\nu_{2m}} \xi^{i_1}(\tau_1) \dots \xi^{i_{2m}}(\tau_{2m}) \\
& =  \frac{(2m)!}{2^m m!} \prod_{i=1}^m \int_0^t d\tau_i \frac{\partial}{\partial q_{\mu}(\tau_i) } g_{i}^{\mu} \frac{\partial}{\partial q_{\nu}(\tau_i) } g_{j}^{\nu} \delta^{ij}
 \end{aligned}$$

So the probability becomes

$$ \begin{aligned}
P(q,t) & = T \bigg\{ \exp\left[ \int_0^t d\tau \left( - \frac{\partial}{\partial q^\nu(\tau)} f^\nu (q(\tau)) \right) \right] \\
& \times \sum_{m=0}^\infty   \frac{1}{2^m m!} \prod_{i=1}^m \int_0^t d\tau_i \frac{\partial}{\partial q^{\mu}(\tau_i) } g_{i}^{\mu} \frac{\partial}{\partial q^{\nu}(\tau_i) } g_{j}^{\nu} \delta^{ij} \\
& \times P(q,0)
\end{aligned}$$

which can be resummed to

$$
P(q,t) = T \left\{ \exp \left[ \int_0^t d\tau \left( - \frac{\partial}{\partial q^\nu)\tau)} f^\nu(q(\tau)) + \frac{1}{2} \delta^{ij} \frac{\partial}{\partial q^\nu(\tau)} g_i^\nu \frac{\partial}{\partial q^\mu(\tau)} g_j^\mu \right) \right] \right\} P(q, 0). \quad (5)
$$

Taking the time derivative of (5) gives us the Fokker-Planck equation

$$
\fra
$$

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
eyJoaXN0b3J5IjpbLTg3OTU5MDI3OSw4OTcwMDY5MDgsODI5Mj
k5NzcxLC0xMjIxMDI2ODIyLDEyNjMzNTY3ODAsLTEzNzgxMjI0
NDUsODUwODY0MjYsMTAwNzA2MTEzNV19
-->