#122_Best_Time_to_Buy_and_Sell_Stock_II

------

> - 问题
> - 代码
> - 思路

------

## 问题

 122.买卖股票的最佳时机 II

给定一个数组，它的第 i 个元素是一支给定股票第 i 天的价格。

 

设计一个算法来计算你所能获取的最大利润。你可以尽可能地完成更多的交易（多次买卖一支股票）。

 

注意：你不能同时参与多笔交易（你必须在再次购买前出售掉之前的股票）。

 

示例 1:

 

输入: [7,1,5,3,6,4]

输出: 7

解释: 在第 2 天（股票价格 = 1）的时候买入，在第 3 天（股票价格 = 5）的时候卖出, 这笔交易所能获得利润 = 5-1 = 4 。

​     随后，在第 4 天（股票价格 = 3）的时候买入，在第 5 天（股票价格 = 6）的时候卖出, 这笔交易所能获得利润 = 6-3 = 3 。

示例 2:

 

输入: [1,2,3,4,5]

输出: 4

解释: 在第 1 天（股票价格 = 1）的时候买入，在第 5 天 （股票价格 = 5）的时候卖出, 这笔交易所能获得利润 = 5-1 = 4 。

​     注意你不能在第 1 天和第 2 天接连购买股票，之后再将它们卖出。

​     因为这样属于同时参与了多笔交易，你必须在再次购买前出售掉之前的股票。

示例 3:

 

输入: [7,6,4,3,1]

输出: 0

解释: 在这种情况下, 没有交易完成, 所以最大利润为 0。

## 代码

```python
class Solution:
    def maxProfit(self, prices):
        """
        :type prices: List[int]
        :rtype: int
        """
        # res=0
        # i=0
        # while i<len(prices)-1:
        #     if prices[i]<prices[i+1]:
        #         cur_min=prices[i]
        #         while i<len(prices)-1 and prices[i]<prices[i+1]:
        #             i+=1
        #         res+=prices[i]-cur_min            
        #     else:
        #         i+=1
        # return res
        res=0
        for i in range(0,len(prices)-1):
            if prices[i]<prices[i+1]:
                res+=prices[i+1]-prices[i]
        return res
if __name__ == "__main__":
    sl=Solution()
    prices=[1,2,3,4,5]
    print(sl.maxProfit(prices))
```

## 思路

思路：

很简单，刚开始的时候思路是，便利prices数组，找到递增序列，然后首位相减得到差值。保存进res，最后返回。

更简单的思路是，直接不用找递增序列，只要遇到prices[i]<prices[i+1]，就将差值保存进res，结果是与前一个思路一样的，但是简单了很多。

 