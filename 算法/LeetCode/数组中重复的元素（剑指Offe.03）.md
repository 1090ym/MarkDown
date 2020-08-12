# 数组中重复的元素（剑指Offe.03）

>
> **题目描述：**
> 在一个长度为 n 的数组 nums 里的所有数字都在 0～n-1 的范围内。数组中某些数字是重复的，但不知道有几个数字重复了，也不知道每个数字重复了几次。请找出数组中任意一个重复的数字。

### 解题思路
- 遍历数组，采用HashMap存储元素，如果HashMap中已经出现过该元素，则返回，时间复杂度O(N)，空间复杂度O(N)
- 遍历数组元素，交换数组中的元素，使得nums[i] = i，如果在交换时发现两个元素相等，则返回该重复的元素。

### 算法原理
- 遍历到索引为i的元素nums[i]时，将其和索引为nums[i]处的元素nums[nums[i]]进行交换。
- 如果存在重复的数字，则在交换某个元素x时，一定有nums[x] == x

### 算法流程
- 遍历数组nums
	1. 若：nums[i] == i，说明数组已经在索引位置了，无需交换，执行i++和continue
	2. 若：如果nums[nums[i]] == nums[i]，说明索引为nums[i]处的索引值也为nums[i]，找到重复元素，返回nums[i]
	3. 否则：当前元素是第一次遇到，交换索引为i和nums[i]的两个元素
- 如果遍历完没有找到，则返回-1

### Java代码
```java
class Solution {
    public int findRepeatNumber(int[] nums) {
        int i = 0;
        while(i < nums.length) {
            if(nums[i] == i) {
                i++;
                continue;
            }
            if(nums[nums[i]] == nums[i]) 
                return nums[i];
            else {
                int tmp = nums[i];
                nums[i] = nums[tmp];
                nums[tmp] = tmp;
            }
        }
        return -1;
    }
}
```