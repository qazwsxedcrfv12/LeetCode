
# 1475. Final Prices With a Special Discount in a Shop
Easy
Given the array prices where prices[i] is the price of the ith item in a shop. There is a special discount for items in the shop, if you buy the ith item, then you will receive a discount equivalent to prices[j] where j is the minimum index such that j > i and prices[j] <= prices[i], otherwise, you will not receive any discount at all.

Return an array where the ith element is the final price you will pay for the ith item of the shop considering the special discount.

 

<b>Example 1:</b>

<pre>Input: prices = [8,4,6,2,3]
Output: [4,2,4,2,3]
Explanation: 
For item 0 with price[0]=8 you will receive a discount equivalent to prices[1]=4, therefore, the final price you will pay is 8 - 4 = 4. 
For item 1 with price[1]=4 you will receive a discount equivalent to prices[3]=2, therefore, the final price you will pay is 4 - 2 = 2. 
For item 2 with price[2]=6 you will receive a discount equivalent to prices[3]=2, therefore, the final price you will pay is 6 - 2 = 4. 
For items 3 and 4 you will not receive any discount at all.
</pre>

<b>Example 2:</b>
<pre>
Input: prices = [1,2,3,4,5]
Output: [1,2,3,4,5]
Explanation: In this case, for all items, you will not receive any discount at all.
 </pre>

<b>Example 3:</b>
<pre>
Input: prices = [10,1,1,6]
Output: [9,0,1,6]
</pre>

<b>Constraints:</b>

<pre> <li>1 <= prices.length <= 500</li>
<li>1 <= prices[i] <= 10^3 </pre>

<h2>Solution</h2>

```cpp
class Solution {
public:
   vector<int> find_discount(vector<int>arr)
   {
         stack<int>s;
         vector<int>v;
         int n=arr.size();
   
       for(int i=n-1; i>=0; i--){
          if(s.size()==0)
           v.push_back(arr[i]);
          else{
           while(s.size()>0 && s.top()>arr[i])
            s.pop();
            v.push_back(s.size()==0 ? arr[i] : arr[i]-s.top());
        }
         s.push(arr[i]);
      }
   reverse(v.begin(),v.end());
 return v;
}
    vector<int> finalPrices(vector<int>& arr) {
         vector<int>v=find_discount(arr);
        return v;
    }
};
```

