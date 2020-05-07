[从尾到头打印链表](https://leetcode-cn.com/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/)
该题有两种比较常见的办法，第一个是将所有的值存进数组里面，然后将数组翻转，第二种方法是单调栈，把所有的值放到栈上，根据栈的性质先进后出，输出结果刚好符合题目要求

class Solution {
public:
    vector<int> reversePrint(ListNode* head) {
        vector<int> res;
        stack<int> s;
        //入栈
        while(head){
            s.push(head->val);
            head = head->next;
        }
        //出栈
        while(!s.empty()){
            res.push_back(s.top());
            s.pop();
        }
        return res;
    }
};
