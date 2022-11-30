#tolearn 

# Ways of Solving Recursive Fibonacci:
- ## Top Down with Memorization
### Code Example
```Js
const cache = [];

const fibonacci = (n) => {
  if (n <= 1) return n;

  const result = cache[n];

  if (result) return result;

  const output = fibonacci(n - 1) + fibonacci(n - 2);

  cache[n] = output;

  return output;
};
```

### Code Behaviour
![[Dynamic Programming 2022-11-29 21.38.32.excalidraw]]



- ##  Bottom Up

```Js
const fibonacci = (n) => {
  let i, back2 = 0, back1 = 1, next;

  if (n == 2) return 0;

  for (i = 2; i < n; i++){
	  next = back1 + back2;
	  back2 = back1;
	  back1 = next;
  }

   return back1 + back2;
};
```