### 题目要求

![](pic/offer22.png)

### 解题思路

直接法

### 本题代码

```c++
class Solution {
public:
    ListNode* FindKthToTail(ListNode* pListHead, unsigned int k) {
        if(!pListHead)
            return NULL;
        ListNode* cur = pListHead;
        int n = k;
        while(cur){
            cur = cur->next;
            n--;
        }
        if(n > 0){
            return NULL;
        }
        if(n == 0)
            return pListHead;
        cur = pListHead;
        while(n != 0){
            cur = cur->next;
            n++;
        }
        return cur;
    }
};
```

### [手撸测试](https://www.nowcoder.com/practice/529d3ae5a407492994ad2a246518148a?tpId=13&tqId=11167&tPage=1&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)  

