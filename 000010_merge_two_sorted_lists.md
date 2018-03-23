Link
---
https://leetcode.com/problems/merge-two-sorted-lists/description/

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
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        ListNode *result = NULL;
        ListNode *current = NULL;

        
        while(l1!=NULL || l2!=NULL)
        {
            if(l1==NULL)
            {
                if(result==NULL)
                {
                    result = new ListNode(l2->val);
                    current = result;
                }
                else
                {
                    current->next = new ListNode(l2->val);
                    current = current->next;
                }
                l2 = l2->next;
                continue;
            }
            
            if(l2==NULL)
            {
                if(result==NULL)
                {
                    result = new ListNode(l1->val);
                    current = result;
                }
                else
                {
                    current->next = new ListNode(l1->val);
                    current = current->next;
                }
                l1 = l1->next;
                continue;
            }
            
            if(l1->val>=l2->val)
            {
                if(result==NULL)
                {
                    result = new ListNode(l2->val);
                    current = result;
                }
                else
                {
                    current->next = new ListNode(l2->val);
                    current = current->next;
                }
                l2 = l2->next;
            }
            else
            {
                if(result==NULL)
                {
                    result = new ListNode(l1->val);
                    current = result;
                }
                else
                {
                    current->next = new ListNode(l1->val);
                    current = current->next;
                }
                l1 = l1->next;
            }
        }
        
        
        return result;
    }
};
```
