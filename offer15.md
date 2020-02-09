### 题目要求

![](pic/offer15.png)

### 解题思路

把一个整数减去1之后在和原来的整数做位与运算，得到的结果相当于把该整数的二进制表示中最右边的1变成0。

### 本题代码

```c++
class Solution {
public:
     int  NumberOf1(int n) {
         int res = 0;
         while(n != 0){
             res++;
             n -= n & (~n+1); 
             // n = (n-1) & n;
         }
         return res;
     }
};
```

### [手撸测试](https://www.nowcoder.com/practice/8ee967e43c2c4ec193b040ea7fbb10b8?tpId=13&tqId=11164&tPage=1&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)  

