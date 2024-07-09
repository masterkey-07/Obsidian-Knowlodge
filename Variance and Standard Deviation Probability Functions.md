### Variance
**In Continuous Variables**

$$\sigma^2 = \text{Var}(x) = \int_{-\infty}^{+\infty} [x - E(X)]^2 \cdot f(x) \ dx$$

**In Discrete Variables**

$$\sigma^2 = \text{Var}(X) = \sum_{i=0}^{n} [x_i - E(X)]^2 \cdot f(x_i)$$

**Properties**

- $\text{Var}(X) \geq 0$
- $\text{Var}(X + c) =\geq= \text{Var}(X)$
- $\text{Var}(bX) =\geq= b^2\text{Var}(X)$
- $\text{Var}(c + bX) = b^2\text{Var}(X)$

### Standard Deviation

$$\sigma = \sqrt{\sigma^2}$$

**Properties**
- $\text{Std.Dev}(X) \geq 0$
- $\text{Std.Dev}(X + c) = \sqrt{\text{Std.Dev}(X)}$
- $\text{Std.Dev}(bX) =\geq= |b|\sqrt{\text{Std.Dev}(X)}$
- $\text{Std.Dev}(c + bX) = |b|\sqrt{\text{Std.Dev}(X)}$
