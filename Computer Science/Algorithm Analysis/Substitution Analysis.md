### Create a Hypothesis, then try to prove it.

### Program: $T(n) = 2T(n/2) + n$

### Hypothesis = $O(n \space log \space n) = c \ n \ log \ n$

### Demonstration: 
## $$\displaylines{T(1) = 1 \\ T(2) = 2\ T(1) + 2 = 4\\ T(3) = 2\ T(1) + 3 = 5 \\ \text{So:} \ T(2) \le c\ 2 \ log \ 2 \ \text{AND} \ T(3) \le c \ 3 \ log \ 3 \\ \text{Proving true in the cases T(2) and T(3)}}$$
