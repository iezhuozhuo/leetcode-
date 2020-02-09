### 题目要求

![](pic/offer16.png)

### 解题思路

注意底数`base`在`exponent`小于等于0时的情况以及`float`型的`base`如何与0判断。乘方的计算有一种时间复杂度$$O(logn)$$的方法，根据二进制中1的个数。

### 本题代码

```c++
class Solution {
public:
    double Power(double base, int exponent) {
        if(is_zero(base, 0.0) && exponent < 0)
            return 0.0;
        bool flag = false;
        if(exponent < 0){
            flag = true;
            exponent = ~exponent + 1;
        }
        double temp = base;
        double res = 1.0;
        while(exponent != 0){
            if(exponent & 1){
                res *= temp;
            }
            temp *= temp;
            exponent = exponent >> 1;
        }
        return flag ? 1.0 / res : res;
    }
    bool is_zero(double d1, double d2){
        if(d1 - d2 < 0.0000001 && d1 - d2 > -0.0000001){
            return true;
        }
        return false;
    }
};
```

### [手撸测试](https://www.nowcoder.com/practice/1a834e5e3e1a4b7ba251417554e07c00?tpId=13&tqId=11165&tPage=1&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)  

