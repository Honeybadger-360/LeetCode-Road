#最直观的思路



```shell
class Solution:
    def isStraight(self, nums: List[int]) -> bool:
        val = set()
        ma,mi = 0, 14
        for i in nums:
            if i == 0:
                continue
            else:
                ma = max(ma, i)
                mi = min(mi, i)
            if i in val:
                return False
            val.add(i)
        return ma - mi < 5  
                  
```
