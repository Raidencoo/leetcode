171 Excel表列序号

> 给定一个Excel表格中的列名称，返回其相应的列序号。
>
>  A -> 1
>     B -> 2
>     C -> 3
>     ...
>     Z -> 26
>     AA -> 27
>     AB -> 28 
>     ...

26进制转10进制，不用用字典一一对应，只要用ascii码减去某个值就可以了，这里是减去64，因为A的ascii码是65.

```python
class Solution(object):
    def titleToNumber(self, s):
        """
        :type s: str
        :rtype: int
        """
        sum=0
        for i in range(len(s)):
            sum+=26**(len(s)-1-i)*(ord(s[i])-64)
        return sum
```

