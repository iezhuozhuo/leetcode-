---
description: 桃李春风一杯酒，江湖夜雨十年灯
---

# 莫问收获，但问耕耘

## 愿

我希望我的刷题过程可以如下所述：

老僧三十年前未参禅时，见山是山，见水是水。及至后来，亲见知识，有个入处，见山不是山，见水不是水。而今得个体歇处，依前见山只是山，见水只是水。

终有一天，我愿不负如来不负卿！

## 剑指offer

剑指offer系列很多题与前面的leetcode重复，因此题解很简陋可参考前面题解。

**1.数组中重复的数组及相关题**

> 可以考虑的解法有：排序\(桶排序\)、异或，二分法，模拟环法\(不常用\)。

[面试题3](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer3.md) 、[41 缺失的第一个整数](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/41.md) 、[268 缺失的数字](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/268.md) 、[287 寻找重复数](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/287.md)。

**2.二维数组的查找及相关题**

> 二维数组可以通过左上和右下两个点可以确定。

[面试题4](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer4.md) 、[240 搜索二维矩阵 II](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/240.md) 、[48 旋转图像](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/48.md) 、[54 螺旋矩阵](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/54.md)

**3.替换空格**

> 打破惯性思维，从后往前操作。

[面试题5](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer5.md)、[283 移动零](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/283.md)

**4.链表的遍历相关**

> 主要是链表的定义以及遍历的考察

[面试题6](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer6.md) 、[面试题24](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer24.md)

**5.重构二叉树**

> 二叉树三种遍历两两结合，重点参考[笔记](https://blog.csdn.net/qq_34342154/article/details/77104202)。注意：前序遍历和后序遍历需要左右孩子都存在。

[面试题7](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer7.md) 、[105 重建二叉树](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/105.md)

**6.二叉树下一个节点**

> 遍历使用中序遍历--左根右，对于给定的节点以是否有右孩子来区分情况。

[面试题8](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer8.md)

**7.用两个栈来实现队列**

> 一个倒，一个装。

[面试题9](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer9.md) 、[232 用栈实现队列](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/232.md)

**8.斐波那契数列**

> 斐波拉契数列的思路实际是简单动态规划。包括青蛙跳台阶、变态跳问题

[面试题10](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer10.md)

**9.旋转数组中找最小值**

> 旋转数组中找数不管是找最小值还是找某个`target`的方法都是一致的：首先需要考虑数组中是否有重复的值\(这些值需要跳过\)，然后确定断点的位置，非断点位置的序列是升序，可以直接判断是否有值。

[面试题11](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/11.md) 、[33 在有序数组中找数](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/33.md) 、[81 搜索旋转排序数组II](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/81.md) 、[153 寻转旋转排序数组中最小值I](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/153.md) 、[154 寻找旋转排序数组中最小值II](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/154.md)

**10.矩阵中的路径**

> 使用回溯法解决。需要有个状态变量来反映是否访问过，上下左右检查。最终返回是否可以。

[面试题12](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer12.md) 、[79 单词搜索](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/79.md)

**11.机器人运动轨迹**

> 回溯法，满足条件后可以进一步遍历。

[面试题13](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer13.md) 、[200 岛屿的数目](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/200.md)

**12.剪绳子**

> 动态规划以及贪心算法

[面试题14](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer/README.md) 、[343 整数拆分](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/343.md)

**13.二进制的1的个数**

> 把一个整数减去1之后在和原来的整数做位与运算，得到的结果相当于把该整数的二进制表示中最右边的1变成0。
>
> 整数取反加1是他的相反数
>
> 其中该思想运用于不用加减乘除法来完成加减乘除运算。

[面试题15](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer15.md) 、[461 汉明距离](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/461.md)

**14.数值的整数次方**

> `float`不能用于判断。乘方的运算可以通过二进制中1的位置来计算。

[面试题16](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer16.md)

**15.打印从1到最大的n位数**

> 全排列思想。

[面试题17](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer17.md) 、[46 全排列](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/45.md) 、[47 全排列II](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/47.md)

**16.删除链表中的节点**

> 怪异链表节点的删除：一种是待删节点下一个节点非`NULL`，另一种是待删节点下一个节点为`NULL`；当下一个节点不为`NULL`时，就可以用下一个节点来代替该节点。对于第二种情况，需要使用头节点遍历到待删节点前一个节点，然后删除该节点。
>
> 重复节点的删除：根据题意保留重复项以及删除重复项。

[面试18](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer18.md) 、[237 删除链表中的节点](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/237.md) 、[82 删除链表重复数字 II](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/82.md)、[83 删除链表重复数字 I](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/83.md)

**17.正则表达式**

> 关键在于通配符的第二个是否是`"*"`，如果不是就看第一个字符的匹配情况\(两种要么相等要么通配符第二个是`"."`\)否则就返回`false`。如果通配符第二个字符是`"*"`，那么也是要么相等要么通配符第二个是`"."`，分匹配0次或者多次。

[面试题19](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer19.md) 、[10 正则表达式](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/10.md)

**18.表达数值的字符串**

> 判断字符串是不是可以用十进制表示，使用直接法遍历看是否能够到达字符串的尾部。特殊的字符有`" "`\(空格\)、`"+"`、`"-"`、`"e"`、`"E"`、`"."`。字符串左右的空格首先去掉，中间出现空格即为非法；`"e"`、`"E"`重复出现以及后面不跟数字为非法；多符号的情况下，前一个不为`"e"`、`"E"`非法，单符号下前一个字符为`"e"`或`"E"`非法；字符不满足`"0"~"9"`非法。
>
> 字符串转换为整数：注意进位，重点是这个判断：
>
> ```cpp
> if(res > INT_MAX / 10 ||(res == INT_MAX / 10 && cur >= -(INT_MIN % 10)))
>     return flag > 0 ? INT_MAX : INT_MIN;
> ```

[面试题20](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/offer20.md) 、[65 有效的数字](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/65.md)、[8 字符转换为整数](https://github.com/iezhuozhuo/leetcode-/tree/e2a24c7782b3dbe157705f2b09ff5071caa8733c/8.md)

**19.调整奇数在偶数前面**

> 双指针以及辅助栈或者数组

[面试题21](offer21.md) 

**20.链表中倒数第K个节点**

> 寻找倒数第K个节点和删除倒数第K个节点的区别。

[面试题22](offer22.md) 

**21.链表中环的入口**

> 快慢指针法：先判断是否有环然后寻找环的入口。`Floyd`算法的推导熟记。

[面试题23](offer23.md) 、[141 环形链表](141.md) 、[142 环形链表 II](142.md)

**22.反转链表**

> 基础题直接手撸，重点是扩展题K个一组反转链表(多画图)。

[面试题24](offer24.md) 、[206 反转链表](206.md) 、 [629 k个逆序对数组](629.md) 

**23.合并两个排序链表**

> 直接手撸，重点是扩展题合并K个排序链表

[面试题25](offer25.md) 、[23 合并k个排序链表](23.md)

**24.树的子结构**

> 递归法直接手撸

[面试题26](offer26.md) 