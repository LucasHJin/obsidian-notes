2025-06-26 14:18

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# React - useMemo

*Note:* [Profiler component](https://react.dev/reference/react/Profiler) can be used to measure performance

**useMemo hook:** allows for memoization inside components
- **Memoization:** optimization technique in programming where the results of expensive function calls are stored (or cached) so that when the same inputs occur again, the stored result is returned instead of recomputing it
	- ==Remembering instead of recalculating==
	- Used in [[Dynamic programming explained|dynamic programming]]  
- Value is only recalculated when dependencies change

Example:
```js
import { useMemo } from "react";

function Cart({ products }) {
  const totalPrice = useMemo(() => {
    return products.reduce(
      (total, product) => total + product.price * product.quantity,
      0
    );
  }, [products]);

  return (
    <div>
      {/* Some other content in the cart */}
      {/* Products to display */}
      <p>
        Total Price: <strong>${totalPrice}</strong>
      </p>
      {/* Some button to checkout */}
    </div>
  );
}
```
- Will use the cached value for totalPrice unless products changes
	- Same syntax as [[React - useEffect|useEffect]] 

**`memo` wrapper:** skips re-rendering a component when its props are unchanged (applies even if parent re-renders)
- Only re-renders if own props/state changes
```js
import { useState, memo } from "react";

const ButtonComponent = memo(({ children, onClick }) => {
  let i = 0;
  let j = 0;
  const ITERATION_COUNT = 10_000;
  while (i < ITERATION_COUNT) {
    while (j < ITERATION_COUNT) {
      j += 1;
    }
    i += 1;
    j = 0;
  }

  return (
    <button type="button" onClick={onClick}>
      {children}
    </button>
  );
});
```

**`useCallback` hook:** allows for memoizing functions specifically
- Only 1 arrow function instead of 2 
```js
const memoizedValue = useMemo(() => {
  return () => {
    console.log('This is a function returned by useMemo');
  };
}, [/* dependencies */]);

// VS

const memoizedFunction = useCallback(() => {
  console.log('This is a memoized function');
}, [/* dependencies */]);
```






# References

