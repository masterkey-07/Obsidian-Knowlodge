## Problem

### best purchase, find the day to buy and the sell.

### data = \[\[10,\_\], \[15,5\], \[5,-10\],... \[value, diff\]\]

### Method : [[Divide and Conquer]]

## Pseudocode :

```C
    max_subarray (A, low, high){
        if (low == high)
            return A[low]
        else
            mid = (low + high) / 2

        max_left = max_subarray(A, low, high)
        max_right = max_subarray(A, low, high)
        max_cross = max_crossing_subarray(A, low, mid, high)

        return max(max_left, max_right, max_cross)
    }

    max_crossing_subarray (A, low, mid, high){
        max_left = -infinity
        sum = 0

        for i=mid down to low
            sum = sum + A[i]
            if sum > max_left
                max_left = sum

        max_right = -infinity
        sum = 0
        for i=mid to high
            sum = sum + A[i]
            if sum > max_right
                max_right = sum

        return max_left + max_right
    }
```
