2024-07-30 23:08

Status:
#in-progress

Tags:
[[cp]]
[[cs]]
[[graph theory]]


___________________________________________________________________________
# BFS explained

**What?**
- A method for graph/grid/tree traversal that checks all close nodes before any farther nodes (layer by layer)
	- Does this with a ==togo== queue and a ==visited== set
		- Add first node to togo and visited
		- Find all neighbours, put them in ==togo== and then visit ==each== one, marking them down accordingly
			- Includes their neighbours
		- Do this until all ==visited== and no more ==togo==
- If grid:
	- Use lists with directions (up, down, left, right)
		- `int diffRow[] = {1, -1, 0, 0}`
		- `int diffCol[] = {0, 0, -1, 1}`
	- Also use `isValid()` to check for any invalid grids (i.e. obstacles)
- If graph:
	- Use adjacency list
```c++
void addEdge(vector<vector<int>>& adjList, int u, int v) {
	adjList[u].push_back(v);
	adjList[v].push_back(u);
}
```

**Code:**
Grid:
```c++
//defining necessary DS
vector<vector<bool>> visited(n, vector<bool>(m, false));
vector<vector<int>> distance(n, vector<int>(m, INT_MAX));
queue<pair<int, int>> togo;

//adding first point (0, 0)
togo.push({0, 0});
visited[0][0] = true;
distance[0][0] = 0;

while (!togo.empty()) {
        pair<int, int> curr_cell = togo.front();
        //curr row
        int y = curr_cell.first;
        //curr col
        int x = curr_cell.second;

		//removing node
        togo.pop();

		//going through the possiblities
        for (int i=0; i<4; i++) {
            //new row
            int adj_y = y + diff_Row[i];
            //new col
            int adj_x = x + diff_Col[i];

            if (isValid(visited, grid, adj_y, adj_x)) {
                togo.push({adj_y, adj_x});
                visited[adj_y][adj_x] = true;
                distance[adj_y][adj_x] = distance[y][x] + 1;
            }

        }

    }

```



Graph:
```c++

//all the data structures necessary
unordered_set<int> visited;
queue<int> togo;
vector<int> path_len(n+1, INT_MAX);

//adding first node
visited.emplace(a);
togo.push(a);
path_len[a] = 0;

//(basically just all neighbor nodes)
vector<int> vals;

//while there are still nodes to go to
while (!togo.empty()) {
		//get current node
        int curr_node = togo.front();

		//if found the answer node
        if (curr_node == b) {
            cout << path_len << endl;
            break;
        }
        //remove node
        togo.pop();

		//for all neighboring nodes (from the adjacency list)
        vals = adjList[curr_node];
        for (auto next: vals) {
	        //if not yet visited -> add them to the queue to visit
            if (visited.find(next) == visited.end()) {
                togo.push(next);
                visited.emplace(next);
                //adding length
                path_len[next] = path_len[curr_node] + 1;
            }
        }
    }
```


# References

