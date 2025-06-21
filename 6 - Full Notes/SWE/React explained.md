2024-09-24 12:46

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# React explained

**React:** a JavaScript library used to build user interfaces, especially for web applications
- Breaks down the website into key [[React - Components|reusable components]] 
	- Runs on [[React - JSX|JSX]] 
- Uses a virtual [[Javascript - DOM Manipulation & Events|DOM]] 
	- Only refreshes/updates parts of page that need to be updated rather than everything
	- Doesn’t actually manipulate the DOM manually with your code
- [[React components vs JS classes|Uses components instead of classes]]

[[Node explained|How to run javascript outside the web browser environment]]

**How to create a React project:** 
1. Install Node.js
	1. `node -v` 
	2. `npm -v` 
2. Navigate to proper directory
3. Create a new Vite project
	1. `npm create vite@latest your-project-name -- --template react` 
4. Navigate into the new project directory
	1. `cd your-project-name` 
5. Install dependencies
	1. `npm install` 
6. Run the development server (to see website)
	1. `npm run dev` 

**Key React Ideas:** 
- [[React - Components]] 
	- [[React - Keys]] 
	- [[React - Props]] 
	- [[React - Lifecycles]]
	- [[React - Class Based Components]] 
- [[React - Hooks]] 
	- [[React - State]] 
		- [[React - useState]] 
		- [[React - Rendering]] 
		- [[React - Updater Functions]] 
	- [[React - useEffect]] 
	- [[React - useContext]] 
	- [[React - useRef]]

**Less Key** 
- [[Javascript - onChange]]
- [[Javascript - Linting]] 

___

**React Native:** open-source framework that allows developers to build mobile applications using JavaScript and React
- Is crossplatform -> IOS and Android
- [[React Native explained]] 

# References

