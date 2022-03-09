# [License Key Formatting](https://leetcode.com/explore/interview/card/google/67/sql-2/472/)
<p>
You are given a license key represented as a string s that consists of only alphanumeric characters and dashes. The string is separated into n + 1 groups by n dashes. You are also given an integer k.

We want to reformat the string s such that each group contains exactly k characters, except for the first group, which could be shorter than k but still must contain at least one character. Furthermore, there must be a dash inserted between two groups, and you should convert all lowercase letters to uppercase.

Return the reformatted license key.
</p>


```
Input: s = "5F3Z-2e-9-w", k = 4
Output: "5F3Z-2E9W"
Explanation: The string s has been split into two parts, each part has 4 characters.
Note that the two extra dashes are not needed and can be removed.
```

<details><summary>Solution</summary>

  <p>
    
    ```
    class Solution:
    def licenseKeyFormatting(self, s: str, k: int) -> str:
        n=""
        counter=0
        for i in range(len(s)-1,-1,-1):
            if s[i].isalnum():
                counter=counter+1
                n=n+s[i]
                if counter%k==0:
                    n=n+'-'
        if counter==0:
            return ""
        if n[len(n)-1]=='-':
            q=n[:len(n)-1]
        else:
            q=n[:len(n)]
        p=""
        for i in range(len(q)-1,-1,-1):
            p=p+q[i]
        return p.upper()
    ```
  </p>
  <details>

