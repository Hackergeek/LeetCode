# LeetCode刷题系列:Jewels and Stones(771)

***刷题顺序：从易到难***

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

除了这种常规解法之外，我在讨论区还看到另外两种解法。

## 较优解法

[参考链接][1]

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

## 一行代码解法

[参考链接][2]

```java
public int numJewelsInStones(String J, String S) {
return S.replaceAll("[^" + J + "]", "").length();
}
```

[1]: https://leetcode.com/problems/jewels-and-stones/discuss/125656/Java-Beat-99 "Jewels and Stones 较优解法"
[2]: https://leetcode.com/problems/jewels-and-stones/discuss/113574/1-liners-PythonJavaRuby "Jewels and Stones 一行代码解法"