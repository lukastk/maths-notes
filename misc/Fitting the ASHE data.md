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

If we impose differentiability, then we get $\mu = \log(\tau) - \alpha \sigma^2$, and $r$ simplifies to

$$
r(\sigma^2, \alpha)= \frac{ \sqrt{2\pi} \alpha \sigma \Phi(\alpha \sigma) e^{\frac{1}{2} {\alpha \sigma}^2}}{ \sqrt{2 \pi} \alpha \sigma \Phi(\alpha \sigma) e^{\frac{1}{2} {\alpha \sigma}^2} + 1 }
$$



## References

Statistical analysis of the
Lognormal-Pareto distribution
using Probability Weighted
Moments and Maximum Likelihood - Marco Bee

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQxODY4OTY2Nl19
-->