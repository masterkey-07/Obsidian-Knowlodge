
# Truth Table of AND  

| A   | B   | C   | Result |
| --- | --- | --- | ------ |
| 0   | 0   | 0   | 0      |
| 0   | 0   | 1   | 0      |
| 0   | 1   | 0   | 0      |
| 1   | 0   | 0   | 0      |
| 1   | 0   | 1   | 0      |
| 1   | 1   | 0   | 0      |
| 1   | 1   | 1   | 1      | 

# Sum of Products (SOP)

## Description : Built with a Truth Table 

## Example : $ABC + A\bar{B}C + A\bar{B}\bar{C}$

# AND Theorems

- ## $x \times 0 = 0$
- ## $x \times x = x$
- ## $x \times 1 = x$
- ## $x \times \bar{x} = 0$

# OR Theorems

- ## $x + 0 = x$
- ## $x + x = x$
- ## $x + 1 = 1$
- ## $x + \bar{x} = 1$

# Multivariable Theorems

- ## Commutative Laws
	- ## $x + y = y + x$
	- ## $x \times y = y \times x$
- ## Associative Laws
	- ## $x + (y + z) = (x + y) + z = x + y + z$
	- ## $x  (y  z) = (x  y)  z = x  y  z$
- ## Distributive Law
	- ## $x(y + z) = xy + xz$
	- ## $(w + x)(y + z) = wy + wz + xy + xz$
	- ## $x + xy = x$
	- ## $x + \bar{x}y = x + y$
	- ## $\bar{x} + xy = \bar{x} + y$  
- ## DeMorgan Theorems 
	- ## $\bar{(x + y)} = \bar{x} \times \bar{y}$
	- ## $\bar{(x \times y)} = \bar{x} + \bar{y}$

# NAND and NOR Equivalents

- ## NAND 
	- ## $\bar{(A \times A)} = \bar{A}$ 
	- ## $\bar{(\bar{(AB)})} = AB$
	- ## $\bar{(\bar{A}\bar{B})} = \bar{\bar{A}} + \bar{\bar{B}} = A + B$
- ## NOR 
	- ## $\bar{(A + A)} = \bar{A}$ 
	- ## $\bar{(\bar{(A + B)})} = A + B$
	- ## $\bar{(\bar{A} + \bar{B})} = \bar{\bar{A}} \times \bar{\bar{B}} = A \times B$