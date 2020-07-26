### 题目要求

![](/pic/offer44.png)

### 解题思路

对于`n`先确定所在多少位，然后确定所在的数字`target`，并将`target`转化为字符串，最后求出`n`在字符串的第几位并将该位输出即可。

### 本题代码

```c++
class Solution {
public:
    int findNthDigit(int n) {
        int bit = 1;
        while(n > 0.9 * pow(10, bit) * bit){
            n -= 0.9 * pow(10, bit) * bit;
            bit++;
        }
        string res = to_string((pow(10, bit-1) + (n-1)/bit));// n-1表示的是所在数字范围可以从0开始计数，如100为基准数， 100+n-1可以从100计数
        return res[(n-1)%bit] - '0';
    }
};
```

### [手撸测试](https://leetcode-cn.com/problems/shu-zi-xu-lie-zhong-mou-yi-wei-de-shu-zi-lcof/) 

