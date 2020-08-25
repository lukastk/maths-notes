### Choice of distribution

We fit the decile data from ASHE using the Log-Normal-Pareto distribution

$$
f(x | \theta) = r f_1 (x ; \mu, \sigma^2, \tau) + (1-r) f_2(x; \tau, \alpha)
$$

where

$$
f_1(x;\mu,\sigma^2,\tau)=\frac{1}{\Phi \left( \frac{\log(\tau)-\mu}{\sigma} \right)} \frac{1}{x \sigma \sqrt{2 \pi}} e^{-\frac{1}{2} \left( \frac{\log(x) - \mu}{\sigma} \right)^2} \mathbb{I}_{ \{0 \le x \leq \tau \}} 
$$

is a truncated Log-Normal distribution, and $\Phi(\cdot)$ is a standard normal distribution, and where

$$
f_2(x ; \tau, \alpha) = \frac{\alpha \theta^\alpha}{x^{\alpha+1}} \mathbb{I}_{ \{ x > \tau \}} 
$$

is the Pareto distribution. We presume that $\alpha > 1$ henceforth.

The parameter space is reduced by enforcing continuity on the distribution, which gives

$$
r(\mu, \sigma^2, \alpha, \tau)= \frac{ \sqrt{2\pi} \alpha \sigma \Phi(\tau^*) e^{\frac{1}{2} {\tau^*}^2}}{ \sqrt{2 \pi} \alpha \sigma \Phi(\theta^*) e^{\frac{1}{2} {\tau^*}^2} + 1 }
$$

where $\tau^* = (\log(\tau) - \mu)/\sigma$.

If we impose differentiability, we get $\mu = \log(\tau) - \alpha \sigma^2$, and $r$ simplifies to

$$
r(\sigma^2, \alpha)= \frac{ \sqrt{2\pi} \alpha \sigma \Phi(\alpha \sigma) e^{\frac{1}{2} {\alpha \sigma}^2}}{ \sqrt{2 \pi} \alpha \sigma \Phi(\alpha \sigma) e^{\frac{1}{2} {\alpha \sigma}^2} + 1 }
$$

### Construction of the likelihood function

The ASHE data has, by sector, the highest annual earnings within the following percentile brackets:

```
0-10, 10-20, 20-25, 25-30, 30-40, 40-50, 50-60, 70-75, 75-80, 80-90
```

Let $n$ be the total number of people in the workforce, then the deciles comprise $n/10$ workers, and the quintiles $n/20$. If we interpret the data as binned microdata (where the bin boundaries have been adjusted so that bins have either populations of $n/10$ or $n/20$), then the likelihood function is

$$
\begin{aligned}
L(\theta | \psi) & = \prod_{j=1}^m \left(\int_{h_j}^{h_{j+1}} dx\ f(x|\theta)\right)^{y_j} \\
& = \prod_{j=1}^m \left( F(h_{j+1}|\theta) - F(h_{j}|\theta) \right)^{y_j}
\end{aligned}
$$

where $h_j,\ j=1,\dots,11$ are the earnings reported in ASHE, and $y_i$ are the bin populations:

$$
y_i = \left\{  \frac{n}{10}, \frac{n}{10}, \frac{n}{20}, \frac{n}{20},\frac{n}{10},\frac{n}{10},\frac{n}{10}, \frac{n}{20}, \frac{n}{20}, \frac{n}{10} \right\}
$$

and $F(x |\theta)$ is the CDF of the Log-Normal-Pareto distribution.

$$
F(x | \theta) = r F_1 (x ; \mu, \sigma^2, \tau) + (1-r) F_2(x; \tau, \alpha)
$$

$$
F_1(x;\mu,\sigma^2,\tau)= \begin{cases}
\frac{1}{\Phi \left( \frac{\log(\tau)-\mu}{\sigma} \right)} \left( \frac{1}{2} + \frac{1}{2} \text{erf}\left[ \frac{\ln x - \mu}{\sqrt{2}\sigma} \right] \right)  &  0  \leq x \leq \tau  \\
\frac{1}{\Phi \left( \frac{\log(\tau)-\mu}{\sigma} \right)} \left( \frac{1}{2} + \frac{1}{2} \text{erf}\left[ \frac{\ln \tau - \mu}{\sqrt{2}\sigma} \right] \right) &  x> \tau 
\end{cases}
$$

$$
F_2(x ; \tau, \alpha) = 1 - \left( \frac{\tau}{x}\right)^\alpha  \mathbb{I}_{ \{ x  > \tau \}} 
$$

where $\Phi$ is the Standard Normal Distribution. The last data-point to take into consideration is the mean earnings $\bar{x}$. We must have

$$
\int_0^\infty dx\ x f(x | \theta) = \bar{x} \quad (1)
$$

which sets up a dependency $\tau = \tau(\sigma^2, \alpha )$ that reduces our total number of free parameters to 2.

We further evaluate the LHS of (1):

$$
\int_0^\infty dx\ x f(x | \theta)  =  r G_1 (\tau ; \mu, \sigma^2, \tau) + (1-r) \frac{\alpha \tau}{\alpha - 1}
$$

where

$$
G_1 (x ; \mu, \sigma^2, \tau) = - \frac{1}{2} e^{ \mu + \frac{\sigma^2}{2}} \text{erf} \left( \frac{\mu + \sigma^2 - \log x}{\sqrt{2} \sigma} \right)
$$

and the 2nd term on the RHS is the mean of the Pareto distribution. We get that, for each choice of $\sigma$ and $\alpha$, we must compute $\tau$ numerically by solving the transcendental equation

$$
r G_1 (\tau ; \mu, \sigma^2, \tau) + (1-r) \frac{\alpha \tau}{\alpha - 1} = \bar{x}
$$


#### References

Statistical analysis of the Lognormal-Pareto distribution using Probability Weighted Moments and Maximum Likelihood - Marco Bee

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAzNzk0NjAyMiwtNzU3MzM3NjA3LDEzOT
EyOTY4NDQsMjA1MjMwNTExOCwtNTE1MzE4Nzk0LC0yMjIxNDgz
MzcsLTEyNTY3NDYzNzYsLTE2MjA5NTAxNjcsLTE4ODk1MjM2MD
AsLTM2NzIxODE0MywtMTEwMzczMjA1NywxMTE0NzAyNjExLC0y
MDYyNzIwMDczXX0=
-->