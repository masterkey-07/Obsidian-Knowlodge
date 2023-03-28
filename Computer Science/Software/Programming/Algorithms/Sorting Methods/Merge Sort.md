### This Sort method follow the strategy of [[Divide and Conquer]]

### By Diving the problem, it is more easy to sort two numbers than multiple ones. And so, it is more effective to merge and sort two sorted subarrays.

Diagram of the process:
![[Merge Sort 2022-10-30 00.13.48.excalidraw]]

## **[[C]] Implementation**

```C
void merge(int *array, int start, int middle, int end)
{
	int first_length = middle - start + 1;
	int second_length = end - middle;
	int i, j, k;
	int first_array[first_length], second_array[second_length];

	for (i = 0; i < first_length; i++)
		first_array[i] = array[start + i];
	
	for (i = 0; i < second_length; i++)
		items_b[i] = array[middle + i + 1];

	i = 0;
	j = 0;
	k = start;

	while (i < first_length && j < second_length)
		if (first_array[i] <= second_array[j])
			array[k++] = first_array[i++];
		else
			array[k++] = second_array[j++];

	while (i < first_length)
		array[k++] = first_array[i++];
  
	while (j < second_length)
		array[k++] = second_array[j++];
}

  

void merge_sort(int *array, int start, int end)
{
	if (end <= start)
		return;

	int middle = (start + end) / 2;

	merge_sort(array, start, middle);
	merge_sort(array, middle + 1, end);
	merge(array, start, middle, end);
}
```
