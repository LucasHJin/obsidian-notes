2024-09-17 09:46

Status:


Tags:
[[cs]]
[[cp]]
[[graph theory]] 


___________________________________________________________________________
# In order tree traversal

**DFS VARIANT** 

**Logic:** primarily for binary tree
- Visit the nodes in a specific order
	- Left subtree -> root node -> right subtree
		- Retrieves the nodes in ==ascending order== 
	- Do this recursively (i.e. doing left left left ) then node node node... then right right right...

**Usecases:** 
- In the case of binary search trees (BST), Inorder traversal gives nodes in non-decreasing order
- To get nodes of BST in non-increasing order, a variation of Inorder traversal where Inorder traversal is reversed can be used
- Inorder traversal can be used to evaluate arithmetic expressions stored in expression trees

**Code:**
Each node's class
```c++
class TreeNode {
public:
    int value; //data in the node
    TreeNode* left; //pointer to another treenode object (left child)
    TreeNode* right; //if no child -> nullptr

    TreeNode(int val) : value(val), left(nullptr), right(nullptr) {} //constructor with no children initially
};
```

Recursive algorithm
```c++
void inOrderRecursive(TreeNode* node) {
    if (node != nullptr) { //null = no child = base case
        inOrderRecursive(node->left);  // Visit left subtree
        std::cout << node->value << " ";  // Visit root
        inOrderRecursive(node->right);  // Visit right subtree
        // arrow is used to access members of an object through a pointer
	        //equivalent to dereferencing, (*pointer).member
    }
}
```



# References
https://www.geeksforgeeks.org/tree-traversals-inorder-preorder-and-postorder/ 
