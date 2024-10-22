# Preorder, Inorder and Postorder in a single traversal

Crux: Push a pair in the stack ({node, num}). This number denotes the kind of traversal we have to perform. 

0 -> preorder

1 -> inorder

2 -> postorder

Go through the code to learn more

**Code**

```c++
#include <bits/stdc++.h>

vector<vector<int>> getTreeTraversal(TreeNode *root) {

  vector<vector<int>> ans;

  if (!root) return ans;
  stack<pair<TreeNode *, int>> st;
  st.push({root, 1});
  vector <int> pre, inO, post;

  while (st.size()) {
    auto item = st.top();
    st.pop();
    TreeNode *node = item.first;
    int num = item.second;
    if (num == 1) {
      pre.push_back(node->data);
      st.push({node, num + 1});
      if (node->left)
        st.push({node->left, 1});
    }
    else if (num == 2) {
      inO.push_back(node->data);
      st.push({node, num + 1});
      if (node->right)
        st.push({node->right, 1});
    } else {
      post.push_back(node->data);
    }
  }
  ans.push_back(inO);
  ans.push_back(pre);
  ans.push_back(post);
  return ans;
}
```
