#最直观的思路



```shell
class Solution:
    def singleNumbers(self, nums: List[int]) -> List[int]:
        val = 0
        for i in nums:
            val ^= i
        mask = 1
        while (val & mask) == 0:
            mask <<= 1
        a, b = 0, 0
        for i in nums:
            if (i & mask) == 0:
                a ^= i
            else:
                b ^= i
        return [a, b]

```


