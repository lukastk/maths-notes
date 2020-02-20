
### 2. 

$$
\begin{aligned}
B(t) & = \frac{1}{2} \int [ 1 - e^{-\beta U(y) } ] d^3 y \\
B(t) & =2 \pi \int_0^\infty [ 1 - e^{-\beta U(y)} ] d y \\
B(t) & =2 \pi \int_0^\infty [ 1 - e^{-\beta \alpha y^{-n} } ] d y
\end{aligned}
$$

As suggested by the question, there is a way to massage this integral into a Gamma function. Taking their suggestion, we make the substitution

$$
\begin{aligned}
y & = x^{-1/n} \left( \frac{\alpha}{T} \right)^{1/n} \\
dy & = - \frac{1}{n} x^{-1 - 1/n} \left( \frac{\alpha}{T} \right)^{1/n}  dx
\end{aligned}
$$

and since $x = 0 \leftrightarrow y = \infty$ and $x = \infty \leftrightarrow y = 0$ the integral limits is flipped, and we get a negative sign that cancels with the substitution of $dy$. We get

$$
\begin{aligned}
B(T) = \frac{2 \pi}{n} \left( \frac{\alpha}{T} \right)^{3/n} \int_0^\infty x^{-1 -3/n} ( 1- e^{-x}) dx
\end{aligned}
$$

Integrate by parts

$$
\int_0^\infty x^{-1 -3/n} ( 1- e^{-x}) dx = \left[ \frac{x^{-3/n}}{-3/n} (1 - e^{-x}) \right]_0^\infty + \frac{n}{3} \int_0^\infty x^{-3/n} e^{-x} dx
$$

Let's look at the first term.

- For $x \to \infty$, we have $(1 - e^{-x}) = 1$, and $x^{-3/n} = 0$.

- When $x \to 0$, we have that $x^{-3/n} \to \infty$, but $(1 - e^{-x}) = 0$. The limit still vanishes overall:

$$
\lim_{x \to 0} \frac{1 - e^{-x}}{x^{-3/n}} = \lim_{x \to 0} \frac{x - \frac{1}{2} x^2 + O(x^3)}{x^{-3/n}} = \lim_{x \to 0}\ \left(x^{1 - 3/n}-\frac{1}{2} x^{2-3/n} + O(x^{3 - 3/n}) \right) = 0
$$

as $n > 3$.

We are left with

$$
\int_0^\infty x^{-1 -3/n} ( 1- e^{-x}) dx =  \frac{n}{3} \Gamma(1-3/n)
$$

Using the identity $\Gamma(1 + z) = z \Gamma(z)$, we get

$$
\begin{aligned}
B(T) = - \frac{2 \pi}{n} \left( \frac{\alpha}{T} \right)^{3/n} \Gamma(-3/n)
\end{aligned}
$$

Setting $n=6$, we get

$$
\begin{aligned}
B(T) = \frac{2}{3} \pi^{3/2} \sqrt{ \frac{\alpha}{T} }.
\end{aligned}
$$

### 4.

The right answer should be

$$
B(T) = \frac{1}{2} \pi r_0^2
$$

and

$$
P \approx \frac{NT}{A} \left( 1 + \frac{N}{A} \left( \frac{1}{2} \pi r_0^2 \right) \right)
$$

I made a silly mistake in my solution.

### 5. (first part)

We'll answer the first part of the question in a systematic way.

The Hamiltonian of the whole system is

$$
H = \sum_{i} \left( \frac{1}{2m} \mathbf{p}_i^2 + \frac{1}{2} \alpha x_i^2  \right)
$$

and the partition function is

$$
\begin{aligned}
Z & = \int \prod_i d^3 \mathbf{x}_i d^3 \mathbf{p}_i\ e^{-\beta H} \\
& = \frac{Z_\text{ideal}^N}{V^N} \int \prod_i d^3 \mathbf{x}_i\ e^{- \beta \sum_j  \frac{1}{2} \alpha x_j^2 } \\
& = \frac{Z_\text{ideal}^N}{L^N} \int \prod_i dx_i\ e^{-\beta   \sum_j \frac{1}{2} \alpha x_j^2 } \\
& =  \left(\frac{Z_\text{ideal}}{L} \int_0^\infty dx\ e^{-\beta \frac{1}{2} \alpha x } \right)^N \\
& = \left(\frac{Z_\text{ideal}}{2 L} \sqrt{ \frac{2 \pi T}{ \alpha}} \right)^N
\end{aligned}
$$

The probability density of the system is

$$
P(\{\mathbf{x}_i\}, \{\mathbf{p}_i\}) = \frac{1}{Z} e^{-\beta H}
$$

Integrate out the momenta, and the yz-axes

$$
P(\{x_i\}) =2^N \left(\frac{\alpha}{2 \pi T} \right)^{N/2} e^{- \beta \sum_i \frac{1}{2} \alpha x_i}
$$

Now, the probability of finding particle $k$ with a certain $x$-coordinate is

$$
P_k(x) = \int \prod_{j \neq k} dx_j P(\{x_i\}) = 2 \sqrt{ \frac{\alpha}{2 \pi T}} e^{-\beta \frac{1}{2} \alpha x_i}
$$

note that the units of $P_k(x)$ is $[L^{-1}]$. And the probability of finding $N(x)$ particles with a certain $x$-coordinate is

$$
N(x) = \sum_k P_k(x) = NP_1(x)
$$

where we use the fact that all $P_k(x)$ are the same, and where $N$ is the total number of particles. The number density of the system is then

$$
\rho(x) = \frac{1}{V} N(x) = 2 N_0 \sqrt{ \frac{\alpha}{2 \pi T}} e^{-\beta \frac{1}{2} \alpha x_i}
$$

where $N_0$ is the number of atoms per unit area.

### 10.

We are considering black-body radiation that is both *homogenous* (radiation occurs with same density at each point in space) and *isotropic* (the black-body is radiating uniformly in all directions).

We thus have that light is radiating from each point in space. At each point, within the frequency range $(\omega, \omega + d\omega)$, light of energy $e(\omega)$ is radiating. $e(\omega)$ is of course proportional to the number of photons being emitted.

Consider the angular distribution $n(\theta, \phi)$ of photons hitting a certain point $\mathbf{x}$ in space. Because the radiation is homogenous and isotropic, the choice of $\mathbf{x}$ and the incoming angle should not matter. So we must have that $n(\theta, \phi)$ is a uniform distribution. We set $n(\theta, \phi) = 0$ and demand

$$
\int_0^{\pi} \int_0^{2\pi} n\ \sin \theta\ d\phi d\theta = 1
$$

which makes $n = \frac{1}{4 \pi}$.

Now consider a surface of area $A$ in space. In time $\Delta t$, we have that 

$$
n c (\cos \theta) \Delta t A
$$

photons within the frequency range $(\omega, \omega + d\omega)$ will hit the surface, from angle $\theta$.

The incident energy per unit time per unit area is

$$
e(\omega) n c \cos \theta = \frac{c}{4 \pi} \cos \theta e(\omega) d\omega
$$

We now integrate over all a solid angle. We take $0 \leq \theta \leq \pi / 2$ as the photons arriving from $\pi/2 \leq \theta \leq \pi$ are travelling in the opposite direction, and won't hit the surface.

$$
\int_{\theta=0}^{\theta=\pi/2} \int_{\phi=0}^{\phi=2\pi} \frac{c}{2\pi} \cos \theta e(\omega) \sin \theta d \theta d \phi  d\omega=\frac{1}{4} c e(\omega) d\omega
$$

### 12.

Let $R_0$ and $R_*$ be the radii of the planet and the sun respectively, and $D$ the distance between them.

We need to find the total luminosity landing on the planet. This can be approximated as

$$
P_\text{in} = L_* \frac{ \pi R_0^2}{4 \pi D^2}
$$

where the ratio $\frac{ \pi R_0^2}{4 \pi D^2}$ is an approximation of the proportion of the luminosity that reaches the planet.

Since the planet is a black body, we can use Stefan's law to compute it's luminosity as well $P_\text{out}$. The energy flowing out of the planet must be equal to the energy flowing out in equilibrium, so we have

$$
P_\text{in} = P_\text{out}
$$

from which we find that $T_0 \approx 17^o$.

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2NTUzODM0NDddfQ==
-->