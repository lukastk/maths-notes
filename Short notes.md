## Aliasing in the semi-discrete Fourier transforms

Consider a function $u : \mathbb{R} \to \mathbb{R}$, and its discretisation on $h \mathbb{Z}$

$$v_j = u(x_j), \quad x_j = jh, \quad j \in \mathbb{Z}.$$

We will consider the relationship between the Fourier transform $\hat{u}(k)$ and the semi-discrete Fourier transform $\hat{v}(k)$. Since $v$ is a discrete function, Fourier space is bounded and $k \in [-\pi / h, \pi / h]$, and because it is unbounded we have that $k$ is continuous.

The Fourier transform is defined as

$$\hat{u}(k) = \int_{-\infty}^\infty e^{-ikx} u(x) dx, \quad k \in \mathbb{R} \quad(1)$$

and the semi-discrete Fourier transform is defined as

$$\hat{v} = h \sum_{j=-\infty}^\infty e^{-ik x_j} v_j, \quad k \in [-\pi/h, \pi/h]. \quad (2)$$

The reason why $\hat{v}$ is defined on a bound domain is due to *aliasing*. Consider the figure below. It shows that, on the grid $\frac{1}{4} \mathbb{Z}$, the functions $\sin(\pi x)$ and $\sin(9 \pi x)$ are identical.

![Aliasing](http://i.imgur.com/Fhym8hj.png)

For any complex exponential $e^{ikx}$, there are infinitely many other complex exponentials that match it on the grid $h \mathbb{Z}$ ("aliases"). Consequently, it suffices to measure wave-numbers for the grid in an interval of length $2 \pi / h$.

For completeness, the inverse Fourier transform is

$$ u(x) = \frac{1}{2 \pi} \int_{-\infty}^{\infty} e^{ikx} \hat{u}(k) dk, \quad x \in \mathbb{R}\ \quad (3) $$

and the inverse semi-discrete Fourier transform is

$$ v_j = \frac{1}{2 \pi} \int_{-\pi / h}^{\pi / h} e^{ikx_j} \hat{v}(k) dk, \quad j \in \mathbb{Z} \quad (4)$$

So we see that the semi-discrete Fourier transform (2) approximates the Fourier transform (1) by a trapezoid rule, and the inverse semi-discrete Fourier transform (4) approximates the inverse Fourier transform (3) by truncating $\mathbb{R}$ to $[-\pi/h, \pi/h]$. As $h \to 0$, the two pairs of formulas converge.

For the relationship between $\hat{u}$ and $\hat{v}$, we have the following theorem:

**Theorem (Aliasing formula):** Let $u \in L^2 (\mathbb{R})$ have a first derivative of bounded variation, and let $v$ be its associated grid function on $h \mathbb{Z}$. Then for all $k \in [-\pi/h, \pi / h]$,

$$\hat{v}(k) = \sum_{-\infty}^\infty \hat{u}(k + 2 \pi j / h).$$

## Center manifolds, and slow manifolds

**Theorem (Stable manifold theorem)**  Let

$$f : U \subset \mathbb{R}^n \to \mathbb{R}^n$$

be a smooth map, and consider the dynamical system

$$\dot{x}  = f(x)$$

with a hyperbolic fixed point $f(p) = 0$. We denote $W^s(p)$ as the stable set and $W^u(p)$ as the unstable set of $p$. Let $E^s(p)$ and $E^u(p)$ be the stable and unstable sets of the linearised system around $p$. Then 

- $W^s(p)$ is a smooth manifold and its tangent space has the same dimension as $E^s(p)$.
- $W^u(p)$ is a smooth manifold and its tangent space has the same dimension as $E^u(p)$.

===

If we have non-hyperbolic points the situation is complicated. Non-hyperbolic points arise when there are eigenvalues of the linearised system with zero-real parts (i.e. fully imaginary eigenvalues). 

**Theorem (Centre Manifold Theorem):** Let $p$ be a non-hyperbolic fixed point of $f$ defined above. Suppose the Jacobian matrix $Df(0)$ has eigenvalues in sets $\sigma_u$ with $\text{Re}(\lambda) > 0$, $\sigma_s$ with $\text{Re}(\lambda) < 0$ and $\sigma_c$ with $\text{Re}(\lambda) = 0$. Then there exist unstable and stable manifolds $W^u$, $W^u$ of the same dimenson as $E^u$ and $E^s$ and tangential to $E^s$ and $E^u$ at $x=0$ respectively; and an invariant centre manifold $W^c$ tangential to $E^c$ at $x=0$.

So in general, locally $\mathbb{R}^n = W^c \oplus W^u \oplus W^s$ with the approximate governing equations on each manifold

$$\begin{aligned}
\dot{x} & = g(x) & \text{on } W^c \\
\dot{y} & = B y & \text{on } W^s \\
\dot{z} & = C z & \text{on } W^u
\end{aligned}$$

where $x \oplus y \oplus z \in \mathbb{R}^n$ and $B$ and $C$ are the Jacobian matrices of the stable and unstable directions respectively; and $g(x)$ is some quadratic (or higher order) function in $x$. All eigenvalues of $B$ have negative real parts, and all eigenvalues of $C$ have positive real parts.

===

So the centre manifold consists of orbits whose behaviour around the equilibrium point is not controlled by the exponential behaviour of the stable or unstable manifolds. It is often the case that points away from the center manifold converge onto the center manifold exponentially quickly, and thus the non-centre manifolds can be seen as a sort of transient behaviour.

In multi-scale mathematics, we often have that long-time dynamics are attracted to a relatively simple center manifolds.

The subset of eigenvalues that are precisely zero (so $\text{Im}(\lambda)=0$ as well) comprise the *slow* manifold. The slow manifold is thus a subspace of the center manifold. They are slow in the sense that the dynamics on these manifolds are sub-exponential in nature, as opposed to the stable/unstable manifolds.

**Example:** We have the system

$$
\dot{x} = - xy, \quad \dot{y} = - y + x^2 - 2 y^2
$$

which has the exact slow manifold $y=x^2$, on which the evolution is $\dot{x} = - x^3$. Apart from exponentially decaying transients, this slow manifold and its evolution captures all solutions that are in the neighbourhood of the origin.



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
eyJoaXN0b3J5IjpbOTA3MTA3NjM1LDU0NzM3OTIxOCwyMzI2Mj
I2MjUsODA5MDYwNzIyLC03NjQ4OTU0NDksMjAzNDg3MzQ3Niwy
MDkyMTM4Mjg5LC0xMzc4MTIyNDQ1LDg5NzAwNjkwOCw4MjkyOT
k3NzEsLTEyMjEwMjY4MjIsMTI2MzM1Njc4MCwtMTM3ODEyMjQ0
NSw4NTA4NjQyNiwxMDA3MDYxMTM1XX0=
-->