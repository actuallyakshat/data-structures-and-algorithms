# Max Width of a Binary Tree

Note: This is different from diameter.

Crux: Push indexes of the left and right child, on each level compare the leftmost and rightmost element of the queue to get the width of the queue and then store max in the array.

**Code**

```c++
int widthOfBinaryTree(TreeNode* root) {
        long ans = 0;
        if(!root) return ans;

        queue<pair<TreeNode*, long>> q;
        q.push({root, 0});

        while(q.size()){
            ans = max(ans, q.back().second - q.front().second + 1);
            int size = q.size();
            for(int i = 0; i<size; i++){
                auto item = q.front();
                q.pop();
                TreeNode* node = item.first;
                int index = item.second;

                if(node -> left) q.push({node -> left, (long)2*index+1});
                if(node -> right) q.push({node -> right, (long)2*index+2});
            }
        }
        return ans;
    }
```
