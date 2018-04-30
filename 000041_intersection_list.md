Link
---
https://leetcode.com/problems/intersection-of-two-linked-lists/description/

Mine Code
---
```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        
        ListNode *curr_headA = headA;
        while(curr_headA)
        {
            ListNode *curr_headB = headB;
            while(curr_headB)
            {
                if(curr_headA==curr_headB)
                {
                    return curr_headA;
                }
                curr_headB = curr_headB->next;
            }
            curr_headA = curr_headA->next;
        }
        
        return NULL;
    }
};
```
