# Entendendo Limites

Os **limites** são um conceito fundamental no cálculo e ajudam a entender o comportamento de uma função quando sua variável se aproxima de um valor específico, seja finito ou infinito. Com os limites, podemos definir conceitos como continuidade, derivadas e integrais.

## Definição de Limite

O **limite** de uma função descreve o comportamento da função à medida que a variável independente se aproxima de um determinado valor. Formalmente, dizemos que o limite de uma função $ f(x) $ quando $ x $ se aproxima de $ c $ é igual a $ L $ se, para cada valor pequeno $ \epsilon > 0 $, existir um valor pequeno $ \delta > 0 $ tal que, sempre que $ 0 < |x - c| < \delta $, temos $ |f(x) - L| < \epsilon $. Ou seja:

$
\lim_{x \to c} f(x) = L \quad \text{se} \quad \forall \epsilon > 0, \, \exists \delta > 0 \, \text{tal que} \, |x - c| < \delta \Rightarrow |f(x) - L| < \epsilon.
$

Se o limite não existir ou se a função não se aproximar de um valor bem definido, dizemos que o limite é **inexistente**.

## Propriedades do Limite

Algumas das propriedades importantes dos limites incluem:

1. **Limite da soma de funções**:

$
\lim_{x \to c} (f(x) + g(x)) = \lim_{x \to c} f(x) + \lim_{x \to c} g(x),
$

desde que ambos os limites existam.

2. **Limite do produto de funções**:

$
\lim_{x \to c} (f(x) \cdot g(x)) = \lim_{x \to c} f(x) \cdot \lim_{x \to c} g(x),
$

se ambos os limites existirem.

  

3. **Limite do quociente de funções** (se o denominador não for zero no limite):

$
\lim_{x \to c} \frac{f(x)}{g(x)} = \frac{\lim_{x \to c} f(x)}{\lim_{x \to c} g(x)},
$

desde que o limite do denominador não seja zero.

4. **Limite de uma constante multiplicada por uma função**:

$
\lim_{x \to c} [k \cdot f(x)] = k \cdot \lim_{x \to c} f(x),
$

onde $ k $ é uma constante.

## Teorema do Confronto

O **Teorema do Confronto** é útil quando se tem duas funções que "confinam" uma terceira função. Se $ f(x) \leq g(x) \leq h(x) $ para $ x $ em torno de $ c $, exceto em $ c $, e se os limites de $ f(x) $ e $ h(x) $ quando $ x \to c $ são iguais, então o limite de $ g(x) $ também será igual a esse valor.

Formalmente, se:

$
\lim_{x \to c} f(x) = \lim_{x \to c} h(x) = L,
$

e se $ f(x) \leq g(x) \leq h(x) $ para $ x $ próximo de $ c $, então:

$
\lim_{x \to c} g(x) = L.
$

Esse teorema é muito útil para determinar limites de funções difíceis de avaliar diretamente.

## Limites e o Infinito

Os limites também podem ser usados para descrever o comportamento de funções quando a variável $ x $ ou a função $ f(x) $ tende para o infinito. Isso é conhecido como **limite no infinito**.

- **Limite quando $ x \to \infty $**:

$
\lim_{x \to \infty} f(x) = L
$

significa que, à medida que $ x $ cresce indefinidamente, $ f(x) $ se aproxima do valor $ L $.

- **Limite quando $ x \to -\infty $**:

$
\lim_{x \to -\infty} f(x) = L
$

significa que, à medida que $ x $ diminui indefinidamente, $ f(x) $ se aproxima do valor $ L $.

Limites no infinito são importantes para entender o comportamento assintótico das funções, especialmente em casos como funções racionais.

## Teoremas Clássicos

Alguns teoremas clássicos sobre limites incluem:

1. **Teorema da continuidade**: Se uma função é contínua em um ponto $ c $, então o limite da função em $ c $ é igual ao valor da função nesse ponto. Ou seja, se $ f $ é contínua em $ c $, então:

$
\lim_{x \to c} f(x) = f(c).
$

2. **Teorema do limite da função composta**: Se $ \lim_{x \to c} f(x) = L $ e $ \lim_{x \to L} g(x) = M $, então:

$
\lim_{x \to c} g(f(x)) = M.
$

3. **Teorema de L'Hopital**: Se $ \lim_{x \to c} \frac{f(x)}{g(x)} $ resulta em uma indeterminação do tipo $ \frac{0}{0} $ ou $ \frac{\infty}{\infty} $, e se as derivadas de $ f(x) $ e $ g(x) $ existem, então:

$
\lim_{x \to c} \frac{f(x)}{g(x)} = \lim_{x \to c} \frac{f'(x)}{g'(x)},
$

sempre que o limite do lado direito existir.

Esses teoremas e propriedades são a base para o estudo de limites e cálculos mais avançados no cálculo, incluindo derivadas e integrais.