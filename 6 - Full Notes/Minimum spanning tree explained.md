2024-08-27 15:24

Status:


Tags:
[[cs]]
[[cp]]
[[graph theory]] 


___________________________________________________________________________
# Minimum spanning tree explained

[[Spanning tree explained]] 

**Minimum spanning tree:** A spanning tree with an added constraint of having the minimum possible weights among all possible spanning trees
- Can have multiple MST per graph
- I.e. ![[Pasted image 20240903104524.png|300]] 

**Kruskal's algorithm:** 
- For finding the MST from a connected undirected graph (greedy alg)
1. Sort all the edges by weight 
	1. Keep track of start, end, weight
2. Start iterations for the MST
	1. Pick the smallest edge and check for cycle
	2. If no cycle -> keep edge, else -> discard
	3. Repeat until $V-1$ edges
- **NOTE:** 
	- Use [[Disjoint set union explained]] because they can help with finding cycles (**find**) and adding edges if no cycle (**merge**) 

**Example code:** 
Disjoint Union Set
```c++
// Structure to represent an edge with a source, destination, and weight
struct Edge {
    int src, dest, weight;
};

// Comparator function to sort edges by their weight in non-decreasing order
bool compare(Edge a, Edge b) {
    return a.weight < b.weight;
}

// A class to represent a disjoint set (Union-Find)
class DisjointSet {
    vector<int> parent, rank;

public:
    DisjointSet(int n) {
        parent.resize(n);
        rank.resize(n, 0);
        for (int i = 0; i < n; i++) {
            parent[i] = i;
        }
    }

    // Find the root of the set containing element u (with path compression)
    int find(int u) {
        if (u != parent[u]) {
            parent[u] = find(parent[u]);
        }
        return parent[u];
    }

    // Union of two sets represented by u and v
    void unionSets(int u, int v) {
        int rootU = find(u);
        int rootV = find(v);

        if (rootU != rootV) {
            // Union by rank
            if (rank[rootU] < rank[rootV]) {
                parent[rootU] = rootV;
            } else if (rank[rootU] > rank[rootV]) {
                parent[rootV] = rootU;
            } else {
                parent[rootV] = rootU;
                rank[rootU]++;
            }
        }
    }
};

```

**Kruskal:** 
```c++

int kruskalMST(vector<Edge>& edges, int V) {
    // Sort edges by weight
    sort(edges.begin(), edges.end(), compare);

    DisjointSet ds(V);
    int mstWeight = 0;

    // Iterate over sorted edges
    for (const auto& edge : edges) {
        int u = edge.src;
        int v = edge.dest;

        // If including this edge doesn't form a cycle
        if (ds.find(u) != ds.find(v)) {
            // Include the edge in MST and unite the sets
            ds.unionSets(u, v);
            mstWeight += edge.weight;
            cout << "Edge: " << u << " - " << v << " Weight: " << edge.weight << endl;
        }
    }

    return mstWeight;
}
```


# References
- https://www.geeksforgeeks.org/what-is-minimum-spanning-tree-mst/ 
- https://www.geeksforgeeks.org/kruskals-minimum-spanning-tree-algorithm-greedy-algo-2/
- 
