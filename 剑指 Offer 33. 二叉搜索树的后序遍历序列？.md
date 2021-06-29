#最直观的思路



```shell
class Solution:
    def verifyPostorder(self, postorder: List[int]) -> bool:
        def isval(i, j):
            if i >= j: #必须是大于等于，防止i=j时，其判断（small，j-1）时出现越界
                return True
            val = i
            while postorder[val] < postorder[j]:
                val += 1
            small = val
            while postorder[val] > postorder[j]:
                val += 1
            return val == j and isval(i, small-1) and isval(small, j-1)
        return isval(0, len(postorder) - 1)




```


