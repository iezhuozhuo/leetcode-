### 题目要求

![](pic/interview17-13.png)

### 解题思路

动态规划解法。`dp[i]`表示的是$$[0.i]$$的最小未识别个数，遍历`dictionary`中每一个单词看是否可以识别，如果可以识别则$$dp[i-len]$$,否则为$$dp[i-1]+1$$。

### 本题代码

```c++
class Solution {
public:
    int respace(vector<string>& dictionary, string sentence) {
        if(sentence.size() == 0)
            return 0;
        vector<int>dp(sentence.size()+1, 0);
        for(int i = 1;i <= sentence.size();i++){
            dp[i] = dp[i-1] + 1;
            for(int j = 0;j < dictionary.size();j++){
                int len = dictionary[j].size();
                if(i >= len){
                    if(sentence.substr(i-len, len) == dictionary[j])
                        dp[i] = min(dp[i], dp[i-len]);
                }
            }
        }
        return dp[sentence.size()];
    }
};
```

### [手撸测试](https://leetcode-cn.com/problems/re-space-lcci/)   

