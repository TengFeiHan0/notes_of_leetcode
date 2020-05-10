[二叉树的最近公共祖先](https://leetcode-cn.com/problems/lowest-common-ancestor-of-a-binary-tree/submissions/)
 ```
class Solution {
public:
    TreeNode* lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q) {
        if(root==nullptr){
            return root;
        }//判断根节点是否非空
        if(root==p || root==q){
            return root;
        }//判断root是否与其中一个节点重复
        TreeNode* left = lowestCommonAncestor(root->left, p, q);
        TreeNode* right = lowestCommonAncestor(root->right, p, q);
        if(left!=nullptr && right!=nullptr){
            return root;
        }
        else if(left !=nullptr){
            return left;
        }else if(right!= nullptr){
            return right;
        }
        return nullptr;
        
    }
};
 ```
