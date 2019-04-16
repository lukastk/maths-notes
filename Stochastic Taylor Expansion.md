# Stochastic Taylor Expansion

## Deterministic Taylor Expansion

Consider the solution $X = \{ X_t,\ t \in [t_0, T] \}$ of a 1-dimensional ODE

$$\frac{d}{dt} X_t = a(X_t) \quad (1)$$

with initial value $X_{t_0}$, for $t \in [t_0 T]$ where $0 \leq t_0 \leq T$. We can write this equivalently as

$$X_t = X_{t_0} + \int_{t_0}^t a(X_s) ds \quad (2)$$

Now, let $f : \mathbb{R} \to \mathbb{R}$ be a continuously differentiable function. Then, by the chain rule, we have

$$\frac{d}{dt} f(X_t) = a(X_t) f'(X_t) \quad (3)$$.

We define the corresponding operator

$$L f = a f' \quad (4)$$

and then express (3) as

$$f(X_t) = f(X_{t_0}) + \int_{t_0}^t L f(X_s) ds$$
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg1NTI5NTkwOSwtMzc0MzMzNjhdfQ==
-->