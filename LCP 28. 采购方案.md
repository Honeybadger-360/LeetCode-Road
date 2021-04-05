#最直观的思路

利用双指针，双百写法
首先将nums数组进行sort排序
随后建立两个指针i和j，分别代表遍历的起始点和终止点
q为每次嵌套循环的终止点，因为一个小的数+nums[q]都不满足<= target，因此后面的数更不会满足（这一步非常重要，否则就会超时）
随后两层for循环开始遍历List，
当遍历到第一组可以使 nums[i] + nums[j] <= target and j > i时，
直接计算j-i变为满足nums[i] + nums[j] <= target的组合数
随后令q为j + 1，这便是下次循环的终止点。（不加这一步便会超时）
当j<=i时跳出循环
返回取余后的结果即可



```shell
class Solution:
    def purchasePlans(self, nums: List[int], target: int) -> int:
        nums.sort()
        Max = 1e9+7
        res = 0
        q = len(nums)
        for i in range(0,len(nums)-1):
            for j in range(q-1,0, -1):
                if nums[i] + nums[j] <= target and j > i:
                    res = (res + j - i) % Max
                    q = j + 1
                    break
            if j <= i:
                break
        return int(res % Max)
        

```
