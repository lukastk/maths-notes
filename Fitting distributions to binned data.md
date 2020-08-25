# Fitting distributions to binned data

We have random variable $X$ which is distributed according to the PDF $f(x|\theta)$. We draw $n$ samples $\chi = \{x_i\}_{i=1}^{n}$ from the distribution, and then bin them into $m$ bins $\psi= \{ y_j \}_{j=1}^m$ where

$$
y_j = \sum_{j=1}^m \int_{h_j}^{h_{j+1}} dx\ \delta(x_j - x)
$$

where $h_i,\ i=1,\dots, m+1$ are the bin boundaries.

The likelihood function over the sample set itself is

$$
L(\theta | \chi) = \prod_{i=1}^n f(x_i|\theta)
$$

implicitly assuming a uniform prior, and discarding overall constants.

For the binned data, the likelihood function is instead

$$
\begin{aligned}
L(\theta | \psi) & = \prod_{j=1}^m \left(\int_{h_j}^{h_{j+1}} dx\ f(x|\theta)\right)^{y_j} \\
& = \prod_{j=1}^m \left( F(h_{j+1}|\theta) - F(h_{j}|\theta) \right)^{y_j}
\end{aligned}
$$

where $F(x|\theta)$ is the CDF of $X$.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTczOTgzNjQ0OCwtNzgwNzMzMjk4XX0=
-->