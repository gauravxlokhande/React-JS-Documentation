To call an API in a React application, you can use the `fetch` function or a library like `axios`. The following example demonstrates how to use `fetch` to make an API call within a React component.

### Using `fetch`

1. **Create a component** that calls the API.
2. **Use the `useEffect` hook** to call the API when the component mounts.
3. **Store the fetched data** in a state variable.

Here’s a simple example:

```jsx
import React, { useState, useEffect } from "react";
import "./App.css";

function App() {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    // Replace with your API endpoint
    const apiUrl = "https://api.example.com/data";

    fetch(apiUrl)
      .then(response => {
        if (!response.ok) {
          throw new Error("Network response was not ok");
        }
        return response.json();
      })
      .then(data => {
        setData(data);
        setLoading(false);
      })
      .catch(error => {
        setError(error);
        setLoading(false);
      });
  }, []);

  if (loading) {
    return <div>Loading...</div>;
  }

  if (error) {
    return <div>Error: {error.message}</div>;
  }

  return (
    <div className="Main">
      <h1>Data from API</h1>
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </div>
  );
}

export default App;
```

### Explanation:
- **State Variables**: `data`, `loading`, and `error` are used to manage the fetched data, loading state, and any errors, respectively.
- **useEffect Hook**: This hook makes the API call when the component mounts. The empty array `[]` as the second argument ensures it runs only once.
- **fetch Function**: The `fetch` function is used to make the API call. It returns a promise that resolves to the response.
- **Error Handling**: If the response is not ok, an error is thrown. The error is caught and stored in the `error` state variable.
- **Conditional Rendering**: The component renders loading, error, or data states based on the current state.

### Using `axios`

If you prefer using `axios`, first install it:

```sh
npm install axios
```

Then, use it in your component:

```jsx
import React, { useState, useEffect } from "react";
import axios from "axios";
import "./App.css";

function App() {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    // Replace with your API endpoint
    const apiUrl = "https://api.example.com/data";

    axios.get(apiUrl)
      .then(response => {
        setData(response.data);
        setLoading(false);
      })
      .catch(error => {
        setError(error);
        setLoading(false);
      });
  }, []);

  if (loading) {
    return <div>Loading...</div>;
  }

  if (error) {
    return <div>Error: {error.message}</div>;
  }

  return (
    <div className="Main">
      <h1>Data from API</h1>
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </div>
  );
}

export default App;
```

This `axios` example works similarly to the `fetch` example but uses `axios` to make the API call.
