#最直观的思路



```shell
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None
class Solution:
    def deleteNode(self, head: ListNode, val: int) -> ListNode:

        
        # dummy = ListNode(-1)
        # dummy.next = head
        # cur = dummy
        # while cur.next:
        #     if cur.next.val == val:
        #         cur.next = cur.next.next
        #         break
        #     else:
        #         cur = cur.next
        # return dummy.next


        dummy = ListNode(1)
        dummy.next = head
        pre, cur = dummy, dummy.next
        while cur:
            if cur.val == val:
                pre.next = cur.next
                break
            else:
                pre = cur
                cur = cur.next
        return dummy.next

```


