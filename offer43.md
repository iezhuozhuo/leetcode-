### 题目要求

![](pic/offer43.png)

### 解题思路

三种解法，第一种是爆搜，即从`1~n`统计每一个数字中`1`出现的个数相加；第二种需要巧妙的观察：![](pic/offer43-1.png)

举例子如：![](pic/offer43-2.png)

但是如果某位出现了位数值小于`1`，那么则：

![](pic/offer43-3.png)

第三种解法是第二种解法的优化，一共考虑输入`n`位数次。将一个数分成三段：`heigh`、`low`、`mid`，如43521，如果`mid`是5，那么`heigh`是43，`low`是21。当`mid`>1那么有1的个数就是`heigh+1`*pow(10,位数-1)次，如果`mid`==1,那么`heigh`\*pow(10, 位数-1)+low+1;如果`mid`\==0，那么`heigh`\*pow(10,位数-1)。起始的bit为1，位数(count)为0.

### 本题代码

#### 解法二

```c++
class Solution {
public:
    int countDigitOne(int n) {
        vector<long>help = vector<long>(11);
        help[1] = 1;
        for(int i = 2;i < help.size();i++){
            help[i] = pow(10, i-1) + 10 * help[i-1];
        }
        stack<int> s = stack<int>();
        while(n){
            s.push(n % 10);
            n /= 10;
        }
        long res = 0;
        while(!s.empty()){
            int size = s.size();
            int top = s.top();
            if(size == 1){
                if(top != 0){
                    res += help[1];
                }
            }
            else{
                if(top > 1)
                    res += pow(10, s.size()-1);
                else if(top == 1)
                    res += get_res(s);
                res += top * help[size - 1];
            }
            s.pop();
        }
        return res;
    }
    int get_res(stack<int> s){
        s.pop();
        int res = 0;
        while(!s.empty()){
            res = res * 10 + s.top();
            s.pop();
        }
        return res+1;
    }
};
```

#### 解法三：

```c++
class Solution {
public:
    int countDigitOne(int n) {
        int count = 0, res = 0;
        int bit = 1;
        long low = 1, mid = 1, heigh = 1;
        int num;
        while(heigh != 0){
            low = n % bit;
            mid = (n / bit) % 10;
            
            // 防止溢出
            if(bit >= 1000000000)
                heigh = 0;
            else{
                heigh = n / (bit * 10);
                bit *= 10;
            }
            
            if(mid > 1)
                num = (heigh + 1) * pow(10, count);
            else if(mid == 0)
                num = (heigh - 1 + 1) * pow(10, count);
            else
                num = heigh * pow(10, count) + low + 1;
            res += num;
            count += 1; 
        }
        return res;
    }
};
```



### [手撸测试](https://leetcode-cn.com/problems/1nzheng-shu-zhong-1chu-xian-de-ci-shu-lcof/)  

