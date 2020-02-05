### 题目要求

![](pic/offer9.png)

### 解题思路

一个倒，一个装。

### 本题代码

```c++
class Solution
{
public:
    void push(int node) {
        while(!stack1.empty()){
            stack2.push(stack1.top());
            stack1.pop();
        }
        stack1.push(node);
        while(!stack2.empty()){
            stack1.push(stack2.top());
            stack2.pop();
        }
    }

    int pop() {
        if(stack1.empty()){
            return 0;
        }
        int x = stack1.top();
        stack1.pop();
        return x;
    }

private:
    stack<int> stack1;
    stack<int> stack2;
};
```

### [手撸测试]([https://www.nowcoder.com/practice/54275ddae22f475981afa2244dd448c6?tpId=13&tqId=11158&tPage=1&rp=1&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking%3E](https://www.nowcoder.com/practice/54275ddae22f475981afa2244dd448c6?tpId=13&tqId=11158&tPage=1&rp=1&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking>))  

