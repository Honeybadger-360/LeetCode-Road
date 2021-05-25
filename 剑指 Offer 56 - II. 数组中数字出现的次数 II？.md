#最直观的思路



```shell
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        # val = {}
        # for i in nums:
        #     if i not in val:
        #         val[i] = 0
        #     val[i] += 1
        # for i in val:
        #     if val[i] == 1:
        #         return i


        #二进制计数法
        res = [0] * 32
        ans = 0
        for i in range(len(nums)):
            for j in range(32):
                res[j] += 1 & (nums[i] >> j)
        
        for i in range(len(res)):
            if res[i] % 3 != 0:
                ans += pow(2, i)
        return ans
              
```


