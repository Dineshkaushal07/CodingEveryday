# [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/submissions/)

Given a string s, find the length of the longest substring without repeating characters.

### Example 1:

```
Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3.
```
### Example 2:

```
Input: s = "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.
```
Time Complexity O(n^2) and Space complexity O(no. of distinct Chracters)
<details><summary>Solution1:</summary>
<p>
    
```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        di={}
        #mini=0
        maxlen=0
        for i in range(len(s)):
            if s[i] in di.keys():
                maxlen=max(maxlen,len(di))
                n=s[:di[s[i]]]
                n.replace(s[i],"")
                for j in range(len(n)):
                    if n[j] in di.keys():
                        if di[n[j]] < di[s[i]]:
                            del di[n[j]]
                di[s[i]]=i
            else:
                di[s[i]]=i
            if i==len(s)-1:
                di[s[i]]=i
                maxlen=max(maxlen,len(di))
                return maxlen
        return maxlen
```
</p>
</details>

TimeComplexity O(n) Space Complexity O(m) where m is the Charset Table .

<details><summary>Solution2:</summary>
<p>
    
```python        
    class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
            chars = [None] * 128
            left = 0
            right = 0
            res = 0
            while right<len(s):
                c = s[right]
                index = chars[ord(c)]
                if index!=None and index >= left and index < right:
                    left=index+1
                res=max(res,right-left+1)
                chars[ord(c)]=right
                right=right+1
            return res        
```
</p>
</details>            
        
