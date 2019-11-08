### 题目要求

![](./pic/offer26.png)

### 解题思路

先序遍历解决。要是根不为空就开始，要是两个根相等，那就继续判断左右树。要是根不相等，那么遍历A的左树看看是否有B树，没有找到就遍历右树看看是否有B树。

### 本题代码

```c++
class Solution {
public:
    bool HasSubtree(TreeNode* pRoot1, TreeNode* pRoot2)
    {
        bool result = false;
        if(pRoot1 != NULL && pRoot2 != NULL){
            if(pRoot1->val == pRoot2->val)
                result =  doseHasTree(pRoot1, pRoot2);
            if(result == false)
                result = HasSubtree(pRoot1->left, pRoot2);
            if(result == false)
                result = HasSubtree(pRoot1->right, pRoot2);
        }
        return result;
    }
    bool doseHasTree(TreeNode* pRoot1, TreeNode* pRoot2){
        if(pRoot2 == NULL)
            return true;
        if(pRoot1 == NULL)
            return false;
        if(pRoot1->val != pRoot2->val)
            return false;
        return doseHasTree(pRoot1->left, pRoot2->left) && doseHasTree(pRoot1->right, pRoot2->right);
    }
};
```

### [手撸测试](<https://www.nowcoder.com/practice/6e196c44c7004d15b1610b9afca8bd88?tpId=13&tqId=11170&tPage=1&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking>) 

