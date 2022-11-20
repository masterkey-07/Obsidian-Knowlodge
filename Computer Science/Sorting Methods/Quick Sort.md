[[Divide and Conquer]] Algorithm

# Explanation 

### Select the Pivot (Usually last item of the Sub Array)

### And Divide the Array using the pivot

### Lesse Than the Pivot in the Left and Greater than in the Right

### And then repeat the process until the Array are sorted

![[Quick Sort 2022-11-20 10.15.29.excalidraw]]





# [[C++]] Example

```   C++
int partition(int arr[], int low, int high)
{
     int pivot = arr[high];   // pivot 
     int i = (low - 1);   // Index of smaller element and indicates 
	 
	 // the right position of pivot found so far 
     for (int j = low; j <= high - 1; j++)
         // If current element is smaller than the pivot 
         if   (arr[j] < pivot) { 
             i++;   // increment index of smaller element 
             swap(&arr[i], &arr[j]); 
         } 

     swap(&arr[i + 1], &arr[high]); 
     
     return   (i + 1); 
 } 

 void quickSort(int arr[], int low, int high) 
 { 
     if (low < high) { 
         int pi = partition(arr, low, high); 
         
         quickSort(arr, low, pi - 1); 
         quickSort(arr, pi + 1, high); 
     } 
 } 
 ```

