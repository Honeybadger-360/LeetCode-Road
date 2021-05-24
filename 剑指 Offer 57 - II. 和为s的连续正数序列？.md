#最直观的思路



```shell
import math
class Solution:
    def findContinuousSequence(self, target: int) -> List[List[int]]:
        if target == 1:
            return [[1]]
        left, right = 1,2
        temp = left + right
        res = []
        while right < math.ceil(target / 2):
            if temp < target:
                right += 1
                temp += right
            if temp > target:
                temp -= left
                left += 1
            if temp == target:
                ans = []
                for i in range(left, right + 1):
                    ans.append(i)
                res.append(ans)
                if len(ans) == 2:
                    break
                temp -= left
                left += 1
        return res
         
```


