## 164.Maximum Gap

## 题目描述

给定一个无序的数组，找出数组在排序之后，相邻元素之间最大的差值。

如果数组元素个数小于 2，则返回 0。

**示例 1:**

```
输入: [3,6,9,1]
输出: 3
解释: 排序后的数组是 [1,3,6,9], 其中相邻元素 (3,6) 和 (6,9) 之间都存在最大差值 3。
```

**示例 2:**

```
输入: [10]
输出: 0
解释: 数组元素个数小于 2，因此返回 0。
```

**说明:**

- 你可以假设数组中所有元素都是非负整数，且数值在 32 位有符号整数范围内。
- 请尝试在线性时间复杂度和空间复杂度的条件下解决此问题。



### 解答

​	这道题我的做法比较简单，首先用sort方法对数组排序，然后再遍历数组，得到最大的间距。评论区复杂点的做法使用桶排序的方式去做的，可以参考一下。

```python
class Solution(object):
    def maximumGap(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        nums.sort() # 时间复杂度为:nlogn
        max_gap = 0
        for i in range(1,len(nums)):
            if nums[i]-nums[i-1]>max_gap:
                max_gap =  nums[i]-nums[i-1]
        return max_gap
```

- 时间复杂度：$O(nlogn)$
- 空间复杂度：$O(1)$