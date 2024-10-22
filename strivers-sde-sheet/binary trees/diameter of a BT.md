# Diameter of a BT

Note: The **diameter** of a binary tree is the **length** of the longest path between any two nodes in a tree. This path may or may not pass through the `root`.

**Approach** : Max Width = max(maxWidth, Height(left) + Height(right));

```cpp
int depth(TreeNode* root, int &maxWidth){
        if(!root) return 0;
        int left = depth(root -> left, maxWidth);
        int right = depth(root -> right, maxWidth);
        maxWidth = max(maxWidth, left+right);
        return max(left, right) + 1;
    }

    int diameterOfBinaryTree(TreeNode* root) {
        if(!root) return 0;
        int maxWidth = 0;
        depth(root, maxWidth);
        return maxWidth;
    }
```


