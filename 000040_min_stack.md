Link
---
https://leetcode.com/problems/min-stack/description/

Mine Code
---
```
struct Node
{
    int val_;
    Node *last_;
    Node *next_;
};

class MinStack {
public:
    /** initialize your data structure here. */
    Node *head;
    Node *curr;
    MinStack() {
        head = new Node();
        // using head node store some information
        head->val_ = 1;
        head->last_ = NULL;
        head->next_ = NULL;
        curr = head;
    }
    
    void push(int x) {
        Node *node = new Node();
        node->val_ = x;
        node->last_ = curr;
        node->next_ = NULL;
        curr->next_ = node;
        curr = node;
        head->val_ += 1;
    }
    
    void pop() {
        if(head->val_>1)
        {
            head->val_ -= 1;   
            Node *last_node = curr;
            curr = last_node->last_;
            
            free(last_node);
        }
        
    }
    
    int top() {
        if(head->val_>1)
            return curr->val_;
    }
    
    int getMin() {
        if(head->val_<2)
        {
            return 0;
        }
        int min_value = head->next_->val_;
        Node *curr_node = head->next_;
        for(int i=1;i<head->val_;i++)
        {
            if(min_value>curr_node->val_)
                min_value = curr_node->val_;
            curr_node = curr_node->next_;
        }
        
        return min_value;
    }
};

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack obj = new MinStack();
 * obj.push(x);
 * obj.pop();
 * int param_3 = obj.top();
 * int param_4 = obj.getMin();
 */
```
