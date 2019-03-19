
# Asymptotics of the Langevin Equation

## The Smoluchowski and Freidlin-Wentzell Limits

The Langevin equation (with $m=1$):

$$\ddot{x} = - \nabla V(x) - \gamma \dot{x} + \sqrt{2 \gamma \beta^{-1}} \dot{W} \quad (1)$$

There are two parameters in the problem, the friction coefficient $\gamma$ and the inverse temperature $\beta$.

### The large temperature limit $\beta \ll 1$

The dynamics of (1) is dominated by diffusion. So (1) is approximated by free Brownian motion

$$\dot x = \sqrt{2 \gamma \beta^{-1}} \dot W$$

### The small temperature limit $\beta \gg 1$

More subtle regime. It leads to exponential, Arrhenius-type, asymptotics for the reaction rate (in the case of a particle escaping from a potential well due to thermal noise), or the diffusion coefficient (in the caes of a particle moving in a periodic potential in the presence of thermal noise).

$$\kappa = \nu \exp ( - \beta E_b )$$

where $\kappa$ is either the reaction rate or the diffusion coefficient. $E_b$ would be some sort of activation energy for the reaction.

In the case of a bistable potential $\kappa$ would give the rate of the particle moving between minima. $\kappa$ could be the diffusion coefficient if we have a periodic potential.

### Friction asymptotics

If the temperature is held fixed, the only parameter left is the friction $\gamma$. The large/small friction asymptotics can be expressed in terms of a slow/fast system of SDEs.

In many applications (especially in Biology), the friction coefficient is large $\gamma \gg 1$, in which case the momentum is the fast variable, which we can eliminate to obtain an equation for the position. This is the **overdamped** or **Smoluchowski** limit.

For $\gamma \ll 1$ the position is the fast variable, whereas the energy is the slow variable

**References:**

- [These slides](http://wwwf.imperial.ac.uk/~pavl/lec_freid_wentz_smooluch.pdf)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc2MDE4ODA0MF19
-->