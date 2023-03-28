## An Tree Representation of an Array
![[Heap Tree 2022-11-19 14.32.27.excalidraw]]

# Representation Rules 

## Left Child : $A[2 * i + 1]$
## Right Child : $A[2 * i + 2]$
## Father Node : $A[i / 2]$
## Rule: $A[Parent(i)] \gt A[i]$
## Rule : $\text{IndexOf}(\text{Last Non Leaf}) = (\frac{Lenght}{2}) - 1$

# Build Heap by Heapify

###### Process to build an [[Heap Tree]]
###### In Recursion, substitute the min or max child an swap it with the father.
##### Do it with all the non leaf nodes.

![[Heap Tree 2022-11-19 15.47.06.excalidraw]]