Solve [[Divide and Conquer]] and Recursion Functions Analysis

## Type of Function this works : $T(n) = aT(n/b) + f(n)$

### Cases :
### - $\text{If } f(n) = O(n^{log_b \ a - \varepsilon}) \ and \ \varepsilon > 0 \implies T(n) = \theta(n^{log_b \ a})$ 

### Resume : $n^{log_b \ a} \lt f(n) \implies T(n) = \theta(n^{log_b \ a})$

### - $\text{If } f(n) = \theta(n^{log_b \ a}) \implies T(n) = \theta(n^{log_b \ a} \ log \ n)$ 

### Resume : $n^{log_b \ a} = f(n) \implies T(n) = \theta(n^{log_b \ a} \ log \ n)$

##### - $\text{If } f(n) = O(n^{log_b \ a + \varepsilon}) \ \text{and} \ \varepsilon > 0 \ \text{and} \ af (\frac{n}{b}) \le cf(n) \ \text{for } c < 1 \implies T(n) = \theta(f(n))$ 

### Resume : $n^{log_b \ a} \gt f(n) \implies T(n) = \theta(f(n))$

