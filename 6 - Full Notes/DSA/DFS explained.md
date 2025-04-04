2024-07-30 23:17

Status:
#in-progress

Tags:
[[cs]]
[[cp]]
[[graph theory]]


___________________________________________________________________________
# DFS explained

**What?**
- A method for graph/grid/tree traversal that checks down one 'lane' completely before the next (goes all the way down and then back up)
- For grids:
	- Use lists with directions (up, down, left, right) and isValid 
	- Go through each of the cardinal directions and immediately recursively call that function
		- Do this until all visited
- For graphs:
	- Use adjacency lists again
	- Then, you can make a function that recursively calls itself
		- Have it check through the neighbours and then for each of the neighbours, call the function for them and so on and so forth until all neighbours of the original node have been investigated (don't forget to mark as visited)
			- This will ensure that you immediately go down a path instead of after all on the same layer
	- ![[Screenshot 2024-07-31 at 2.48.42 PM.png|250]]
- 

**Usecases:** 
- [[Topological sorting explained]]


**Code:**
Grid:
```c++
int n, h;

bool isValid(const vector<vector<bool>>& vis, const vector<vector<int>>& grid, int curr_row, int curr_col, int prev_row, int prev_col) {
    if (curr_row<0 or curr_col<0 or curr_row>=n or curr_col>=n)
        return false;
 
    if (vis[curr_row][curr_col])
        return false;

    if (abs(grid[curr_row][curr_col]-grid[prev_row][prev_col]) > h) {
        return false;
    }
 
    //otherwise valid
    return true;
}

int diff_Row[] = {-1, 0, 1, 0};
int diff_Col[] = {0, 1, 0, -1};

void dfs(vector<vector<bool>>& vis, vector<vector<int>>& grid, int row, int col) {
    //marking current node as visited
    vis[row][col] = true;

	//new nodes
    int dx, dy;

	//go through each of the new nodes -> if valid, immediately recursively call
    for (int i=0; i<4; i++) {
        dx = row+diff_Row[i];
        dy = col+diff_Col[i];

        if (isValid(vis, grid, dx, dy, row, col)) {
            dfs(vis, grid, dx, dy);
        }
    }
}

```

Graph:
```c++
PSEUDOCODE
//if node not in visited:
    //print (node)
    //visited.add(node)
    //for neighbour in graph[node]:
        //dfs(visited, graph, neighbour)

CODE
bool dfs(int node, unordered_set<int>& visited, vector<vector<int>>& adjList) {
    //base case -> found path
    if (node == b) {
        return true;
    }
    
    //unvisited node
    if (visited.find(node) == visited.end()) {
        visited.emplace(node);
        for (auto neighbor: adjList[node]) {
            //don't need to check if visited because will do that in recursive call
            if (dfs(neighbor, visited, adjList)) {
                //if the target node is found in any of the recursive calls, return true
                return true;
            }
        }
    }

    //if already visited node, will go to next one
    return false;
}
```

# References
https://courses.cs.washington.edu/courses/cse326/03su/homework/hw3/dfs.html
