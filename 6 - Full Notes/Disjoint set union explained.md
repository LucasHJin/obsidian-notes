2024-08-27 15:23

Status:


Tags:
[[cs]]
[[cp]]
[[graph theory]] 


___________________________________________________________________________
# Non-minimum spanning tree explained

==**ALSO CALLED Union Find or Non-minimum spanning tree**== 

[[Spanning tree explained]]

**Disjoint sets:** 
- Sets where there are no elements in common (intersection is a null set)
- ==Same tree = Same Disjoint union== 
	- Root node/top node of a tree: ==**representative/leader of the set**== 
		- Only 1 per set
		- `Parent[i] = i` 

**What?** 
- Provides a data structure that allows for fast union and find operations

**TO NOTE:** 
- **Parent Array**: 
	- Each element in the set has a "parent" pointer, which either points to itself (if it is the leader of its subset) or points to another element in the set. This forms a tree structure, where the root is the leader of the subset.
- **Rank/Size**: 
	- This is used to keep the tree flat by attaching the smaller tree under the root of the larger tree during the union operation. It helps optimize the performance of the structure.

**Operations:**
- Adding new sets to the disjoint set.
- Check if two sets are disjoint or not.
- ==Merging disjoint sets to a single disjoint set using **Union** operation.== 
	- Merges 2 subsets into 1 set
```c++
void union(int x, int y) {
    int rootX = find(x);
    int rootY = find(y);
    if (rootX != rootY) {
        if (rank[rootX] > rank[rootY]) {
            parent[rootY] = rootX;
        } else if (rank[rootX] < rank[rootY]) {
            parent[rootX] = rootY;
        } else {
            parent[rootY] = rootX;
            rank[rootX]++;
        }
    }
}
``` 
- ==Finding representative of a disjoint set (that contains a specific element) using **Find** operation.== 
	- Checks if 2 elements are in the same subset
```c++
int find(int x) {
    if (parent[x] != x) {
        parent[x] = find(parent[x]); // Path compression
    }
    return parent[x];
}
```

**Usecases:** 
- Finding connected components in a graph



# References
https://www.geeksforgeeks.org/introduction-to-disjoint-set-data-structure-or-union-find-algorithm/
https://cp-algorithms.com/data_structures/disjoint_set_union.html