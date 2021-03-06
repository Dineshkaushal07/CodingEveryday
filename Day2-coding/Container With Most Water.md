# [Container With Most Water](https://leetcode.com/problems/container-with-most-water/)
You are given an integer array height of length n. There are n vertical lines drawn such that the two endpoints of the ith line are (i, 0) and (i, height[i]).

Find two lines that together with the x-axis form a container, such that the container contains the most water.

Return the maximum amount of water a container can store.

Notice that you may not slant the container.
![question_11](https://user-images.githubusercontent.com/97383137/157504996-a6219e7d-5172-4ad6-80cd-31dc18788de0.jpg)

```
Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container 
can contain is 49.
```
Time Complexity O(n) Space Complexity O(1) 
<details><summary>Solution</summary>
<p>
    
```python
    class Solution:
    def maxArea(self, height: List[int]) -> int:
        water=0
        i=0
        j=len(height)-1
        while i<j:
            water = max(water,(j-i)*min(height[i],height[j]))
            if height[i]<height[j]:
                i=i+1
            else:
                j=j-1
        return water
```
</p>  
</details>
    
