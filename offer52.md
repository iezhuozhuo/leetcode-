### 题目要求

![](pic/offer52.png)

### 解题思路

直接法

### 本题代码

```c++
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        stack<ListNode*>s1;
        stack<ListNode*>s2;
        while(headA){
            s1.push(headA);
            headA = headA->next;
        }
        while(headB){
            s2.push(headB);
            headB = headB->next;
        }
        ListNode* res = NULL;
        while(!s1.empty() && !s2.empty()){
            if(s1.top() != s2.top()){
                return res;
            }
            res = s1.top();//注意先判断再保存
            s1.pop();
            s2.pop();
        }
        return res;
    }
};
```

### [手撸测试](https://www.nowcoder.com/practice/6ab1d9a29e88450685099d45c9e31e46?tpId=13&tqId=11189&tPage=2&rp=1&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking) 

