★LCP 2 分式化简

![img](https://assets.leetcode-cn.com/aliyun-lc-upload/uploads/2019/09/09/fraction_example_1.jpg)

> 输入的cont代表连分数的系数（cont[0]代表上图的a0，以此类推）。返回一个长度为2的数组[n, m]，使得连分数的值等于n / m，且n, m最大公约数为1。
>
> 示例 1：
>
> 输入：cont = [3, 2, 0, 2]
> 输出：[13, 4]
> 解释：原连分数等价于3 + (1 / (2 + (1 / (0 + 1 / 2))))。注意[26, 8], [-13, -4]都不是正确答案。

```python
class Solution(object):
    def fraction(self, cont):
        """
        :type cont: List[int]
        :rtype: List[int]
        """
        res=[cont[-1],1]
        length=len(cont)
        for i in range(length-1,0,-1):
            temp=res[1]
            res[1]=res[0]
            res[0]=cont[i-1]*res[1]+temp
        return res
```

