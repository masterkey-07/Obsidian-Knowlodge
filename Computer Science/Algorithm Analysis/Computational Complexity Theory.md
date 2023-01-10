#tolearn 

#### Study from:
- ### [[PAA - Aula 9 - Teoria da Complexidade.pdf]] 
- ### [[Introduction to Algorithms.pdf#page=1069]] 

---

# Polynomial Time Problem (P)

### There is Fast Solutions

## Rules to be Polynomial Time Solvable
- ### There is a Concrete Problem : Set of Binary Strings
- ### If a Problem of Length  $n$ is done in time $n^k$ so it is a Polynomial Time Problem

## Aspects of a Polynomial Time Program
- ### If there is a problem of order $n^k$ there will be a version faster
- ### A Problem solved in Polynomial Time in a Model can be solved in Polynomial Time in Other
- ### If the output of one Polynomial Time algorithm is fed into the input of another, the composite algorithm is polynomial

## Enconding

- ### Enconding is How the format that data is conceived to the program.

- ### Enconding are important for the Time Complexity of a Program
  > The size of the input depends on it Enconding, some encondings make $n$ to $2^n$

---

# Non Deterministic Polynomial Time Problem (NP)

### Can be Verified in Polynomial Time the Solution.

# NP-Completeness

### Can be Verifiend in Polynomial Time but don' (yet) exist a Fast Solution 

## To be NP Complete
- ### $C \text{ is in } NP$
- ### $\text{All NP Problem is reducible to C}$

## If the Second conduction is satisfied, then $C$ is _NP Hard_
---
# Relation between P, NP, NP Complete
![[Computational Complexity Theory 2023-01-10 12.47.15.excalidraw | 300 ]]

---

# Reduction

### Reduce (transform) a problem to another problem, to verify it "hardness".

![[NP-Completeness 2022-12-22 21.56.48.excalidraw|1000]]