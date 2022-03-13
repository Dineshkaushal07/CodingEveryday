# [Fizz Buzz](https://leetcode.com/problems/fizz-buzz/)

Given an integer n, return a string array answer (1-indexed) where:

answer[i] == "FizzBuzz" if i is divisible by 3 and 5.
answer[i] == "Fizz" if i is divisible by 3.
answer[i] == "Buzz" if i is divisible by 5.
answer[i] == i (as a string) if none of the above conditions are true.

```
Example 1:

Input: n = 3
Output: ["1","2","Fizz"]
```

```
Example 2:

Input: n = 5
Output: ["1","2","Fizz","4","Buzz"]
```

Time Complexity O(n)
Space O(n)
<details><summary>Solution</summary>
<p>
  
```python
class Solution:
    def fizzBuzz(self, n: int) -> List[str]:
        l=[]
        for i in range(1,n+1):
            if i%3 == 0 and i%5 == 0:
                l.append("FizzBuzz")
            elif i%3 == 0:
                l.append("Fizz")
            elif i%5 == 0:
                l.append("Buzz")
            else:
                l.append(str(i))
        return l
```
</p>
</details>

