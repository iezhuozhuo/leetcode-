### 题目要求

![](./pic/offer32.png)

### 解题思路

利用两个栈，广度优先遍历交替压栈出栈。

### 本题代码

```c++
class Solution {
public:
    vector<vector<int> > Print(TreeNode* pRoot) {
        if(!pRoot)
            return vector<vector<int>>();
        stack<TreeNode*>s1;
        stack<TreeNode*>s2;
        vector<vector<int>>res;
        s1.push(pRoot);
        while(!s1.empty() || !s2.empty()){
            if(!s1.empty()){
                vector<int>data;
                while(!s1.empty()){
                    data.push_back(s1.top()->val);
                    if(s1.top()->left)
                        s2.push(s1.top()->left);
                    if(s1.top()->right)
                        s2.push(s1.top()->right);
                    s1.pop();
                }
                res.push_back(data);
            }
            else{
                vector<int>data;
                while(!s2.empty()){
                    data.push_back(s2.top()->val);
                    if(s2.top()->right)
                        s1.push(s2.top()->right);
                    if(s2.top()->left)
                        s1.push(s2.top()->left);
                    s2.pop();
                }
                res.push_back(data);
            }
        }
        return res;
    }
};
```

### [手撸测试](<https://www.nowcoder.com/practice/91b69814117f4e8097390d107d2efbe0?tpId=13&tqId=11212&tPage=3&rp=1&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking>) 

