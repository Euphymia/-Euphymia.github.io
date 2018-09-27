#66_Plus_One

---

> * 问题 
> * 代码
> * 思路

---

## 问题

\66. 加一

给定一个非负整数组成的非空数组，在该数的基础上加一，返回一个新的数组。

最高位数字存放在数组的首位， 数组中每个元素只存储一个数字。

你可以假设除了整数 0 之外，这个整数不会以零开头。

示例 1:

输入: [1, 2, 3]

输出: [1, 2, 4]

解释: 输入数组表示数字 123。

示例 2:

输入: [4, 3, 2, 1]

输出: [4, 3, 2, 2]

解释: 输入数组表示数字 4321。

## 代码

```python
class Solution:
    def plusOne(self, digits):
        """
        :type digits: List[int]
        :rtype: List[int]
        """
        # if digits[-1]<9:
        #     digits[-1]=digits[-1]+1
        #     return digits
        l=len(digits)-1
        while digits[l]==9 and l>=0:
            digits[l]=0
            l-=1
        if l==-1:
            a=[1]
            a.extend(digits)
            return a
        else:
            digits[l]=digits[l]+1
        return digits

if __name__ =='__main__':
    sl=Solution()
    result=sl.plusOne([0])
    print(result)
```

##思路

思路：

将一个数字的每个位上的数字分别存到一个一维向量中，最高位在最开头，我们需要给这个数字加一，即在末尾数字加一，如果末尾数字是9，

那么则会有进位问题，而如果前面位上的数字仍为9，则需要继续向前进位。具体算法如下：首先判断最后一位是否为9，若不是，直接加一返回，

若是，则该位赋0，再继续查前一位，同样的方法，知道查完第一位。如果第一位原本为9，加一后会产生新的一位，那么最后要做的是，

查运算完的第一位是否为0，如果是，则在最前头加一个1

 