# Linear response functions

Let $\phi_i(t)$ be the input into a system (e.g a force), and $\delta \mathcal{O}_i(t)$ the response of the system (e.g a position). In general it is difficult to understand how a system responds to the inputs, but for some systems we can make the assumption that the input results in a small perturbation of the original system. Mathematically, this means that we assume that the response of the system is linear in the perturbing input. We write

$$
\delta \mathcal{O}_i(t) = \int dt'\ \chi_{ij} (t ; t') \phi_j(t') \quad (1)
$$

Where $\chi_{ij}(t;t')$ is the *response function*. Assuming time-translation invariance, we have

$$\chi_{ij}(t;t') = \chi_{ij}(t - t').$$

It is useful to take the Fourier transform of (1). We define the Fourier transformations as

$$
\hat{f}(\omega) = \int dt e^{i \omega t} f(t), \quad f(t) = \frac{1}{2 \pi} \int d\omega e^{-i\omega t} f(\omega).
$$

Taking the Fourier transform of (1) gives

$$
\begin{aligned}
\delta \hat{\mathcal{O}}_i(\omega)  & = \int dt' \int dt\ e^{i \omega t} \chi_{ij}(t - t') \phi_j(t') \\
& = \int dt' \int dt\ e^{i \omega (t - t')} \chi_{ij} (t - t') e^{i \omega t'} \phi_j(t') \\
& = \hat{\chi}_{ij}(\omega) \hat{\phi}_j(\omega)
\end{aligned}
$$

So the response is "local" in frequency space: if you shake something at frequency $\omega$, it responds at frequency $\omega$. Anything beyond this lies in the domain of non-linear response.

### Volterra series

The linear response function is the first-order term in the Volterra series. The Volterra series is a method to capture the non-linear response of a system to some input. A Taylor series can be used for this if the response of the system is dependent solely on the value of the input at that particular time. The Volterra series depends on the input of the system at *all* times.

Let $y(t)$ denote a continuous time-invariant system, with input $\phi(t)$. Then the response of $y(t)$ can be expanded in a Volterra series as

$$
y(t) = h_0 + \sum_{n=1}^N \int_a^b \dots \int_a^b h_n(\tau_1, \dots, \tau_n) \prod_{j=1}^n \phi(t - \tau_j) d \tau_j
$$

The function $h_n(\tau_1, \dots, \tau_n)$ is called the *n*-th order Volterra kernel. If $N$ is finite, the series is said to be *truncated*. If *a*, *b*, and *N* are finite, the series is called *doubly finite*.

### Example: Classical mechanics

Consider a driven system of the form

$$
\ddot x_i + g_i (\dot x, x) = F_i(t) \quad (2)
$$

Then we can clearly see from the response

$$
x_i(t) = \int_0^t \chi_{ij}(t - t') F_j(t)
$$

that $\chi_{ij}(t-t')$ is simply the Green's function of the left-hand side of (2).

### Example:  Damped harmonic oscillator

For a damped harmonic oscillator, with external driving force $h(t)$,

$$
\ddot x + \gamma \dot x + \omega_0^2 x = h,
$$

the complex-valued Fourier transform of the linear response function is given by

$$
\hat{\chi}(\omega) = \frac{1}{\omega_0^2 - \omega^2 + i \gamma \omega}.
$$

### References

- http://www.damtp.cam.ac.uk/user/tong/kintheory/four.pdf
- https://en.wikipedia.org/wiki/Linear_response_function
- https://en.wikipedia.org/wiki/Volterra_series
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjk4Njc0NzA3LDIwNDkwOTMwOF19
-->