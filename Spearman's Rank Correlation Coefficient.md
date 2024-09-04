## **Description**
The Spearman coefficient evaluates the monotonic relationship between two variables, which means it assesses whether the variables tend to move in the same direction (either both increasing or both decreasing) or in opposite directions.


## **Equations**

### Rank

If there is a tie, the rank of both are the average of the supposed ranks ($\frac{2 + 3}{2} = 1.5$)

| index | X   | Y   | R(X) | R(Y) |
| ----- | --- | --- | ---- | ---- |
| 1     | 10  | 1   | 1.5  | 3    |
| 2     | 10  | 2   | 1.5  | 2    |
| 3     | 8   | 3   | 3    | 1    |
| ...   | ... | ... | ...  | ...  |

### Difference Between Ranks

#### $$d_i = R(X_i) - R(Y_i)$$

### Spearman's Rank Correlation Coefficient

If there values are distinct

#### $$\rho = 1 - \frac{6 \sum d^2_i}{n(n^2 - 1)}$$

If the values are not distinct

## **Interpretation**
- The value of the Spearman coefficient ranges from -1 to +1.
    - $\rho = +1$: Indicates a perfect positive correlation, meaning as one variable increases, the other variable also increases.
    - $\rho = -1$: Indicates a perfect negative correlation, meaning as one variable increases, the other variable decreases.
    - $\rho = 0$: Indicates no correlation, meaning there is no monotonic relationship between the variables.
