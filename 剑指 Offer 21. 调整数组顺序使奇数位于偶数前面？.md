#最直观的思路



```shell
class Solution:
    def exchange(self, nums: List[int]) -> List[int]:
        # a, b = [], []
        # for i in nums:
        #     if i % 2 == 0:
        #         a.append(i)
        #     else:
        #         b.append(i)
        # for i in a:
        #     b.append(i)
        # return b

        slow, fast = 0 ,0 
        for fast in range(len(nums)):
            if nums[fast] & 1:
                nums[slow], nums[fast] = nums[fast], nums[slow]
                slow += 1
        return nums
```


