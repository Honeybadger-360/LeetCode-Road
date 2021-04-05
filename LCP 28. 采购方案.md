#最直观的思路




```shell
class Solution:
    def purchasePlans(self, nums: List[int], target: int) -> int:
        nums.sort()
        Max = 1e9+7
        res = 0
        q = len(nums)
        i, j = 0,0
        for i in range(0,len(nums)-1):
            for j in range(q-1,0, -1):
                if nums[i] + nums[j] <= target and j > i:
                    print (res)
                    res = (res + j - i) % Max
                    q = j + 1
                    break
            if j <= i:
                break
        return int(res % Max)
        

```
