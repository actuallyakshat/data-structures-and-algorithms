# Boundary Traversal

Approach:

1. Find all left nodes (except leaf)

2. Find all leaf nodes

3. Find all right nodes (except leafs) and reverse them (because that's how we are expected to traverse).

4. Return ans

```c++
class Solution {
    private:
    bool isLeaf(Node* node){
        if(!node) return false;
        if(node && !node -> left && !node->right){
            return true;
        }
        return false;
    }
    
    void getLeftNodes(Node* node, vector<int>& arr){
        while(temp){
            if(!isLeaf(temp)) arr.push_back(temp->data);
            if(temp -> left) temp = temp -> left;
            else temp = temp -> right;
        }
    }
    void getRightNodes(Node* node, vector<int>& arr){
        vector<int> tempArr;
        Node* temp = node -> right;
        while(temp){
            if(!isLeaf(temp)) tempArr.push_back(temp->data);
            if(temp -> right) temp = temp -> right;
            else temp = temp -> left;
        }
        reverse(tempArr.begin(), tempArr.end());
        for(auto it: tempArr){
            arr.push_back(it);
        }
    }
    
    void getLeafNodes(Node* node, vector<int>& arr){
        if(!node) return;
        if(isLeaf(node)) arr.push_back(node->data);
        getLeafNodes(node -> left, arr);
        getLeafNodes(node -> right, arr);
    }
    
public:
    vector <int> boundary(Node *root)
    {
        vector<int> ans;
        if(!isLeaf(root)) ans.push_back(root->data);
        getLeftNodes(root -> left, ans);
        getLeafNodes(root, ans);
        getRightNodes(root -> rigjt, ans);
        return ans;
    }
};
```
