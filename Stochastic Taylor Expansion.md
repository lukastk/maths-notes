# Stochastic Taylor Expansion

## Deterministic Taylor Expansion

Consider the solution $X = \{ X_t,\ t \in [t_0, T] \}$ of a 1-dimensional ODE

$$\frac{d}{dt} X_t = a(X_t)$$

with initial value $X_{t_0}$, for $t \in [t_0 T]$ where $0 \leq t_0 \leq T$. We can write this equivalently as

$$X_t = X_{t_0} + \int_{t_0}^t a(X_s) ds$$

Now, let $f : \mathbb{R} \to \mathbb{R}$ be a continuously differentiable function. Then, by the chain rule, we have

$$\frac{d}{dt} f(X_t) = a(X_t) f'(X_t)$$.

We define the corresponding operator

$$L f = a f'
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzg5OTI2Mzc1LC0zNzQzMzM2OF19
-->