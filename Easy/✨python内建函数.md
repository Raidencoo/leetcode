*python内建函数

1. 最大公约数：

   `from fractions import gcd`

   `gcd(param1,param2)`求二者的最大公约数

2. reduce：

   e.g `reduce(gcd, vals)`,表示对于迭代器`vals`中的元素，用`gcd`先对头两个元素求解，再把求得的解与下一个元素同样用`gcd`求解，以此类推。

3. 计数：

   `dict=collections.Counter(iter)`

4. 分组：

   `from itertools import groupby`

   `groupby(iter)`是将一个列表中相同的元素归为一组，返回的是两个值：（组别名，组中元素）