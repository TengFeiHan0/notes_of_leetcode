 
 
 ```
class Solution {
public:
    string decodeString(string s) {
        string res;
        stack<pair<int, string>> stk;
        int count =0;
        for(auto &c: s){
            if(isdigit(c)){//是否是数字
                count = count*10 + c- '0';
            }
            else if(c == '['){//左边边框
                stk.push({count, res});//入栈
                count =0;//归零
                res = "";

            }
            else if(c == ']'){//右边边框
                auto p =stk.top();//取出一个
                stk.pop();
                string tmp =res;//copy对应的次数
                for(int i=1; i<p.first; i++){
                    res +=tmp;
                }
                res = p.second +res;//合到一起

            }
            else{
                res +=c;
            }
        }
        return res;


    }
};
 ```
