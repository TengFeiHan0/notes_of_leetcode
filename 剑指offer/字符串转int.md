
 这题最主要的难点就是复杂，需要考虑很多情况
 ```
class Solution {
public:
    int strToInt(string str) {
        if(str.empty())
           return 0;//是否为空
        int i=0;
        long res =0;
        bool negative = false;
        
        while(str[i]== ' ') i++;//剔除前面的空格

        if(str[i]== '-'){//判断正负

            negative = true;
            i++;
        }
        else if(str[i]=='+'){
            i++;
        }
        for(; i<str.size();i++){

            if(str[i]>='0'&&str[i]<='9'){//判断是否是数字，并且生成int
                
                res = res*10 +(str[i]-'0');
                if(res > INT_MAX && negative) return INT_MIN;//限制范围
                if(res > INT_MAX && !negative) return INT_MAX;
            }
            else
                break;
            
        }

        return negative? -res:res;
    }
};
 ```
