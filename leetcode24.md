[反转链表](https://leetcode-cn.com/problems/fan-zhuan-lian-biao-lcof/)
``` 
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
