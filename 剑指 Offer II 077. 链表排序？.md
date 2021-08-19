#最直观的思路

利用归并的思想

```shell
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def sortList(self, head: ListNode) -> ListNode:
        h = head
        length = 0
        while h:
            h = h.next
            length += 1
        res = ListNode(-1)
        res.next = head
        intv = 1
        while intv < length:
            pre = res
            h = res.next
            while h:
                h1 = h
                i = intv
                while i and h:
                    h = h.next
                    i -= 1
                if i:
                    break #已经不存在h2了
                h2 = h
                i = intv
                while i and h:
                    h = h.next
                    i -= 1
                c1 = intv
                c2 = intv - i
                while c1 and c2:
                    if h1.val < h2.val:
                        pre.next = h1
                        h1 = h1.next
                        c1 = c1 - 1
                    else:
                        pre.next = h2
                        h2 = h2.next
                        c2 -= 1
                    pre = pre.next
                pre.next = h1 if c1 else h2
                while c1 > 0 or c2 > 0:
                    pre = pre.next
                    c1 -= 1
                    c2 -= 1
                pre.next = h
            # print(res.next)
            intv *= 2
        return res.next

                        

```


