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
f_2(x ; \tau, \alpha) = \frac{\alpha \tau^\alpha}{x^{\alpha+1}} \mathbb{I}_{ \{ x > \tau \}} 
$$

is the Pareto distribution. We presume that $\alpha > 1$ henceforth.

The parameter space is reduced by enforcing continuity on the distribution, which gives

$$
r(\mu, \sigma^2, \alpha, \tau)= \frac{ \sqrt{2\pi} \alpha \sigma \Phi(\tau^*) e^{\frac{1}{2} {\tau^*}^2}}{ \sqrt{2 \pi} \alpha \sigma \Phi(\tau^*) e^{\frac{1}{2} {\tau^*}^2} + 1 }
$$

where $\tau^* = (\log(\tau) - \mu)/\sigma$.

If we impose differentiability, we get $\mu = \log(\tau) - \alpha \sigma^2$, and $r$ simplifies to

$$
r(\sigma^2, \alpha)= \frac{ \sqrt{2\pi} \alpha \sigma \Phi(\alpha \sigma) e^{\frac{1}{2} (\alpha \sigma)^2}}{ \sqrt{2 \pi} \alpha \sigma \Phi(\alpha \sigma) e^{\frac{1}{2} (\alpha \sigma)^2} + 1 }
$$

### Normalization and the CDF

$F(x |\theta)$ is the CDF of the Log-Normal-Pareto distribution.

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

where $\Phi$ is the Standard Normal Distribution.

To normalize $f$, we compute $F$ as $x \to \infty$.

$$
\begin{aligned}
\lim_{x \to \infty} F(x;\theta) & = r \left( F_1(\tau;\mu,\sigma^2,\tau) \right) + (1-r)  \\
& = r \left( \frac{1}{\Phi \left( \frac{\log(\tau)-\mu}{\sigma} \right)} \left( \frac{1}{2} + \frac{1}{2} \text{erf}\left[ \frac{\ln \tau - \mu}{\sqrt{2}\sigma} \right] \right) \right) + (1-r) \\
& \equiv \mathcal{N}(\theta)
\end{aligned}
$$

We re-normalize the distributions as follows:

$$
f(x | \theta) = \frac{1}{\mathcal{N}(\theta)} \left(  r f_1 (x ; \mu, \sigma^2, \tau) + (1-r) f_2(x; \tau, \alpha) \right)
$$

$$
F(x | \theta) = \frac{1}{\mathcal{N}(\theta)} \left( r F_1 (x ; \mu, \sigma^2, \tau) + (1-r) F_2(x; \tau, \alpha) \right)
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

The last data-point to take into consideration is the mean earnings $\bar{x}$. We must have

$$
\int_0^\infty dx\ x f(x | \theta) = \bar{x} \quad (1)
$$

which sets up a dependency $\tau = \tau(\sigma^2, \alpha )$ that reduces our total number of free parameters to 2.

We further evaluate the LHS of (1). The indefinite integral of $x f_1(x|\theta)$ is

$$
-\frac{1}{\mathcal{N}} \sqrt{ \frac{\pi}{2}} e^{ \frac{(\mu + \sigma^2)^2}{2 \sigma^2}} \tau^{ - \frac{2 \mu - \log{\tau}}{2 \sigma^2}} \text{erf} \left( \frac{ \mu + \sigma^2 - \log{x} }{\sqrt{2} \sigma} \right)
$$

and it can be shown that its limit as $x\to0$ is

$$
-\frac{1}{\mathcal{N}} \sqrt{ \frac{\pi}{2}} e^{ \frac{(\mu + \sigma^2)^2}{2 \sigma^2}} \tau^{ - \frac{2 \mu - \log{\tau}}{2 \sigma^2}} 
$$

and so we get that

$$
\int_0^\infty dx\ x f(x | \theta)  =  \frac{1}{\mathcal{N}} \left( r G_1 (\tau ; \mu, \sigma^2, \tau) + (1-r) \frac{\alpha \tau}{\alpha - 1} \right)
$$

where

$$
G_1 (x ; \mu, \sigma^2, \tau) = \sqrt{ \frac{\pi}{2}} e^{ \frac{(\mu + \sigma^2)^2}{2 \sigma^2}} \tau^{ - \frac{2 \mu - \log{\tau}}{2 \sigma^2}} \left[ 1 -  \text{erf} \left( \frac{ \mu + \sigma^2 - \log{x} }{\sqrt{2} \sigma} \right) \right]
$$

and the 2nd term on the RHS is the mean of the Pareto distribution. We get that, for each choice of $\sigma$ and $\alpha$, we must compute $\tau$ numerically by solving the transcendental equation

$$
r G_1 (\tau ; \mu, \sigma^2, \tau) + (1-r) \frac{\alpha \tau}{\alpha - 1} = \bar{x}
$$


#### References

Statistical analysis of the Lognormal-Pareto distribution using Probability Weighted Moments and Maximum Likelihood - Marco Bee

<!--stackedit_data:
eyJoaXN0b3J5IjpbMzA4ODI2NzksMTg0OTEwNTQ0OCw4NjQ1Mj
EyMTgsMjAzOTA0OTIyLC0xNzU5MTI0MTQ0LDkxNjY5ODA5Niwx
MDM3OTQ2MDIyLC03NTczMzc2MDcsMTM5MTI5Njg0NCwyMDUyMz
A1MTE4LC01MTUzMTg3OTQsLTIyMjE0ODMzNywtMTI1Njc0NjM3
NiwtMTYyMDk1MDE2NywtMTg4OTUyMzYwMCwtMzY3MjE4MTQzLC
0xMTAzNzMyMDU3LDExMTQ3MDI2MTEsLTIwNjI3MjAwNzNdfQ==

-->