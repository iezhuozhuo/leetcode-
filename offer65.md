### 题目要求

![](pic/offer52.png)

### 解题思路

异或得到没有进位的数，相与并往左移一位得到进位。

### 本题代码

```c++
class Solution {
public:
    int add(int a, int b) {
        while(b != 0){
            int c = (unsigned int)(a & b) << 1; //注意考虑负数情况
            a ^= b;
            b = c;
        }
        return a;
    }
};
```

### [手撸测试](https://leetcode-cn.com/problems/bu-yong-jia-jian-cheng-chu-zuo-jia-fa-lcof/)  

