# Description
### The Automata Can Be Only One State

# Representation 

# $$ A = (Q,\sum,\delta, q_0, F)$$

## $Q$ - States
## $\sum$ : Sets of Data
## $\delta$ : Function to Change State over Data
## $q_0$ : Initial State
## $F$ : Final State

# Example

# $$L = \{w|w \text{ ends with 01}\}$$



```mermaid 
graph LR

q0 -->|0| q1 
q0 -->|1| q0

q1 -->|1| q2   
q1 -->|0| q1

q2 -->|0| q1
q2 -->|1| q0
```