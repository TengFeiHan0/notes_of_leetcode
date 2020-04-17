[三数之和](https://leetcode-cn.com/problems/3sum/)
这题其实不算很难,因为只要做过两数之和的话, 解题思路很容易想到,比较头疼的点在于题目限制了不能冲副,这样的话,就需要多加考虑了. 
```c++
class Solution {
public:
    vector<vector<int> > threeSum(vector<int>& nums) {
       
        vector<vector<int>> ans;
        if(nums.empty()|| nums.size() <=2)
            return ans;
        
        vector<int> vtemp;
        sort(nums.begin(), nums.end());
        for(int i=0; i<nums.size()-2;i++){
           if(i==0 || (i>0 && nums[i]!= nums[i-1])){
               int p1= i+1, p2=nums.size()-1;
               while(p1 < p2){
                   if(nums[p1] + nums[p2]< -nums[i]){
                       p1++;
                   }
                   else if(nums[p1] + nums[p2] == -nums[i]){
                        if(p1 == i+1){
                            vector<int > vtemp{nums[i], nums[p1], nums[p2]};
                            ans.push_back(vtemp);
                            vtemp.clear();

                        }else if(nums[p1] != nums[p1-1]){
                            vector<int > vtemp{nums[i], nums[p1], nums[p2]};
                            ans.push_back(vtemp);
                            vtemp.clear();

                        }
                        p1++,p2--;
                    }
                    else{
                        p2--;
                    }
               }
           }
               
       
        }
         return ans;
    }

};
``` 
