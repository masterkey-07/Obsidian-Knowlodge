```Python
insertion_sort(array = []):

	# For each item
	for i in range(2, len(array)):
		# Select the present item
		key = array[i]

		# Set the previous index
		j = i - 1

		# From this previous index to his expected position
		while (j > 0 and array[j] > key):
			# Move forward items lower than him
			array[j + 1] = array[j]
			j = j - 1

		# Insert the selected item in his expected position
		array[j + 1] = key
```

# Time Complexity of $O(N^2)$
