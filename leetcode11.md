[盛水最多的容器](https://leetcode-cn.com/problems/container-with-most-water/)
这题其实就是直方图形成最大的矩形面积,用双指针的思想去做, 

```c++ 
class Solution {
public:
    int maxArea(vector<int>& height) {
        int left=0, right=height.size()-1;
        int res=0;
        while(left < right){
            res = max(res, (right -left) *min(height[right], height[left]));
            if(height[left] > height[right]) --right;
            else ++left;
        }

        return res;
        
    }
};
``` 
