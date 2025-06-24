2025-06-24 13:56

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# React - fetch

**Fetch request:** allows you to get information from APIs/the internet
- Involves → [[APIs explained|API]] calls, managing [[React - Components|component state]], handling [[Javascript - Asynchronous Code|async operations]]
	- **NOTE:** use `await` most of the time instead of `.then` chaining
		- And then also use `try / catch` 
	- Has a cleaner and more organized context + modern standard
- Many times → wrapped with `useEffect` to handle on the side
- **Syntax:** `fetch(url, options)` 

**Handling errors:** throw an error using a conditional after the response status
I.e. 
```js
useEffect(() => {
  fetch("https://jsonplaceholder.typicode.com/photos", { mode: "cors" })
    .then((response) => {
      if (response.status >= 400) {
        throw new Error("server error");
      }
      return response.json();
    })
    .then((response) => setImageURL(response[0].url))
    .catch((error) => setError(error));
}, []);
```
- Handle error in `catch` but still throw an error in `.then / try` 
	- It might be a successful connection but wrong data

**Loading state:** can also make it wait until loaded
- Use `try / catch / finally` → set loaded state in finally
```js
const fetchImage = async () => {
      try {
        const response = await fetch("https://jsonplaceholder.typicode.com/photos", {
          mode: "cors",
        });

        if (!response.ok) {
          throw new Error("Server error");
        }

        const data = await response.json();
        setImageURL(data[0].url);
      } catch (error) {
        setError(error);
      } finally {
        setLoading(false); // always runs after try/catch
      }
    };
```

**Custom [[React - Hooks|hooks]]:** a function that lets you use features of React (like states, effects etc.)
- Follows the naming custom of `useX` 
	- Useful because hooks can only be called at top level of component/another hook
```js
import { useState, useEffect } from "react";

const useImageURL = () => {
  const [imageURL, setImageURL] = useState(null);
  const [error, setError] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/photos", { mode: "cors" })
      .then((response) => {
        if (response.status >= 400) {
          throw new Error("server error");
        }
        return response.json();
      })
      .then((response) => setImageURL(response[0].url))
      .catch((error) => setError(error))
      .finally(() => setLoading(false));
  }, []);

  return { imageURL, error, loading };
};

const Image = () => {
  const { imageURL, error, loading } = useImageURL();

  if (loading) return <p>Loading...</p>;
  if (error) return <p>A network error was encountered</p>;

  return (
    <>
      <h1>An image</h1>
      <img src={imageURL} alt={"placeholder text"} />
    </>
  );
};
```
- Can just call useImageURL instead of rewriting the logic
	- Basically → within a function that is already inside a component, can only use hooks if you make it custom

**Managing multiple fetch:** will only start rendering once conditional is true
- Instead → lift fetch up and pass data down
	- I.e. fetch in parent components and pass to child components

**Wrappers for fetch:** 
- [[React - axios|Axios]]



# References
https://blog.logrocket.com/modern-api-data-fetching-methods-react/
