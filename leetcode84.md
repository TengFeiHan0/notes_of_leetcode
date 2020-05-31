int largestRectangleArea(vector<int>& heights) {
     heights.push_back(0);
     stack<int> stk;
     int maxArea = 0;
     for(int i = 0;i<heights.size();i++)
     {
         while(!stk.empty() && heights[i]<heights[stk.top()])
         {
             int top= stk.top();
             stk.pop();
             maxArea = max(maxArea,heights[top]*(stk.empty()? i:(i - stk.top() -1)));
         }
         stk.push(i);
     }
     return maxArea;
}
[参考博客1](https://blog.csdn.net/Zolewit/article/details/88863970)
[参考博客2](https://blog.csdn.net/qq_17550379/article/details/85093224)
