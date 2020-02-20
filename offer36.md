### 题目要求

![](./pic/offer36.png)

### 解题思路

#### 变换成双向链表

和[二叉树变换成链表](114.md)思路相似，直接使用递归。递归返回的是头节点，那么需要记录其末节点(遍历即可)，然后与根节点相连。

#### 变成环形双向链表

额外定义三个全局指针变量，中序遍历，`pre`记录左树最后的节点，`tail`记录双向链表最后的节点，`head`记录双向链表的头节点。

### 本题代码

#### 变换成双向链表

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

#### 变换环形双向链表

```c++
class Solution {
public:
    Node* treeToDoublyList(Node* root) {
        if(root == NULL)
            return root;
        inorder(root);
        head->left = tail;
        tail->right = head;
        return head;
    }
    void inorder(Node* root){
        if(!root)
            return;
        inorder(root->left);
        if(pre)
            pre->right = root;
        else
            pre = head;
        root->left = pre;
        pre = root;
        tail = root;
        inorder(root->right);
    }
    private:
    Node* pre = NULL, head = NULL, tail = NULL;
};
```

### [手撸测试](<https://www.nowcoder.com/practice/947f6eb80d944a84850b0538bf0ec3a5?tpId=13&tqId=11179&tPage=2&rp=1&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking>)    [力扣手撸](https://leetcode-cn.com/problems/er-cha-sou-suo-shu-yu-shuang-xiang-lian-biao-lcof/)



