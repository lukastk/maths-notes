# Fitting distributions to binned data

We have random variable $X$ which is distributed according to the PDF $f(x|\theta)$. We draw $n$ samples $\chi = \{x_i\}_{i=1}^{n}$ from the distribution, and then bin them into $m$ bins

$$
y_i = \sum_{i=1}^m \int_{h_i}^{h_{i+1}} dx\ \delta(x_i - x)
$$

where $h_i,\ i=1,\dots, m$ are the bin boundaries.

Whereas the likelihood fun
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyNDc5NjExMTksLTc4MDczMzI5OF19
-->