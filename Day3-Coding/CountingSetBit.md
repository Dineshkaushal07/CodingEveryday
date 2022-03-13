# Counting the Set Bits in a number 

Given an integer count the set bits of the integer i.e how many 1's it has

```
Example 1:
Input : 9
OutPut : 2
Explaination: 9 in binary is 1001 so no of 1's in 9 are 2
```
<details><summary>Solution</summary>
<p>

```python
a=int(input())
count=0
while(a):
    if a&1:
        count=count+1
    a=a>>1
print(count)
```
</p>
</details>  
  
        
        
