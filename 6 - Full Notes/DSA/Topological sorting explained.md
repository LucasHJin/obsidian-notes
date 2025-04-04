2024-08-15 11:30

Status:


Tags:
[[cs]]
[[cp]]
[[graph theory]]


___________________________________________________________________________
# Topological sorting explained

**Requirements:** 
- [[Directed acrylic graphs explained]]

**What?** 
- Is a method of sorting a DAG such that for every directed edge $(u,v)$, the vertex $u$ comes before $v$ in the ordering
	- So that you check all the required nodes to get the correct value for future nodes

**How?**
- **DFS based:** 
	- For each unvisited node, you recursively call the nodes adjacent nodes (which then recursively call their own neighbors)
		- Then, if you have $u_{a1}$ leading to $v_{a1}$, $v_{a2}$, ... where they each lead to more respectively:
			- You will go down $v_{b1}$, $v_{c_1}$ and so on in case $v_{a_2}$ is dependent on $v_{c1}$ for example
	- Basically:
		- ==Go down one path completely, push to the back the end node, then go back one node and if no other paths, push in front that node and so on and so forth ==
			- Do this for each starting node (if not yet visited -> if visited then it was in the path of another node (not starting))
	- Do this with a stack and vector
	-  ![[Screenshot 2024-08-22 at 11.30.07 AM.png]]
- **Kahn's Algorithm (BFS based):** 
	- Repeatedly remove nodes without **dependencies** and add them to the topological ordering (because no dependencies = starting point)
		- This creates more nodes w/o dependencies
	- Repeat until all nodes are processed or cycle is discovered
	- I.e. ![[Screenshot 2024-08-22 at 11.36.27 AM.png|400]] 
		- 2 -> then (0 or 4)
		- 0 -> then 4 is only free
		- 4 -> then can choose 3 or 5
		- 3 -> only 5 is free
		- 5 -> 1
	- **How to do it:**
		- Loop through graph and create the **inDegree** by incrementing the ID of each destination node
		- Use array of **inDegree** (incoming degree) and a **queue** (add only to the queue when the inDegree is 0)
			- ==Use a priority queue when you want smallest or greatest first== 
		- Then decrease the degree of all attached nodes to the processed node by 1
			- Check if can be added to queue (inDegree = 0)
		- ==If the queue is empty and there are still nodes in the graph, the graph contains a cycle and cannot be topologically sorted.== 


**Code:** 
**DFS**
```c++
void topologicalSort(int v, vector<vector<int>>& adjList, vector<bool>& visited, stack<int>& togo) {

    visited[v] = true;
    
    for (int i: adjList[v]) {
        if (!visited[i]) {
            topologicalSort(i, adjList, visited, togo);
        }
    }

    togo.push(v);
}

int main() {
	stack<int> togo;
    vector<bool> visited(n+1, false);

	for (int i = 1; i <= n; i++) {
        if (!visited[i]) {
            topologicalSort(i, adjList, visited, togo);
        }
    }
}

```

**BFS** 
```c++
// Vector to store indegree of each vertex
vector<int> indegree(V);
for (int i = 0; i < V; i++) {
	for (auto it : adj[i]) {
		indegree[it]++;
	}
}

// Queue to store vertices with indegree 0
queue<int> q;
for (int i = 0; i < V; i++) {
	if (indegree[i] == 0) {
		q.push(i);
	}
}
vector<int> result;
//Go through the queue and add any indegree=0 nodes while processing the rest
while (!q.empty()) {
	int node = q.front();
	q.pop();
	result.push_back(node);

	// Decrease indegree of adjacent vertices as the
	// current node is in topological order
	for (auto it : adj[node]) {
		indegree[it]--;

		// If indegree becomes 0, push it to the queue
		if (indegree[it] == 0)
			q.push(it);
	}
}

// Check for cycle
if (result.size() != V) {
	cout << "Graph contains cycle!" << endl;
	return {};
}

return result;
```



# References
https://www.geeksforgeeks.org/topological-sorting/ 
https://www.geeksforgeeks.org/topological-sorting-indegree-based-solution/
