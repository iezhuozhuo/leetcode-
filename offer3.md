### 题目要求

![](pic/offer3.png)

### 解题思路

### 本题代码

```c++
class Solution {
public:
    // Parameters:
    //        numbers:     an array of integers
    //        length:      the length of array numbers
    //        duplication: (Output) the duplicated number in the array number
    // Return value:       true if the input is valid, and there are some duplications in the array number
    //                     otherwise false
    bool duplicate(int numbers[], int length, int* duplication) {
        for(int i = 0;i < length;i++){
            int index = numbers[i] % length;
            if(numbers[index] >= length){
                *duplication = index;
                return true;
            }
            numbers[index] += length;
        }
        return false;
    }
};
```

### [手撸测试](https://www.nowcoder.com/practice/623a5ac0ea5b4e5f95552655361ae0a8?tpId=13&tqId=11203&tPage=1&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-ranking)   

