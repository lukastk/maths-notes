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

### Derivation

The linear response function is the first-order term in the Volterra series. The Volterra series is a method ot

### Example: Classical mechanics

Consider a driven system of the form

$$
\ddot x_i + g_i (\dot x, x) = F_i(t) \quad (1)
$$

Then we can clearly see from the response

$$
x_i(t) = \int_0^t \chi_{ij}(t - t') F_j(t)
$$

that $\chi_{ij}(t-t')$ is simply the Green's function of the left-hand side of (1).

### Example:  Damped harmonic oscillator


### References

- http://www.damtp.cam.ac.uk/user/tong/kintheory/four.pdf
- https://en.wikipedia.org/wiki/Linear_response_function
- https://en.wikipedia.org/wiki/Volterra_series
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTAzNDgzNDc5LDIwNDkwOTMwOF19
-->