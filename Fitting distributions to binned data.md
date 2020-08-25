# Fitting distributions to binned data

We have random variable $X$ which is distributed according to the PDF $f(x|\theta)$. We draw $n$ samples $\chi = \{x_i\}_{i=1}^{n}$ from the distribution, and then bin them into $m$ bins $\psi= \{ y_j \}_{j=1}^m$ where

$$
y_j = \sum_{j=1}^m \int_{h_j}^{h_{j+1}} dx\ \delta(x_j - x)
$$

where $h_i,\ i=1,\dots, m+1$ are the bin boundaries.

The likelihood function over the sample set itself is

$$
L(\theta | \psi) = \prod_i f(x_i|\theta)
$$

neglecting prior
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjY2OTkwNTA2LC03ODA3MzMyOThdfQ==
-->