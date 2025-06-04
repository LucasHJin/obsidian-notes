2025-06-03 21:41

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Javascript - npm

**What is it?** 
- A package manager (repo of plugins and libraries) that gives a cli tool to install these packages into the application
	- I.e. can import open source libraries with npm and import them into your files

**package.json** 
- JSON file containing information about our project, such as its name or any dependencies and their version numbers
	- npm can read this file → install necessary dependencies and run scripts

**devDependencies vs dependencies:** 
- `dependencies` → needed for the actual application during runtime (bundled together)
- `devDependencies` → packages that were only necessary during development (not production)
	- I.e. babel plugins and presets, test runners and linter packages.


# References
[[Node explained]] 
