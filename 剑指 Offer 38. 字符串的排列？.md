#最直观的思路


```shell
class Solution:
    def permutation(self, s: str) -> List[str]:
        res = []
        used = []
        path = ""
        def backtracking(val):
            nonlocal path
            if len(path) == len(s):
                res.append(path)
                return
            # print(path)
            for i in range(len(val)):
                if i not in used:
                    if i > 0 and val[i] == val[i-1] and (i-1) not in used: #同层去重，记着去重必须先将数组排序。
                        continue
                    path += val[i]
                    used.append(i)
                    backtracking(val)
                    path = path[:-1]
                    used.pop()
        backtracking(sorted(s))
        return res

```


