# [Two Sum](https://leetcode.com/problems/two-sum/)

<p>
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.
</p>

```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```
## Brute Force 
Time Complexity O(n^2) Space O(1)
<details><summary>Solution</summary>

<p>
  
```python
  class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in range(len(nums)):
            for j in range(i+1,len(nums)):
                sum=nums[i]+nums[j]
                if sum==target:
                    return [i,j]
```
</p>
</details>

## Improved Solution 
Time Complexity O(n) Space O(n)
<details><summary>Solution</summary>

<p>
  
```python
  class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        di={}
        for i in range(len(nums)):
            sum=target-nums[i]
            if sum in di.keys():
                return [i,di[sum]]
            else:
                di[nums[i]]=i
```
</p>
</details>
