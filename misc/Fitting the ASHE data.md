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

is the Pareto distribution.

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
F_1(x;\mu,\sigma^2,\tau)=\frac{1}{\Phi \left( \frac{\log(\tau)-\mu}{\sigma} \right)} \left( \frac{1}{2} + \frac{1}{2} \text{erf}\left[ \frac{\ln x - \mu}{\sqrt{2}\sigma} \right] \right)
$$



#### References

Statistical analysis of the Lognormal-Pareto distribution using Probability Weighted Moments and Maximum Likelihood - Marco Bee

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTEyMzYxMzc1MiwtMzY3MjE4MTQzLC0xMT
AzNzMyMDU3LDExMTQ3MDI2MTEsLTIwNjI3MjAwNzNdfQ==
-->