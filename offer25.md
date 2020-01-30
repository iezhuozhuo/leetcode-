### 题目要求

![](pic/offer25.png)

### 解题思路

直接法

### 本题代码

```c++
class Solution {
public:
    ListNode* Merge(ListNode* pHead1, ListNode* pHead2)
    {
        if(pHead1 == NULL || pHead2 == NULL)
            return pHead1 ? pHead1 : pHead2;
        ListNode* Head = new ListNode(0);
        ListNode* cur = Head;
        while(pHead1 && pHead2){
            if(pHead1->val < pHead2->val){
                cur->next = pHead1;
                pHead1 = pHead1->next;
            }
            else{
                cur->next = pHead2;
                pHead2 = pHead2->next;
            }
            cur = cur->next;
        }
        cur->next = pHead1?pHead1:pHead2;
        return Head->next;
    }
};
```

### [手撸测试](https://www.nowcoder.com/practice/d8b6b4358f774294a89de2a6ac4d9337?tpId=13&tqId=11169&tPage=1&rp=1&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking)  

