### 题目要求

![](./pic/offer36.png)

### 解题思路

和[二叉树变换成链表](114.md)思路相似，直接使用递归。递归返回的是头节点，那么需要记录其末节点(遍历即可)，然后与根节点相连。

### 本题代码

```c++
class Solution {
public:
    TreeNode* Convert(TreeNode* pRootOfTree)
    {
        if(pRootOfTree == NULL)
            return pRootOfTree;
        if(pRootOfTree->left == NULL && pRootOfTree->right == NULL)
            return pRootOfTree;
        TreeNode* left = Convert(pRootOfTree->left);
        TreeNode* cur = left;
        while(cur != NULL && cur->right != NULL){
            cur = cur->right;
        }
        if(left != NULL){
            cur->right = pRootOfTree;
            pRootOfTree->left = cur;
        }
        TreeNode* right = Convert(pRootOfTree->right);
        if(right != NULL){
            pRootOfTree->right = right;
            right->left = pRootOfTree;
        }
        return left ? left : pRootOfTree;
    }
};
```

### [手撸测试](<https://www.nowcoder.com/practice/947f6eb80d944a84850b0538bf0ec3a5?tpId=13&tqId=11179&tPage=2&rp=1&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking>) 

