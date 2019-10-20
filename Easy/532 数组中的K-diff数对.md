532 数组中的K-diff数对

> 给定一个整数数组和一个整数 k, 你需要在数组里找到不同的 k-diff 数对。这里将 k-diff 数对定义为一个整数对 (i, j), 其中 i 和 j 都是数组中的数字，且两数之差的绝对值是 k.
>

1. 超时算法

两个指针分别指向首尾，每一次循环时，若出现k则头指针指向下一个值，尾指针初始化指向最后，值得注意的是需要考虑若一次循环时没有出现k，则还是要将头指针指向下一个值

```python
class Solution(object):
    def findPairs(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: int
        """
        s=sorted(nums)
        l=0
        r=len(s)-1
        map={}
        while l<=r:
            if abs(s[r]-s[l])==k and r!=l:
                if s[l] not in map:
                    map[s[l]]=s[r]
                l+=1     
                r=len(s)-1                            
            elif abs(s[r]-s[l])!=k and l!=r:
                r-=1
            elif l==r:
                l+=1     
                r=len(s)-1  
        return len(map)
```

2.哈希

遍历列表，对当前值查找n+/-k是否在s集合中中，若在，则添加进r集合，每次循环均将当前值添加至s集合。

```
class Solution(object):
    def findPairs(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: int
        """
        # 这里有一个细节需要注意的是: (1,3)等同于(3,1)
    # 所以我们无需将1,3都存储起来, 只要存储3即可. 因为k是确定的, 导致1也是确定的
        if k<0:
            return 0
        # s存储遍历的元素, r存储上面注释的3
        s, r = set(), set()
        for n in nums:
            if n + k in s:
                r.add(n + k)
            if n - k in s:
                r.add(n)
            s.add(n)
            
        return len(r)
```

