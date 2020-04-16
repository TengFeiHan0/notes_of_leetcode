[合并两个有序链表](https://leetcode-cn.com/problems/merge-two-sorted-lists/)
notes: 这题其实很简单,一点小提醒就是当其中一个链表到头的时候,别忘了立刻切换到下一个链表
```
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        
       ListNode* head = new ListNode(0);
       ListNode* curhead = head;
       while(l1 && l2){
           if(l1->val < l2->val){
               curhead->next = l1;
               curhead = curhead->next;
               l1 = l1->next;
           }
           else{
               curhead->next = l2;
               curhead = curhead->next;
               l2 = l2->next;
           }
       }
       if(!l1){
           curhead->next = l2;
       }
       else{
           curhead->next = l1;
       }
       return head->next;
        
    }
};
```
