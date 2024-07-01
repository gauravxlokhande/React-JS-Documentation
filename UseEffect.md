Certainly! Here is a basic example of how to use the `useEffect` hook in React.js:

```javascript
import React, { useState, useEffect } from 'react';

const ExampleComponent = () => {
  const [count, setCount] = useState(0);

  // useEffect hook
  useEffect(() => {
    // This effect will run after every render
    document.title = `You clicked ${count} times`;

    // Cleanup function (optional)
    return () => {
      console.log(`Cleanup after count: ${count}`);
    };
  }, [count]); // Dependency array: effect will run when 'count' changes

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
};

export default ExampleComponent;
```

### Explanation:

1. **Importing Hooks:**
   - `useState` and `useEffect` are imported from `react`.

2. **State Initialization:**
   - `count` is initialized to `0` using `useState`.

3. **useEffect Hook:**
   - `useEffect` runs after every render. In this example, it updates the document title with the current count.
   - The effect has a dependency array `[count]`, meaning it will only run when `count` changes.
   - The optional cleanup function logs a message to the console whenever the component unmounts or before the effect runs again.

4. **Component Render:**
   - The component renders a paragraph displaying the count and a button that increments the count when clicked.

This example shows how `useEffect` can be used to perform side effects in a functional component, such as updating the document title or logging to the console.
