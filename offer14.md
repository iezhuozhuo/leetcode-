### 题目要求

![](pic/offer14.png)

### 解题思路

两种解法：(1)动态规划；(2)数学[贪心算法]。动态规划很好解，构建动态规划表`dp[n + 1]`，其中`n`是输入的数字。`dp[i]`的意义是`i`长度的最大乘积(甚至切一次，因为当`n`大于3后`dp[i]`不可能取到`i`)，需要定义前四个动态规划初始值，因此动态规划转移矩阵是$$dp[i] = max(dp[j] * dp[i - j])$$，在已知`dp[j]`的情况下，遍历寻找最大组合积$$dp[j] * dp[i - j]$$。数学方法的贪心是找规律的，当n>4之后，尽可能分出来尽可能多的3，就会得到最大值。

数学贪心尽可能的分出来3.

### 本题代码

#### 贪心

```c++
class Solution {
public:
    int cuttingRope(int n) {
        if(n <= 1)
            return 0;
        if(n == 2)
            return 1;
        if(n == 3)
            return 2;
        if(n == 4)
            return 4;
        long res = 1;
        while(n > 4){
            res = (res % 1000000007) * 3;
            n -= 3;
        }
        res *= n;
        return res % 1000000007;
    }
};
```

#### 动态规划

```c++
class Solution {
public:
    int cutRope(int number) {
        if(number < 2)
            return 0;
        if(number == 2)
            return 1;
        if(number == 3)
            return 2;
        int dp[60 + 1] = {0};
        dp[0] = 0;
        dp[1] = 1;
        dp[2] = 2;
        dp[3] = 3;
        int res = 0;
        for(int i = 4;i <= number;i++){
            for(int j = 1;j <= i / 2;j++){
                dp[i] = max(dp[i], dp[j] * dp[i - j]);
            }
            res = max(res, dp[i]);
        }
        return res;
    }
};
```

### [手撸测试](https://www.nowcoder.com/practice/57d85990ba5b440ab888fc72b0751bf8?tpId=13&tqId=33257&tPage=4&rp=4&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking)  

