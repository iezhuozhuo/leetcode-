### 题目要求

![](./pic/offer8.png)

### 解题思路

中序遍历的下一个节点首先考虑中序遍历--左根右。如果一个节点有右树，那么右树最左边的节点就是中序遍历的下一个节点。如果该节点没有右树也分两种情况：该节点是其父节点的左孩子，那么中序遍历的下一个就是该节点的父节点；该节点是其父节点的右孩子，那么就沿着父节点往上遍历直到找到满足节点是父节点的左孩子的节点。

### 本题代码

```c++
class Solution {
public:
    TreeLinkNode* GetNext(TreeLinkNode* pNode)
    {
        if(!pNode)
            return NULL;
        if(pNode->right){
            pNode = pNode->right;
            while(pNode->left)
                pNode = pNode->left;
            return pNode;
        }
        while(pNode->next){
            TreeLinkNode* root = pNode->next;
            if(root->left == pNode)
                return root;
            pNode = pNode->next;
        }
        return NULL;
    }
};
```

### [手撸测试](<https://www.nowcoder.com/practice/9023a0c988684a53960365b889ceaf5e?tpId=13&tqId=11210&tPage=3&rp=1&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking>) 
