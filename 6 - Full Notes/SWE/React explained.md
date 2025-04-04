2024-09-24 12:46

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# React explained

**React:** a JavaScript library used to build user interfaces, especially for web applications
- Breaks down the website into key **reusable components** 
- Uses a virtual DOM
	- Only refreshes/updates parts of page that need to be updated rather than everything

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
- [[React - Props]]
- [[React - Hooks]]
- [[React - useState]]
- [[React - onChange]]
- [[React - Updater Functions]] 
- [[React - useEffect]]
- [[React - useContext]] 
- [[React - useRef]]

___

**React Native:** open-source framework that allows developers to build mobile applications using JavaScript and React
- Is crossplatform -> IOS and Android

**How to Create React Native Project:** 
1. Create Reactive Native project
	1. `npx react-native init MyApp` 
2. Install dependencies
	1. `npm install` 
3. Start Metro Bundler (what RN uses to package the code)
	1. Navigate to the project directory
	2. Start Metro
		1. `npx react-native start` 
4. Build and run app on IOS simulator
	1. `npx react-native run-ios --simulator="iPhone 14"` 
		1. Only `npx react-native run-ios` is necessary
		2. `xcrun simctl list devices` for all available simulators

# References

