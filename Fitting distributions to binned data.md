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
L(\theta | \psi) = \prod_{j=1}^m \int_{h_j}^{h_{j+1}} dx\ f(x|\theta)
$$
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwOTE1MDIzNTYsLTc4MDczMzI5OF19
-->