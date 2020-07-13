#### [放苹果](https://blog.csdn.net/u012283461/article/details/52761238)

把M个同样的苹果放在N个同样的盘子里，允许有的盘子空着不放，问共有多少种不同的分法？

分两种：有空盘子或者没有空盘子
有空盘子：f(m, n) = f(m, n - 1) 有递归的思想可以空1，2，3，…，
没有空盘子：当m>n时--先每一个放1个，那么就剩下了(m-n)继续放的问题；当m < n时--就剩下每一个盘子放一个。
综合：f(m,n) = f(m, m) m<n; f(m,n) = f(m, n-1) + f(m-n, n) m > n

##### 递归

```c++
// m 苹果数  k 盘子
int palceApple(int m, int k){
	if(m == 0 || k == 1)
		return 1;
	if(k > m)
		return palceApple(m, m);
	else
		return palceApple(m, k-1) + placeApple(m-k, k);
}
```

##### 动态规划

```c++
int placeApple(int m, int k){
    int dp[m+1][k+1];
    for(int i = 0;i <= m;i++){
        dp[i][0] = 1;
        dp[i][1] = 1;
    }
    for(int i = 0;i <= k;i++){
        dp[0][i] = 1;
        dp[1][i] = 1;
    }
    for(int i = 2;i <= m;i++){
        for(int j = 2;j <= k;j++){
            if(i < j)
                dp[i][j] = dp[i][i];
            else
                dp[i][j] = dp[i][j-1] + dp[i-j][j];
        }
    }
}
```

