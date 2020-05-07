斐波那契数列，动态规划的思想，很容易理解
```
class Solution {
public:
    int fib(int n) {
        if(n<2)
            return n;
        int a =0;
        int b= 1;
        int c =0;
        for(int i=1;i<n;++i){
            c=a+b;
            if(c >=1000000007){
                c-=1000000007;
            }
            a=b;
            b=c;
        }
        return c;
    }
};
```
