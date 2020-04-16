[无重复的最长字符串](https://leetcode-cn.com/problems/longest-substring-without-repeating-characters/)
这题的解决办不止一种,我用的是哈希表,其他的解法参考[这里](https://leetcode-cn.com/problems/longest-substring-without-repeating-characters/solution/wu-zhong-fu-zi-fu-de-zui-chang-zi-chuan-cshi-xian-/)
``` 


class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        if(s.empty())
            return 0;
        int left(0), right(0), res(0), length(0);
        unordered_map<char, int> m;
        while(right < s.size()){
            char c1 = s[right];
            if(m.find(c1) != m.end() && m[c1] >=left){
               left = m[c1] +1;
               length = right-left;
            }
            m[c1] = right;
            right++;
            length++;
            res = max(res, length);

        }
        return res;
        
    }
};
``` 
