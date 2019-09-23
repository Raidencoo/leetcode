28 strStr()

> 在一个字符串中找另一个字符串第一次出现的位置

*如果子字符串为空，则返回0，如果子字符串长度大于母字符串长度，则返回-1*

1. 

```python

class Solution(object):
    def strStr(self, haystack, needle):
        """
        :type haystack: str
        :type needle: str
        :rtype: int
        """
        if not needle:
            return 0
        for i in range(len(haystack)-len(needle)+1):
        	if len[i:i+len(needle)]==needle:
        		return i
        return -1
```

2. 

```python
class Solution(object):
    def strStr(self, haystack, needle):
        """
        :type haystack: str
        :type needle: str
        :rtype: int
        """
        if needle == "":
            return 0
        if needle in haystack:
            return len(haystack.split(needle)[0])
        else:
            return -1
```

1. 判断两段字符相同，切片就好了，我之前的想法很复杂，将二者zip(),然后len(set()),-->[1,1,1..]形如这样的列表才算一一对应的相等，然后计算sum()是否等于字串长度。其实完全没想到python的切片功能。
2. in这个封装函数，可以判断包含关系。

