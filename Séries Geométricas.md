**Teorema 3.1** : uMA SÉRIE geométrica

$$\sum_{k=0}^\infty =a+  ar + ar^2 + ar^3 + ar^4 + \dots + ar^n + \dots$$

$$\text{converge se } |r| < 1 (-1 < r < 1) \text{e} diverge se |r|$$



**Demonstração:** 

* $|r| = 1$

$$r = 1 \text{ A série é}$$

$$a +a + a +a+a +a + a +a+a +a + a +a + \dots + a + \dots$$

$$S_n = (n + 1) a => \lim_{n \rightarrow \infty}(n +1) a = \pm\infty$$
$S_1 = a + a$
$S_2 = a + a + a$

A śerie diverge para r = 1

* r = -1

$\sum_{k=0}^\infty a(-1)^k = a -  a + a - a + a - a + \dots$

$$S_1 = a - a = 0$$
$$S_2 = a - a + a = a$$
$$S_2 = a - a + a - a = 0$$

(0,a,0,a,0,a,...) -> sewq. da n-ésima soma parcial (diverge [oscila])

Para r = -1, a śerie diverge


* $|r| \ne 1$

S_n = a + ar + ar^2 + ... + an^n (*)

(*) Multiplicando por r

(**) rS_n = ar + ar^2 + ar^3 + ... ar^n + ar_{n + 1}

Subtraindo (**) de (\*)

S_n - rS_n = a + ar + ar^2 + ... + ar^n - ar - a^r 2 - .... ar^n - ar^{n + 1}

S_n(1-r) = a - ar^{n+1}

S_n = \frac{a(1 - r ^{n+1})}{1 -r}


* |r| < 1 (-1 < r < 1)

\lim_{n \rightarrow \infty} S_n = (\frac{a}{1-r}) \lim_{n \rightarrow \infty}[1 - r^{n+1}]

\* lim_{n \rightarrow \infty}[1] - r lim_{n \rightarrow \infty} r^n 
r lim_{n \rightarrow \infty} r^n = 0 

Para -1 < r <1, a série converge e sua soma $S = \frac{a}{1-r}$


* |r| > 1 (r>1 ou r<-1)

\* \lim_{n \rightarrow \infty}[1] - r \lim_{n \rightarrow \infty} r^n