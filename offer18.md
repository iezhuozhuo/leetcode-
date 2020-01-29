### 题目要求

![](pic/offer18.png)

### 解题思路

参考[保留重复值](./83.md)和[不保留重复值](82.md) 

### 本题代码

```c++
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        if(head == NULL || head->next == NULL)
            return head;
        ListNode* Head = new ListNode(0);
        Head->next = head;
        ListNode* pre = Head;
        ListNode* cur = Head->next;
        while(cur){
            if(cur->next && cur->val == cur->next->val){
                while(cur->next && cur->val == cur->next->val)
                    cur = cur->next;
                pre->next = cur->next;
                cur = cur->next;
            }
            else{
                pre = pre->next;
                cur = cur->next;
            }
        }
        return Head->next;
    }
};
```

### [手撸测试](https://www.nowcoder.com/practice/fc533c45b73a41b0b44ccba763f866ef?tpId=13&tqId=11209&tPage=1&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)  

