
![[Analyzing Recursion 2022-11-16 17.46.40.excalidraw]]

## Then :
## $T(n) = c n^2 + \frac{2}{16}cn^2 + (\frac{2}{16})^2 c n^2 + \dots + {(\frac{2}{16})^{log_4 {n - 1}}} \ cn^2 + \theta(n^{log_4 2})$
## $T(n) = \sum_{i=0}^{log_4 {n-1}} (\frac{2}{16})^i \ cn^2 + \theta(n^{log_4 2})$
<br>

## $\sum_{i=0}^{log_4 {n-1}} (\frac{2}{16})^i \ cn^2 + \theta(n^{log_4 2}) < \sum_{i=0}^{\infty} (\frac{2}{16})^i \ cn^2 + \theta(n^{log_4 2})$

<br>

## To calculate... take the right side

## $\frac{1}{1 - (2/16)}cn^2 + \theta(n^{log_4 2}) \to \frac{8}{7}cn^2 + \theta(\sqrt n ) \to O(n^2)$


<br>

```ad-note
title: Geometric Series

## $$\sum_{k=0}^n x^k = \frac{x^{n+1} - 1}{x - 1}$$


## $$\sum_{k=0}^\infty x^k = \frac{1}{1 - x}$$
```
