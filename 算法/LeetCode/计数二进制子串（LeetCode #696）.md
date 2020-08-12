# 计数二进制子串（LeetCode #696）

### 题目

给定一个字符串 s，计算具有相同数量0和1的非空(连续)子字符串的数量，并且这些子字符串中的所有0和所有1都是组合在一起的。

**注**：重复出现的子串要计算它们出现的次数。

**示例  :**

```
输入: "10101"
输出: 4
解释: 有4个子串：“10”，“01”，“10”，“01”，它们具有相同数量的连续1和0。
```

链接：https://leetcode-cn.com/problems/count-binary-substrings

### 解题思路

对于任意一个连续的0和1组成的子串，假设包含a个0和b个1，则该子串中符合条件的子串有min{a,b}个，例如00011，则符合条件的有01，0011。

### 算法流程

**1.** 计算字符串中连续的0和的个数，存放在数组中，例如00100111可得到数组{2,1,2,3}

**2.** 遍历数组中所有相邻的数对，以此找出相邻两个数中的最小值并累加

**3.** 累加的结果即为符合条件的子串个数。

### 代码

```java
class Solution {
    public int countBinarySubstrings(String s) {
        List<Integer> counts = new ArrayList<Integer>();
        int ptr = 0, n = s.length();
        while (ptr < n) {
            char c = s.charAt(ptr);
            int count = 0;
            while (ptr < n && s.charAt(ptr) == c) {
                ++ptr;
                ++count;
            }
            counts.add(count);
        }
        int ans = 0;
        for (int i = 1; i < counts.size(); ++i) {
            ans += Math.min(counts.get(i), counts.get(i - 1));
        }
        return ans;
    }
}
```

