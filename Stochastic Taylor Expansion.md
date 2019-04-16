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

$$f(X_t) = f(X_{t_0}) + \int_{t_0}^t L f(X_s)\ ds \quad (5)$$

for all $t \in [t_0, T]$.  Now let $f(x) = x$ we have $Lf = a$, $L^2 f = La$, and so on. Then (5) reduces to equation (2).

Now let $f=a$, we then have

$$a(X_t) = a(X_{t_0}) + \int_{t_0}^t L a(X_s) ds \quad(6)$$

which we can plug into (2) to get

$$ \begin{aligned}
X_t & = X_{t_0} + \int_{t_0}^t \left( a(X_{t_0}) + \int_{t_0}^{s_2} L a(X_{s_1}) ds_1 \right) ds_2 \\
& =  X_{t_0} + a(X_{t_0}) \int_{t_0}^t ds_2 + \int_{t_0}^t \int_{t_0}^{s_2} L a(X_{s_1}) ds_1 ds_2  \\
& =  X_{t_0} + a(X_{t_0}) (t - t_0) + \int_{t_0}^t \int_{t_0}^{s_2} L a(X_{s_1}) ds_1 ds_2 \quad (7)
\end{aligned} $$

which is the simplest non-trivial Taylor expansion for $X_t$.  We can continue this expansion by setting $f=La$. We get

$$La(X_t) = La(X_{t_0}) + \int_{t_0}^t L^2 a(X_s) ds \quad(8)$$

and we substitute this into (7) to get

$$X_t = X_{t_0} + a(X_{t_0}) \int_{t_0}^t ds_1 + La(X_{t_0}) \int_{t_0}^t \int_{t_0}^{s_2} ds_1 ds_2 + R_3 \quad (9)$$

with the remainder

$$R_3 = \int_{t_0}^t \int_{t_0}^{s_3} \int_{t_0}^{s_2} L^2 a(X_{s_1})\ ds_1 ds_2 ds_3 . $$

Doing this $r+1$ times gives us the classical *Taylor formula*

$$\begin{aligned}
f(X_t) =\ & f(X_0) + \sum_{l=1}^r \frac{ (t-t_0)^l}{l!} L^l f(X_{t_0}) \\
& + \int_{t_0}^t \dots \int_{t_0}^{s_2} L^{r+1} f(X_{s_1})\ ds_1 \dots ds_{r+1} \quad (10)
\end{aligned}$$

## The Ito-Taylor Expansion



## References

- Numerical Solutions of SDEs Through Computer Experiments - Kloeden, Platen, Schurz. Section 2.3.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc5MjQyNjYxNywxNTU3MDg0MDMxLDEyOT
IwOTI1NjEsMTg1NTI5NTkwOSwtMzc0MzMzNjhdfQ==
-->