[删除链表倒数第k个节点](https://leetcode-cn.com/problems/remove-nth-node-from-end-of-list/)
这题要求一次遍历就得出结果,基本思路就是快慢指针,快指针先走n步, 然后快慢指针一起走,当快指针到头的时候,慢指针也就到了倒数第n个位置
需要注意的是删除的可能是第一个

class Solution {
public:
    ListNode* removeNthFromEnd(ListNode* head, int n) {
        if(!head|!head->next) return NULL;
        ListNode *slow=head, *fast=head;
        
        for(int i=0;i<n;i++){
            fast = fast->next;
        }
        if(!fast){
            return head -> next;    
        }
        
        while(fast->next){
            fast =fast->next;
            slow= slow->next;
        }
        slow->next = slow->next->next;
        return head;
        
    }
};

