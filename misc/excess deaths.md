Let $D_{ij}$ be the number of deaths during week $i$ of year $j = 1, \dots, n$, and let $N_{ij}$ be the population during the same time. The weekly death rate at that time is then $d_{ij} = \frac{D_{ij}}{N_{ij}}$.

The average weekly death rate during week $i$ of any given year is

$$
\bar{d}_i = \frac{1}{n} \sum_j d_{ij}
$$

and the standard deviation is

$$
\text{STD}[d_i] = \sqrt{ \frac{1}{n} \sum_{j=1}^n (d_j - \bar{d}_j)^2 }
$$

---

Herd immunity is reached when a large enough proportion of the population is immune (either recovered or vaccinated), where the immunized serve as a buffer, lowering the probability of secondary infections.

The herd immunity criterion is

$$
h = \frac{R_0 - 1}{R_0}
$$

where $R_0$ is the basic reproductive ratio, which is the number of secondary infections produced by a typical case of an infection in a population where everyone is susceptible.

As the basic reproductive ratio is both a function of the inherent infectivity of the pathogen, as well as the social contact structure of the susceptibles, $R_0$ has a lower value during lock-down. This is why there is often talk about "keeping $R_0$ below $1$" in the media.

Estimates for $R_0$ of the COVID-19 virus vary from $1.4$ to $5.7$ [Ref: 1-4], outside of a lock-down. Using the conservative estimate of $R_0 = 1.4$, we can estimate the herd immunity criterion to be $h \sim 28.7\%$. This would mean approximately $19$ million of the UK's $66.65$ million inhabitants would have to be infected for herd immunity to be reached.

Current estimates 

References:

[1] - https://www.nejm.org/doi/10.1056/NEJMoa2001316

[2] - https://www.eurosurveillance.org/content/10.2807/1560-7917.ES.2020.25.4.2000058

[3] - https://www.nature.com/articles/s41591-020-0822-7

[4] - https://wwwnc.cdc.gov/eid/article/26/7/20-0282_article

[5] - https://post.parliament.uk/analysis/models-of-covid-19-part-3/
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgxMjE2MDg3NSwtMjMyMjQ4OTMyLDgyOD
E4NjMxMV19
-->