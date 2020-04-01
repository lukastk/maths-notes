$$
\begin{aligned}
\dot{S} & = - \frac{\beta}{N} IS \\
\dot{R} &  = \gamma I
\end{aligned}
$$

Divide the former by the latter:

$$
\frac{dS}{dR} = - \frac{R_0}{N} S
$$

we get

$$
S(t) = S(0) e^{ -R_0( R(t) - R(0) )  / N}
$$

where $R_0 = \beta/\gamma$.

Now in the $t\to\infty$ limit, we expect $I=0$ and $S(\infty) = N - R(\infty)$. We have

$$
S(\infty) = N -R(\infty) = S(0) e^{ -R_0( R(\infty) - R(0) )  / N}
$$

This is a transcendental equation for $R(\infty)$, and note that $R(\infty) = N$ is not in general a solution. The solution can be found via the Lambert W function:

$$
S(\infty) = N - R(\infty) = - R_0^{-1} W \left( - \frac{S(0) R_0}{N} e^{-R_0(N - R(0)/N} \right) 
$$
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzA0MDQzOTU3XX0=
-->