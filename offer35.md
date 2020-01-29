### 题目要求

![](pic/offer35.png)

### 解题思路

直接参考[leetcode](https://nlper.gitbook.io/leetcode/138)

### 本题代码

```c++
class Solution {
public:
    Node* copyRandomList(Node* head) {
        if(head == NULL)
            return head;
        map<Node*, Node*>m;
        Node* cur = head;
        while(cur != NULL){
            m[cur] = new Node(cur->val);
            cur = cur->next;
        }
        cur = head;
        while(cur != NULL){
            m[cur]->next = m[cur->next];
            m[cur]->random = m[cur->random];
            cur = cur->next;
        }
        return m[head];

    }
};
```

### [手撸测试](https://www.nowcoder.com/practice/f836b2c43afc4b35ad6adc41ec941dba?tpId=13&tqId=11178&tPage=2&rp=1&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking)  

