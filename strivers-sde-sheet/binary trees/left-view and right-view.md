# Left View

**Brute Force**: Get the level order traversal and print the first node of each level

**Algorithm for Left View**

**Step 1:** Initialise an empty vector `res` to store the left view nodes.

**Step 2:** Implement a recursive depth-first traversal of the binary tree.

**Base Case:** Check if the current node is null, if true, return the function as we have reached the end of that particular vertical level.

**Recursive Function:** The recursive function takes in arguments the current node of the Binary Tree, its current level and the result vector.

1. We check if the size of the result vector is equal to the current level.
2. If true, it means that we have not yet encountered any node at this level in the result vector. Add the value of the current node to the result vector.
3. Recursively call the function for the current nodes left then right child with an increased level ie. level + 1.
4. We call the left child first as we want to traverse the left most nodes. In cases where there is no left child, the recursion function backtracks and explores the right child.

**Step 3:** The recursion continues until it reaches the base case. Return the result vector at the end.

![](https://static.takeuforward.org/content/right-left-tree-image9-xjy_h8re)

# Right View

**Algorithm for Right View**

**Step 1:** Initialise an empty vector `res` to store the left view nodes.

**Step 2:** Implement a recursive depth-first traversal of the binary tree.

**Base Case:** Check if the current node is null, if true, return the function as we have reached the end of that particular vertical level.

**Recursive Function:** The recursive function takes in arguments the current node of the Binary Tree, its current level and the result vector.

1. We check if the size of the result vector is equal to the current level.
2. If true, it means that we have not yet encountered any node at this level in the result vector. Add the value of the current node to the result vector.
3. Recursively call the function for the current nodes right then left child with an increased level ie. level + 1.
4. We call the right child first as we want to traverse the right most nodes. In cases where there is no right child, the recursion function backtracks and explores the left child.

**Step 3:** The recursion continues until it reaches the base case. Return the result vector at the end.

![](https://static.takeuforward.org/content/right-left-tree-image10-bDzTVkfD)
