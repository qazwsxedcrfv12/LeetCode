# 1299. Replace Elements with Greatest Element on Right Side
Easy

Given an array arr, replace every element in that array with the greatest element among the elements to its right, and replace the last element with -1.

After doing so, return the array.

 

<b>Example 1:</b>

<pre>Input: arr = [17,18,5,4,6,1]
Output: [18,6,6,6,1,-1]
Explanation: 
- index 0 --> the greatest element to the right of index 0 is index 1 (18).
- index 1 --> the greatest element to the right of index 1 is index 4 (6).
- index 2 --> the greatest element to the right of index 2 is index 4 (6).
- index 3 --> the greatest element to the right of index 3 is index 4 (6).
- index 4 --> the greatest element to the right of index 4 is index 5 (1).
- index 5 --> there are no elements to the right of index 5, so we put -1.
</pre>

<pre>Example 2:

Input: arr = [400]
Output: [-1]
Explanation: There are no elements to the right of index 0.</pre>
 

<b>Constraints:</b>

<pre>1 <= arr.length <= 104
1 <= arr[i] <= 105</pre>

<h2>Solution</h2>

```cpp

The question is just a variation of problem " Leaders in an array ". We just have to keep track of maximum element on right side of any element. 
Traverse the loop from last elelement. We know there is no element on right side of last element so put -1. And bang you solved the problem. We 
just need to identify the variation ( easy peasy ☺️)

class Solution {
public:
    vector<int> replaceElements(vector<int>& arr) {
        int n=arr.size();
        int ma=arr[n-1];
        arr[n-1]=-1;
        for(int i=n-2; i>=0; i--)
        {
            int c=ma;
               ma=max(arr[i],ma);
            arr[i]=c;
        }
        return arr;
    }
};
```
