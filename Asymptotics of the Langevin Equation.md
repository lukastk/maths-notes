
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

$$\kappa = \nu \exp ( - \beta E_b ) \quad (2)$$

where $\kappa$ is either the reaction rate or the diffusion coefficient. $E_b$ would be some sort of activation energy for the reaction.

In the case of a bistable potential $\kappa$ would give the rate of the particle moving between minima. $\kappa$ could be the diffusion coefficient if we have a periodic potential.

### Friction asymptotics

If the temperature is held fixed, the only parameter left is the friction $\gamma$. The large/small friction asymptotics can be expressed in terms of a slow/fast system of SDEs.

In many applications (especially in Biology), the friction coefficient is large $\gamma \gg 1$, in which case the momentum is the fast variable, which we can eliminate to obtain an equation for the position. This is the **overdamped** or **Smoluchowski** limit.

For $\gamma \ll 1$ the position is the fast variable, whereas the energy is the slow variable. We can eliminate the position, and obtain an equation for the energy. This is the **underdamped** or **Freidlin-Wentzell** limit.

In both cases, we have to look at sufficiently long time scales. Rescale the solution to (1)

$$x(t) \to x^\gamma(t) =  \lambda_\gamma x (t / \mu_\gamma) \quad (3)$$

in which case the rescaled process $x^\gamma$ satisfies the equation

$$\ddot{x}^\gamma = - \frac{\lambda_\gamma}{\mu_\gamma^2} \partial_x V(x^\gamma/\lambda_\gamma) - \frac{\gamma}{\mu_\gamma} \dot{x}^\gamma + \sqrt{2 \gamma \lambda_\gamma^2 \mu_\gamma^{-3} \beta^{-1}} \dot{W} \quad (3).$$

Different choices for these two parameters leads to the overdamped and underdamped limits.

#### Overdamped limit

Take $\lambda_\gamma =1$, $\mu_\gamma = \gamma^{-1}$ and $\gamma 

## References

- [These slides](http://wwwf.imperial.ac.uk/~pavl/lec_freid_wentz_smooluch.pdf)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU2NzE5NDI3Miw1OTI0MjE3MDEsMTY1Nz
k4MTE5MV19
-->