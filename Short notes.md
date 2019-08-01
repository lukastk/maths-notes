## Multiple-scale analysis

Standard perturbation techniques involve expanding the solution of an equation in a power series in some "small parameter". So for the Duffing equation

$$ \frac{d^2 y}{dt^2} + y + \epsilon y^3 = 0, \quad y(0) =1, \quad \frac{dy}{dt}(0) = 0 $$

we would expand the solution as

$$ y(t) = Y_0(t) + \epsilon Y_1(t) + \mathcal{O}(\epsilon^2). $$

This leads to

$$ y(t) = \cos (t) + \epsilon \left[ \frac{1}{32} \cos(3t) - \frac{1}{32} \cos (t) - \frac{3}{8} t \sin (t) \right] + \mathcal{O}(\epsilon^2) $$

The last term in the square braces is secular: it grows without bound for large $t$. Specifically, for $t = O(\epsilon^{-1})$ we have that 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMxMTg2OTMyMl19
-->