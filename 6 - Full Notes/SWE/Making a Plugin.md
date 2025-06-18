2025-06-07 15:28

Status:
#in-progress

Tags:
[[todo]] 
[[cs]] 


___________________________________________________________________________
# Making a Plugin

**Diagram:** 
![[Pasted image 20250608105056.png]] 

**Important commands:** 
- `npm run dev` → keep it running during development to update the plugin
- `cmd + option + i` for developer tools
- `this.app.emulateMobile(!this.app.isMobile);` in the developer tools → toggles if it acts like a mobile device or not
- For status bar → create in same item if you want smaller spacing
- `getLeaf(true)` → creates a leaf in root
- `detach()` → deletes leaf

**Important components:** 
- `Setting`: UI helper class that lets you quickly create clean and consistent UI elements inside plugin settings panels or modals
	- I.e. labeled text inputs, buttons, toggles, dropdowns, etc.
	- Pass `this.contentEl` → content area of the surrounding element
- `Partial<Type>` → TypeScript utility that returns a type with all properties set to optional
	- Allows for type checking + only need to define defaults for desired proper
- **View:** how Obsidian displays content
	- You should extract the id of a view to a constant
	- Need to use `unload` to cleanup view after unregister
	- Use `getLeavesOfType()` to access instances of view
	- **Factory function:** creates and returns an object
		- I.e. `(leaf) => new ExampleView(leaf)` 
- **Parents:** one of the two types of nodes (workspace items) in the [visible content](https://docs.Aobsidian.md/Plugins/User+interface/Workspace) 
	- Can contain leafs and other parents
	- **Splits:** type of parent that shows child items side by side
	- **Tabs:** type of parent that shows only one child item at a time
- **`leaf` or `WorkspaceLeaf`**: a visual "pane" in the app UI that can display a view
	- I.e. like a split screen view
	- Can show:
		- A markdown note
		- A custom plugin view
		- A search result
		- Graph view
	- Can link views together by grouping leafs
- **`Editor`:** allows you to manipulate the MD doc in edit mode
	- 
 
**Styling:** 
- Use logical instead of directional properties ([link](https://docs.obsidian.md/Plugins/User+interface/Right-to-left))
	- I.e. `margin-inline-start` instead of `margin-left` 
- `plaintext` → used for single line that might be too long

**Can add HTML elements:**
- https://docs.obsidian.md/Plugins/User+interface/HTML+elements 

*Note:* Use arrow functions instead of regular
- Preserves `this.` to reference the plugin instance

**Publishing the plugin:** 
- https://docs.obsidian.md/Plugins/Releasing/Submit+your+plugin

# References
- [Video](https://www.youtube.com/watch?v=AgXa03ZxJ88) 
- [Official Docs](https://docs.obsidian.md/Plugins/Getting+started/Build+a+plugin) 
