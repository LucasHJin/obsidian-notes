2025-06-24 14:52

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# React - Context

**Context API:** feature that allows you to manage the global state of your application without the need to pass data through multiple levels of components using props
- I.e. don’t need to pass through multiple parents and children
- Useful for:
	- Auth
	- Light/dark mode
	- Cart systems (ecommerce) 
- ==Alternative option to lifting state up to parents and passing as props== 
	- Can get from any depth as long as nested inside provider

**Key elements:** 
- `createContext` → can take any value (default value of context) and returns context object to be pass down data to components
- `useContext` → accepts context object as a parameter and gets the necessary data for the component
- `ContextObject.Provider` → is a component that accepts a prop called `value` → context value passed down to ALL components
	- Provider component of context object

**Drawbacks:** 
- Performance issues → every component using the context re-renders on state update
- Code is less organized

**Potential solutions:** 
- Use multiple smaller contexts
- Don’t use it → https://www.robinwieruch.de/react-component-composition/

```js
'use client';
import { createContext, useState, useContext } from 'react';

// 1. Create context
const AuthContext = createContext();

// 2. Export a provider component
export const AuthProvider = ({ children }) => {
  const [user, setUser] = useState(null);

  const login = (userData) => setUser(userData);
  const logout = () => setUser(null);

  return (
    <AuthContext.Provider value={{ user, login, logout }}>
      {children}
    </AuthContext.Provider>
  );
};

// 3. Helper hook to use the auth context
export const useAuth = () => useContext(AuthContext);

------------------------------------------------------------

import { AuthProvider } from '../auth-context';

export default function RootLayout({ children }) {
  return (
    <html>
      <body>
        <AuthProvider>{children}</AuthProvider>
      </body>
    </html>
  );
}

------------------------------------------------------------

'use client';
import { useAuth } from '../auth-context';

export default function Profile() {
  const { user, login, logout } = useAuth();

  if (!user) {
    return <button onClick={() => login({ name: 'Lucas' })}>Login</button>;
  }

  return (
    <>
      <p>Welcome, {user.name}!</p>
      <button onClick={logout}>Logout</button>
    </>
  );
}

```





# References

