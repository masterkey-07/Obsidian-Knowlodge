## **Problem**

Given multiples sorted array, remove the lowest value of the arrays.
By doing this multiple times, sum all the lowest value of each array, than print it.

## Example Input

```
3 2
3 4 5 6
2 2 3
4 1 2 3 4
```

removing by one time (2 - 1) the lowest values...

```
4 5 6
2 3
2 3 4
```

## **Resolving**

### **Method 1** : Total Sort

### Joining all arrays, and then sorting it all with a stable sorting method ([[Merge Sort]])
### And then remove easly all the lowest values blazing fast.

### **Score** : 59/100

### **Method 2** : Binary Tree

### To Implement