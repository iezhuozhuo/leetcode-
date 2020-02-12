### 题目要求

![](pic/offer20.png)

### 解题思路

判断字符串是不是可以用十进制表示，使用直接法遍历看是否能够到达字符串的尾部。特殊的字符有`" "`(空格)、`"+"`、`"-"`、`"e"`、`"E"`、`"."`。字符串左右的空格首先去掉，中间出现空格即为非法；`"e"`、`"E"`重复出现以及后面不跟数字为非法；多符号的情况下，前一个不为`"e"`、`"E"`非法，单符号下前一个字符为`"e"`或`"E"`非法；字符不满足`"0"~"9"`非法。

### 本题代码

```c++
class Solution {
public:
    bool isNumeric(char* string)
    {
        bool sign = false, dot = false, hase = false;
        for(int i = 0;i < strlen(string);i++){
            if(string[i] == 'e' || string[i] == 'E'){
                if(i == strlen(string) - 1)
                    return false;
                if(hase)
                    return false;
                hase = true;
            }
            else if(string[i] == '+' || string[i] == '-'){
                if(sign && string[i - 1] != 'e' && string[i - 1] != 'E')
                    return false;
                if(!sign && i > 0 && string[i - 1] != 'e' && string[i - 1] != 'E')
                    return false;
                sign = true;
            }
            else if(string[i] == '.'){
                if(i == 0 || hase || dot)
                    return false;
                dot = true;
            }
            else if(string[i] < '0' || string[i] > '9')
                return false;
        }
        return true;
    }

};
```

### [手撸测试](https://www.nowcoder.com/practice/6f8c901d091949a5837e24bb82a731f2?tpId=13&tqId=11206&tPage=3&rp=1&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking)  

