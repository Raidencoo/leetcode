412 Fizz Buzz

> 写一个程序，输出从 1 到 n 数字的字符串表示。
>
> 1. 如果 n 是3的倍数，输出“Fizz”；
>
> 2. 如果 n 是5的倍数，输出“Buzz”；
>
> 3.如果 n 同时是3和5的倍数，输出 “FizzBuzz”。
>

迄今为止最简单的题目，没有之一。有点怀疑自己是否没注意到题目中的陷阱，直到提交才发现想多了。

只需注意：

1.各if之间是有先后顺序的，先判断同时能被3，5整除，再判断其余两个条件。不然能被15整除的一定可以被3，5整除。

2.if..if..if是独立判断的，而if..elif..elif..else是互斥的关系。

```python
class Solution(object):
    def fizzBuzz(self, n):
        """
        :type n: int
        :rtype: List[str]
        """
        l=[]
        for i in range(1,n+1):       
            if i%3==0 and i%5==0:
                l.append("FizzBuzz")
            elif i%3==0:
                l.append("Fizz")
            elif i%5==0:
                l.append("Buzz")
            else:
                l.append(str(i))           
        return l
```

