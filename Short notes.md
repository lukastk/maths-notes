## Center manifolds, and slow manifolds

**Theorem (Stable manifold theorem)** Let

$$f : U \subset \mathbb{R}^n \to \mathbb{R}^n$$

be a smooth map, and consider the dynamical system

$$\dot{x}  = f(x)$$

with a hyperbolic fixed point $f(p) = 0$. We denote $W^s(p)$ as the stable set and $W^u(p)$ as the unstable set of $p$. Let $E^s(p)$ and $E^u(p)$ be the stable and unstable sets of the linearised system around $p$. Then 

- $W^s(p)$ is a smooth manifold and its tangent space has the same dimension as $E^s(p)$.
- $W^u(p)$ is a smooth manifold and its tangent space has the same dimension as $E^u(p)$.</i>


If 

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
eyJoaXN0b3J5IjpbLTIwMTU5MjQ0NDcsLTEzNzgxMjI0NDUsOD
k3MDA2OTA4LDgyOTI5OTc3MSwtMTIyMTAyNjgyMiwxMjYzMzU2
NzgwLC0xMzc4MTIyNDQ1LDg1MDg2NDI2LDEwMDcwNjExMzVdfQ
==
-->