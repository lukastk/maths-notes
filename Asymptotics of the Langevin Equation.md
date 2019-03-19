
# Asymptotics of the Langevin Equation

## The Smoluchowski and Freidlin-Wentzell Limits

The Langevin equation (with $m=1$):

$$\ddot{x} = - \nabla V(x) - \gamma \dot{x} + \sqrt{2 \gamma \beta^{-1}} \dot{W} \quad (1)$$

There are two parameters in the problem, the friction coefficient $\gamma$ and the inverse temperature $\beta$.

#### The large temperature limit $\beta \ll 1$

The dynamics of (1) is dominated by diffusion. So (1) is approximated by free Brownian motion

$$\dot x = \sqrt{2 \gamma \beta^{-1}} \dot W$$

#### The small temperature limit $\beta \gg 1$

More subtle regime. It leads to exponential, Arrhenius-type, asymptotics for the reaction rate (in the case of a particle escaping from a potential well due to thermal noise), or the diffusion coefficient (in the caes of a particle moving in a periodic potential in the presence of thermal noise).

$$\kappa = \nu \exp ( - \beta E_b )$$

where $\kappa$ is either the reaction rate or the diffusion coefficient. $E_b$ would be some sort of activation energy for the reaction/

**References:**

- [These slides](http://wwwf.imperial.ac.uk/~pavl/lec_freid_wentz_smooluch.pdf)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NDM4MjkwNjRdfQ==
-->