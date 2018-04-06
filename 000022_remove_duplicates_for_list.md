Link
---
https://leetcode.com/problems/remove-duplicates-from-sorted-list/description/

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
    ListNode* deleteDuplicates(ListNode* head) {
        ListNode *current = head;
        
        if(head==NULL)
        {
            return head;
        }
        
        ListNode *next = current->next;
        
        while(next)
        {
            if(current->val == next->val)
            {
                current->next = next->next;
                free(next);
                next = current->next;
            }
            else
            {
                current = next;
                next = next->next;
            }
        }
        
        return head;
    }
};
```
