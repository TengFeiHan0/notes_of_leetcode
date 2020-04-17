[删除排序中重复的项](https://leetcode-cn.com/problems/remove-duplicates-from-sorted-array/),这题本身看上去特别简单,更别提已经是排好顺序的了,重点是如果要求原地输出,不占用额外空间,这样以来,就有点棘手了,我在leetcode评论区发现的解法很棒,特地分享一下单指针,代码一看就懂,容易理解但是不容易想
``` c++
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        
        if(nums.size()==0)    return 0;

        int i=0;   //i做指针，记录需要替换元素的位置 
        for(int n:nums)
        {
            if(n!=nums[i])
            nums[++i]=n;
        }

        return i+1;
    }
};
``` 
双指针, 这个是比较容易想到的解法
