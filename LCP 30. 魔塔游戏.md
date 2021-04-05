#最直观的思路

利用最小堆可以求解

add用来存放当前的和
当遇到正数时，直接相加即可
当遇到负数时，首先将此值入堆，
同时检查当前的和是否<0,
若和小于0，则将和减去当前堆里最小的值，也就是堆里0位置上的元素
同时将此值移出堆
可以想成将当前元素移动到数组的最后面，所以res+=1
最后返回res即可



```shell
class Solution:
    def magicTower(self, nums: List[int]) -> int:
        if sum(nums) + 1 < 0:
            return -1
        res = 0
        add = 0
        neg = []
        for i in range(len(nums)):
            add += nums[i]
            if nums[i] < 0:
                heappush(neg, nums[i])
                if add < 0:
                    add -= neg[0]
                    heappop(neg)
                    res +=1
        return res
      
```
