# LCA

- If current node is null or one of the children nodes whose lca we are finding, return the root

- Recursively call lca for left and right subtrees

- If ! left, return right

- else if ! right, return left

- else return root
