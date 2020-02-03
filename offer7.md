### 题目要求

![](pic/offer7.png)

### 解题思路

前序遍历和中序构建二叉树，前序和后序构建二叉树(必须左右孩子都有才能构建出二叉树)，中序和后序构建二叉树。

重点参考：[重建二叉树](https://blog.csdn.net/qq_34342154/article/details/77104202)

另外，注意非递归的解法可以后续[参考](https://leetcode-cn.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/solution/c-fei-di-gui-by-zhangxianbing-2/) 

### 本题代码

```c++
class Solution {
public:
    TreeNode* reConstructBinaryTree(vector<int> pre,vector<int> vin) {
        if(pre.size() == 0 || vin.size() == 0 || pre.size() != vin.size())
            return NULL;
        map<int,int>m;
        for(int i = 0;i < vin.size();i++)
            m[vin[i]] = i;
        TreeNode* root = reconstruct(pre, 0, pre.size() - 1, vin, 0, vin.size() - 1, m);
        return root;
    }
    TreeNode* reconstruct(vector<int> pre, int pi, int pj, vector<int> vin, int ni, int nj, map<int, int>m){
        if(pi > pj)
            return NULL;
        int index = m[pre[pi]];
        TreeNode* root = new TreeNode(pre[pi]);
        root->left = reconstruct(pre, pi+1, pi + index - ni, vin, ni, index - 1, m);
        root->right = reconstruct(pre, pi + index - ni + 1, pj, vin, index + 1, nj, m);
        return root;
    }
};
```

### [手撸测试](https://www.nowcoder.com/practice/8a19cbe657394eeaac2f6ea9b0f6fcf6?tpId=13&tqId=11157&tPage=1&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)  

