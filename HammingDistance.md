# LeetCode刷题系列（三）：Hamming Distance(461)

[题目链接][2]
## 常规解法

解题思路：

1. 将两个整数x和y进行异或运算，得到差异数n
2. 求出差异数n的二进制表示中有多少个1

关于如何求一个数的二进制表示中1的个数，可以参考《剑指offer》中的面试题10

```java
public int hammingDistance(int x, int y) {
    int n = x ^ y;
    int count = 0;
    while(n > 0) {
        n = (n - 1) & n;
        ++count;
    }
    return count;
}
```

## 一行代码解法

[参考链接][1]

```Java
public class Solution {
    public int hammingDistance(int x, int y) {
        return Integer.bitCount(x ^ y);
    }
}
```

[1]: https://leetcode.com/problems/hamming-distance/discuss/94698/Java-1-Line-Solution-:D "Hamming Distance 一行代码解法"
[2]:https://leetcode.com/problems/hamming-distance/description/ "题目链接"
