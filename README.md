---
description: 桃李春风一杯酒，江湖夜雨十年灯
---

# 愿

我希望我的刷题过程可以如下所述：

老僧三十年前未参禅时，见山是山，见水是水。及至后来，亲见知识，有个入处，见山不是山，见水不是水。而今得个体歇处，依前见山只是山，见水只是水。

终有一天，我愿不负如来不负卿！

# 剑指offer

剑指offer系列很多题与前面的leetcode重复，因此题解很简陋可参考前面题解。

**1.数组中重复的数组及相关题**

> 可以考虑的解法有：排序(桶排序)、异或，二分法，模拟环法(不常用)。

[面试题3](offer3.md) 、[41 缺失的第一个整数](41.md) 、[268 缺失的数字](268.md) 、[287 寻找重复数](287.md)。

**2.二维数组的查找及相关题**

> 二维数组可以通过左上和右下两个点可以确定。

[面试题4](offer4.md) 、[240 搜索二维矩阵 II](240.md) 、[48 旋转图像](48.md) 、[54 螺旋矩阵](54.md) 

**3.替换空格**

> 打破惯性思维，从后往前操作。

[面试题5](offer5.md)、[283 移动零](283.md) 

**4.链表的遍历相关**

> 主要是链表的定义以及遍历的考察

[面试题6](offer6.md) 、[面试题24](offer24.md) 

**5.重构二叉树**

> 二叉树三种遍历两两结合，重点参考[笔记](https://blog.csdn.net/qq_34342154/article/details/77104202)。注意：前序遍历和后序遍历需要左右孩子都存在。

[面试题7](offer7.md) 、[105 重建二叉树](105.md) 

**6.二叉树下一个节点**

> 遍历使用中序遍历--左根右，对于给定的节点以是否有右孩子来区分情况。

[面试题8](offer8.md)

**7.用两个栈来实现队列**

> 一个倒，一个装。

[面试题9](offer9.md) 、[232 用栈实现队列](232.md) 

**8.斐波那契数列**

> 斐波拉契数列的思路实际是简单动态规划。包括青蛙跳台阶、变态跳问题

[面试题10](offer10.md) 

**9.旋转数组中找最小值**

> 旋转数组中找数不管是找最小值还是找某个`target`的方法都是一致的：首先需要考虑数组中是否有重复的值(这些值需要跳过)，然后确定断点的位置，非断点位置的序列是升序，可以直接判断是否有值。

[面试题11](11.md) 、[33 在有序数组中找数](33.md) 、[81 搜索旋转排序数组II](81.md)  、[153 寻转旋转排序数组中最小值I](153.md) 、[154 寻找旋转排序数组中最小值II](154.md) 