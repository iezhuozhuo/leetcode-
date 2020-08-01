### 题目要求

![](./pic/offer17.png)

### 解题思路

全排列：查看[46.全排列](46.md) 、[47.全排列II](47.md) 。从第一个位置放置开始，每次放下一个。保存number时需要排除掉前导0.

### 本题代码

```c++
class Solution {
public:
    vector<int>res;
    vector<int> printNumbers(int n) {
        if(n <= 0)
            return res;
        string nums(n, '0');
        for(int i = 0;i <= 9;i++){
            nums[0] = i + '0'; // 首字符赋值
            permu(nums, n, 1); // 下一位赋值
        }
        return res;
    }
    void permu(string& nums, int length, int index){
        if(index == length){
            save(nums);
            return;
        }
        else{
            for(int i = 0;i <= 9;i++){
                nums[index] = i + '0';
                permu(nums, length, index+1);
            }
        }
    }
    void save(string nums){
        string temp = "";
        bool begin0 = true;
        string::iterator it = nums.begin();
        while(it != nums.end()){
            if(begin0 && *it != '0')
                begin0 = false;
            if(!begin0)
                temp += *it;
            it++;
        }
        if(temp != "")
            res.push_back(stoi(temp));
    }
};
```

### [手撸测试](https://leetcode-cn.com/problems/da-yin-cong-1dao-zui-da-de-nwei-shu-lcof/)  

