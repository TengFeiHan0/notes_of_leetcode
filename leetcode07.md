```
class Solution {
public:
    TreeNode* buildTree(vector<int>& preorder, vector<int>& inorder) {
        for(int i=0; i<inorder.size();i++){
            record.insert(make_pair(inorder[i], i));
        }
        return helper(preorder, inorder, 0, preorder.size());
      
    }

private:
    int preIndex = 0;                // 根结点索引
    unordered_map<int,int> record;   //(元素，索引)

    TreeNode* helper(vector<int>& preorder, vector<int>& inorder, int left, int right){
        if(left == right)
            return NULL;

        int root_value = preorder[preIndex];
        int root_index = record.find(root_value)->second;
        preIndex++;    
       
        //先序遍历建树，因为先序遍历数组为根结点获取来源，且先序遍历顺序为先左后右
        TreeNode* root = new TreeNode(rootVal);  //建立当前结点
        root->left = helper(preorder, inorder, left, index);
        root->right = helper(preorder, inorder, index + 1, right);

        return root;
    }
};
```
