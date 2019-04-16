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

Consider the an Ito SDE in integral form

$$ X_t = X_{t_0} + \int_{t_0}^t a(X_s) ds + \int_{t_0}^t b(X_s)\ dW_s \quad (11) $$

where the second integral is an Ito stochastic integral. Recall the Ito formula

$$
g(t, X_t) = g(t_0, X_{t_0})  + \int_{t_0}^t \left\{ \frac{\partial g}{\partial t} + a \frac{\partial g}{\partial x} + \frac{1}{2} b^2 \frac{\partial^2 g}{\partial x^2}\right\}ds + \int_{t_0}^t b \frac{\partial g}{\partial x}\ dW_s \quad.
$$

For a time-independent function $f=f(x)$, we have

$$\begin{aligned}
f(X_t) & = f(X_{t_0})  + \int_{t_0}^t \left( a(X_s) f'(X_s) + \frac{1}{2} b^2(X_s) f''(X_s) \right) ds + \int_{t_0}^t b(X_s) f'(X_s)\ dW_s \\
& = f(X_{t_0}) + \int_{t_0}^t L_0 f(X_s) ds + \int_{t_0}^t L_1 f(X_s) dW_s
\end{aligned} \quad (12)$$

where we have introduced the operators

$$L_0 f = af' + \frac{1}{2} b^2 f'' \quad (13)$$

and

$$L_1 f = b f' \quad (14)$$

In analogy with above, we can apply (12) to the functions $f=a$ and $f=b$, to get

$$\begin{aligned}
X_t = X_{t_0} + a(X_{t_0}) \int_{t_0}^t ds + b(X_{t_0}) \int_{t_0}^t dW_s + R
\end{aligned} \quad (15)$$

where

$$\begin{aligned}
R  = & \int_{t_0}^t \int_{t_0}^s L_0 a(X_z) dz ds + \int_{t_0}^t \int_{t_0}^s L_1 a(X_z) dW_z ds \\
 & + \int_{t_0}^t  \int_{t_0}^s L_0 b(X_z) dz dW_s + \int_{t_0}^t \int_{t_0}^s L_1 b(X_z) dW_z dW_s
\end{aligned} \quad(16)$$

## References

- Numerical Solutions of SDEs Through Computer Experiments - Kloeden, Platen, Schurz. Section 2.3.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc5MDUyNTgxMywtMTI1NDIwOTgzMiw3NT
A0NTg2NTQsMTQwNzM4MjQ0MiwtMjk0OTA3NDgwLC0yOTExMTIz
MCwtNzkyNDI2NjE3LDE1NTcwODQwMzEsMTI5MjA5MjU2MSwxOD
U1Mjk1OTA5LC0zNzQzMzM2OF19
-->