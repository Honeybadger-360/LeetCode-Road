#最直观的思路



```shell
class Solution:
    def findNumberIn2DArray(self, matrix: List[List[int]], target: int) -> bool:
        # if not matrix:
        #     return False
        # n = len(matrix)
        # m = len(matrix[0])
        # i, j = 0, 0
        # for i in range(n):
        #     for j in range(m):
        #         if matrix[i][j] == target:
        #             return True
        # return False

        if not matrix:
            return False
        n = len(matrix)
        m = len(matrix[0])
        i, j = len(matrix) - 1, 0
        while i >= 0 and j < m:
            if matrix[i][j] > target:
                i -= 1
            elif matrix[i][j] < target:
                j += 1
            else:
                return True
        return False


```


