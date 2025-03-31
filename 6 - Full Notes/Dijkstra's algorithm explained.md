2024-07-31 14:54

Status:
#in-progress 

Tags:
[[cs]]
[[graph theory]]
[[cp]]


___________________________________________________________________________
# Dijkstra's algorithm explained

**What?**
- A graph traversal algorithm that should be used with a ==**weighted graph**==
	- I.e. ![[Screenshot 2024-07-31 at 2.55.56 PM.png|300]]
	- **Specific requirements:**
		- Graphs with ==positive weights== only
			- Because shortest path is based on adding the values so if there is negative, it might make the value of a node reachable in a shorter distance than what it should be
- If not weighted:
	- [[DFS explained]]
	- [[BFS explained]]

**Use cases:**
- Shortest path from a node to all other reachable nodes
	- I.e. used in GPS

**How does it work?**
- Can start at any node
- Keeps track of the currently known shortest distance from each node to the source node
	- These values are updated if a shorter path is found
- Once the shortest possible path is found (all options are exhausted) -> marked as visited and added to the path
- Continues until all nodes have been added to the path
- Normally use an [[BFS explained|adjacency list]]

**Example:**
- ![[Screenshot 2024-07-31 at 3.01.38 PM.png|300]]
	- Shortest path from node 0 to all other nodes
- Initially, all distances are $\infty$ except for the starting node (0)
	- Also have a list of all unvisited nodes (not yet included in the path)
	- `unvisited = {0, 1, 2, 3, 4, 5, 6}`

| Step | Unvisited                                         | Distance                                             |
| ---- | ------------------------------------------------- | ---------------------------------------------------- |
| 0    | {~~0~~, 1, 2, 3, 4, 5, 6}                         | {==0==, ∞, ∞, ∞, ∞, ∞, ∞}                            |
| 1    | {~~0~~, ~~1~~, 2, 3, 4, 5, 6}                     | {==0==, ==2==, 6, ∞, ∞, ∞, ∞}                        |
| 2    | {~~0~~, ~~1~~, ~~2~~, 3, 4, 5, 6}                 | {==0==, ==2==, ==6==, 7, ∞, ∞, ∞}                    |
| 3    | {~~0~~, ~~1~~, ~~2~~, ~~3~~, 4, 5, 6}             | {==0==, ==2==, ==6==, ==7==, ∞, ∞, ∞}                |
| 4    | {~~0~~, ~~1~~, ~~2~~, ~~3~~, ~~4~~, 5, 6}         | {==0==, ==2==, ==6==, ==7==, ==17==, 22, ∞}          |
| 5    | {~~0~~, ~~1~~, ~~2~~, ~~3~~, ~~4~~, 5, ~~6~~}     | {==0==, ==2==, ==6==, ==7==, ==17==, 22, ==19==}     |
| 6    | {~~0~~, ~~1~~, ~~2~~, ~~3~~, ~~4~~, ~~5~~, ~~6~~} | {==0==, ==2==, ==6==, ==7==, ==17==, ==22==, ==19==} |

==After each distance update of adjacent nodes:==
- Select the node that is closest to the source node based on the current known distances.
- Mark it as visited.
- Add it to the path.

==After:==
- Only analyze new nodes that are **adjacent** to nodes in the path
	- I.e. after step 1 -> can analyze node 2 and node 3
		- EVEN THOUGH YOU ALREADY ANALYZED 2 -> do it again
	- Add the weights of all the edges that form the shortest path to reach that node
	- Only update value if new value is smaller

**Pseudocode:**
```c++
function Dijkstra(Graph, source):
    for each vertex v in Graph.Vertices:
        dist[v] ← INFINITY
        prev[v] ← UNDEFINED
        add v to Q
    dist[source] ← 0
    
    while Q is not empty:
        u ← vertex in Q with min dist[u]
        remove u from Q
        
        for each neighbor v of u still in Q:
            alt ← dist[u] + Graph.Edges(u, v)
            if alt < dist[v]:
                dist[v] ← alt
                prev[v] ← u

    return dist[], prev[]
```





**IMPORTANT:**
Sparser graphs: **==O(elog(v))==** - e = edge, v = vertex
- USE A MINHEAP FOR EFFICIENT RETRIEVAL
	- in c++, it is:
`priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;`
- Because priority_queue supports a constructor that requires two extra arguments to make it min-heap
`priority_queue <Type, vector<Type>, ComparisonType > min_heap;`
https://www.geeksforgeeks.org/implement-min-heap-using-stl/

More dense graphs: **==O(v^2)==**
- Use adjacency matrix to store the graph
- Use a simple array to store distances
- NEED visited for this





**Code:**
```c++
void addEdge(vector<vector<pair<int, int>>>& graph, int u, int v, int w) {
    graph[u].push_back({v, w});
    graph[v].push_back({u, w});
}

int main() {
	vector<vector<pair<int, int>>> graph(n+1); //adjacency list
    vector<int> dist(n+1, INT_MAX);
    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> smallest_node;
    //not necessary, just for keeping track
    vector<bool> visited(n+1, false);


	while (!smallest_node.empty()) {
        int curr_node = smallest_node.top().second; 
        int curr_dist = smallest_node.top().first; 

        //remove from priority queue -> extracted the node with the smallest known distance among all nodes in the queue (shortest possible distance)
            //because for any other nodes, even if they reach it, they will be > already
        smallest_node.pop();

        if (visited[curr_node]) {
            continue; //skip if already visited
        }

        visited[curr_node] = true; 

        for (const auto& edge : graph[curr_node]) {
            //getting the next node and weight
            int adj_node = edge.first; 
            int adj_weight = edge.second; 

            if (curr_dist + adj_weight < dist[adj_node]) {
                dist[adj_node] = curr_dist + adj_weight;
                smallest_node.push({dist[adj_node], adj_node});
            }
        }
    }
}

```

- INSTEAD OF VISITED:
	- `if (d > dist[u]) continue;`

# References
https://www.freecodecamp.org/news/dijkstras-shortest-path-algorithm-visual-introduction/
https://www.freecodecamp.org/news/dijkstras-algorithm-explained-with-a-pseudocode-example/
