[三数之和](https://leetcode-cn.com/problems/3sum/)
这题其实不算很难,因为只要做过两数之和的话, 解题思路很容易想到,比较头疼的点在于题目限制了不能冲副,这样的话,就需要多加考虑了. 
```c++
class Solution {
public:
    vector<vector<int> > threeSum(vector<int>& nums) {
        
        <vector<int>>res;
        sort(nums.begin(),nums.end());
        if(nums.empty()||nums.back()<0||nums.front()>0) return {};
        
        for(int k=0;k<nums.size();k++)
        {
            if(nums[k]>0) break;//某一位大于0
            if(k>0&&nums[k]==nums[k-1]) continue;
            int target=0-nums[k];
            int left=k+1, right=nums.size()-1;
            while(left<right)//双指针
            {
                if(nums[left]+nums[right]==target)
                {
                    res.push_back({nums[k],nums[left],nums[right]});
                
                while(left<right&&nums[left]==nums[left+1])++left;
                while(left<right&&nums[right]==nums[right-1])--right;
                
                ++left;--right;
                }
                else if(nums[left]+nums[right]<target) ++left;
                else
                    --right;
            }
            
        }
        
        return res;   
          
    }

};
``` 
