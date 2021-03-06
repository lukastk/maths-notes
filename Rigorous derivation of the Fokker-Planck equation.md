# Rigorous derivation of the Fokker-Planck equation

Consider the Langevin equation of a system with macroscopic variables $q^\nu$.

$$ \dot q^\nu = f^\nu(q) + g_i^\nu \xi^i (t)  \quad (1)$$

We have that Greek indices $\nu=1, \dots, n$ number the macroscopic variables, and $i=1, \dots, m$ number the fluctuating forces.

*Note: We interpret (1) in the sense of Stratonovich, not in the sense of Ito. This allows us to use the normal rules of calculus on $q^\nu$.*

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
\frac{\partial P(q,t)}{\partial t} = \left\{ - \frac{\partial}{\partial q^\nu} K^\nu (q) + \frac{1}{2} \frac{\partial^2 }{\partial q^\nu \partial q^\mu} Q^{\nu \mu}(q)\right\} P(q,t)
$$

with

$$\begin{aligned}
K^\nu(q) & = f^\nu(q) + \frac{1}{2} \frac{\partial g_i^\nu(q)}{\partial q^\mu} g_k^\mu(q) \delta^{ik} \\
Q^{\nu\mu}(q) & = g_i^\nu(q) g_k^\mu(q) \delta^{ik}
\end{aligned}$$

#### Reference

See the introduction (Section 1) of *Covariant Formulation of Non-Equilibrium Statistical Thermodynamics* by *Robert Graham*.

Link: [https://link.springer.com/content/pdf/10.1007%2FBF01570750.pdf](https://link.springer.com/content/pdf/10.1007%2FBF01570750.pdf)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNTI3NzU2NjVdfQ==
-->