# Symmetric-Tree

/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    bool isSymmetric(TreeNode* root) {
        if(root == nullptr) {
            return true;
        }
        return mirror(root->left, root->right);
    }

    bool mirror(TreeNode* tree1, TreeNode* tree2) {
        if(tree1 == nullptr && tree2 == nullptr) {
            return true;
        }
        if (tree1 == nullptr || tree2 == nullptr) {
            return false;
        }
        return mirror(tree1->left, tree2->right) && mirror(tree1->right, tree2->left);
    }
};
