### 题目要求

![](pic/offer4.png)

### 解题思路

### 本题代码

```c++
class Solution {
public:
    bool Find(int target, vector<vector<int> > array) {
        if(array.size() == 0)
            return false;
        int rows = 0;
        int cols = array[0].size() - 1;
        while(rows < array.size() && cols >= 0){
            if(target == array[rows][cols]){
                return true;
            }
            else if(target > array[rows][cols]){
                rows++;
            }
            else if(target < array[rows][cols]){
                cols--;
            }
        }
        return false;
    }
};
```

### [手撸测试](https://www.nowcoder.com/practice/abc3fe2ce8e146608e868a70efebf62e?tpId=13&tqId=11154&tPage=1&rp=1&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking)  

