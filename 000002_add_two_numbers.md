Link
---
https://leetcode.com/problems/add-two-numbers/description/

Mine Code
---
```
class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode *result_list = NULL;
        ListNode *current_node = NULL;
        int next_step = 0;
        int current_val = 0;
        while(l1!=NULL || l2!=NULL){
            
            current_val += next_step;
            if(l1!=NULL)
            {
                current_val += l1->val;
                l1 = l1->next;
            }
            if(l2!=NULL)
            {
                current_val += l2->val;
                l2 = l2->next;
            }
            
            next_step = current_val/10;
            current_val = current_val%10;
            
            if(result_list==NULL)
            {
                result_list = new ListNode(current_val);
                current_node = result_list;
            }
            else
            {
                current_node->next = new ListNode(current_val);
                current_node = current_node->next;
            }
            
            current_val = 0;
        }
        
        if(next_step)
        {
            current_node->next = new ListNode(next_step);
        }
        
        return result_list;
    }
};
```
