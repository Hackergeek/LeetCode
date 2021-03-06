# LeetCode刷题系列（一）:Jewels and Stones(771)

[题目链接][3]
## 常规解法

```java
public int numJewelsInStones(String J, String S) {
    int count = 0;
    int i = 0;
    while(J.length() > i) {
        for(int index = 0; index < S.length(); index++){
            if(S.charAt(index) == J.charAt(i)) {
                ++count;
            }
        }
        ++i;
    }
    return count;
}
```

这种解法的时间复杂度为O(n^2)。除了这种解法之外，还有一种更优的解法，我称之为查表法。

## 查表法

[参考链接][1]

解题思路：

1. 建表
2. 查表

```java
public int numJewelsInStones(String jewels, String stones) {
    boolean[] isAJewel = new boolean[52];
    for(char jewel: jewels.toCharArray()) isAJewel[jewelIndex(jewel)] = true;
    int jewelCount = 0;
    for(char stone: stones.toCharArray()) if(isAJewel[jewelIndex(stone)]) jewelCount++;
    return jewelCount;
}

private int jewelIndex(char jewel){
return (jewel >= 'A' && jewel <='Z')
        ? jewel-'A'+26
        : jewel-'a';
}
```

查表法的时间复杂度为O(n)，明显比上一种解法更快。

## 一行代码解法

[参考链接][2]

```java
public int numJewelsInStones(String J, String S) {
return S.replaceAll("[^" + J + "]", "").length();
}
```

[1]: https://leetcode.com/problems/jewels-and-stones/discuss/125656/Java-Beat-99 "Jewels and Stones 较优解法"
[2]: https://leetcode.com/problems/jewels-and-stones/discuss/113574/1-liners-PythonJavaRuby "Jewels and Stones 一行代码解法"
[3]:
https://leetcode.com/problems/jewels-and-stones/description/ "题目链接"