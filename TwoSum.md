# LeetCode刷题系列（四）：Two Sum（1）

[题目链接][1]

## 暴力破解

```java
public int[] twoSum(int[] nums, int target) {
    for (int i = 0; i < nums.length; i++) {
        for (int j = i + 1; j < nums.length; j++) {
            if (nums[j] == target - nums[i]) {
                return new int[] { i, j };
            }
        }
    }
    throw new IllegalArgumentException("No two sum solution");
}
```
时间复杂度：O($n^2$)

空间复杂度：O(1)

## 
利用哈希表查找快的特性

[1]:
https://leetcode.com/problems/two-sum/description/ "题目链接"
