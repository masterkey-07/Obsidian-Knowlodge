**Definition**

$$f'(x) = lim_{h \rightarrow 0} \frac{f(x + f) - f(x)}{h}$$

**Rules of Differentiation**

- Constant Rule: $\frac{d}{dx} (c) = 0$, where c is a constant.
- Power Rule: $\frac{d}{dx} (x^n) = n * x^{n-1}$, where $n$ is a constant.
- Constant Multiple Rule: $\frac{d}{dx} (k * f(x)) = k * \frac{d}{dx} (f(x))$, where $k$ is a constant.
- Sum/Difference Rule: $\frac{d}{dx} (f(x) ± g(x)) = \frac{d}{dx} (f(x)) ± \frac{d}{dx} (g(x))$.
- Product Rule: $\frac{d}{dx} (f(x) * g(x)) = f'(x) * g(x) + f(x) * g'(x)$.
- Quotient Rule: $\frac{d}{dx} (\frac{f(x)}{g(x)}) = \frac{g(x) * f'(x) – f(x) * g'(x)}{g(x)^2}$.
- Chain Rule: $\frac{d}{dx} (f(g(x))) = f'(g(x)) * g'(x)$.

**Differentiation of algebraic functions**

- $\frac{d}{dx}(x^n) = nx^{n - 1}, n \in R$
- $\frac{d}{dx}(e^x) = e^x$
- $\frac{d}{dx}(a^x) = a^x \log_e a$
- $\frac{d}{dx}(log_e x) = \frac{1}{x}; x > 0$

**Differentiation of trigonometric functions**

- $\frac{d}{dx}(\sin x) = \cos x$
- $\frac{d}{dx}(\cos x) = -\sin x$
- $\frac{d}{dx}(\tan x) = \sec^2 x$
- $\frac{d}{dx}(\sec x) = \sec (x) \tan (x)$
- $\frac{d}{dx}(\csc x) = -\csc (x) \cot (x)$
- $\frac{d}{dx}(\cot x) = -\csc^2 (x)$

**Exponential Derivatives**

- $f(x) = a^x \text{ then } f'(x) = \ln(a)a^x$
- $f(x) = e^x \text{ then } f'(x) = e^x$
- $f(x) = a^g(x) \text{ then } f'(x) = \ln(a)a^{g(x)} g'(x)$
- $f(x) = e^{g(x)} \text{ then } f'(x) = e^{g(x)}g'(x)$

**Logarithm Derivatives**
- $f(x) = \log_a(x) \text{ then } f'(x) = \frac{1}{\ln(a)x}$
- $f(x) = \ln(x) \text{ then } f'(x) = \frac{1}{x}$
- $f(x) = \log_a(g(x)) \text{ then } f'(x) = \frac{g' (x)}{ln(a)g(x)}$
- $f(x) = \ln(g(x)) \text{ then } f'(x) = \frac{g'(x)}{g(x)}$