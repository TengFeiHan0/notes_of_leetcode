[反转链表](https://leetcode-cn.com/problems/fan-zhuan-lian-biao-lcof/)
递归
``` c++
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        ListNode* pre{nullptr}, *cur = head;
        while(cur){
            ListNode* next = cur->next;
            cur->next = pre;
            pre = cur;
            cur = next;

        }

        return pre;

    }
};
``` 
迭代
```c++ 
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        if(!head) return NULL;
        if(!head->next) return head;
        ListNode * newHead = reverseList(head->next);
        head->next->next = head;
        head->next = NULL;
        return newHead;
    }
};
``` 
