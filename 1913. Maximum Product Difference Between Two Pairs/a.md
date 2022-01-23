

# 1913. Maximum Product Difference Between Two Pairs
Easy
The product difference between two pairs  <code>(a, b) and (c, d)</code> is defined as <code>(a * b) - (c * d)</code>.

For example, the product difference between  <code>(5, 6) and (2, 7) is (5 * 6) - (2 * 7) = 16</code>.
Given an integer array nums, choose four distinct indices w, x, y, and z such that the product difference between pairs (nums[w], nums[x]) and (nums[y], nums[z]) is maximized.

Return the maximum such product difference.

 

<b>Example 1:</b>

<pre>Input: nums = [5,6,2,7,4]
Output: 34
Explanation: We can choose indices 1 and 3 for the first pair (6, 7) and indices 2 and 4 for the second pair (2, 4).
The product difference is (6 * 7) - (2 * 4) = 34.
</pre>

<b>Example 2:</b>
<pre>
Input: nums = [4,2,5,9,7,4,8]
Output: 64
Explanation: We can choose indices 3 and 6 for the first pair (9, 8) and indices 1 and 5 for the second pair (2, 4).
The product difference is (9 * 8) - (2 * 4) = 64.
 </pre>


<b>Constraints:</b>

<pre> <li>4 <= nums.length <= 104</li>
<li>1 <= nums[i] <= 104</li> </pre>

<h2>Solution</h2>

```cpp
The logic is simple we have to find maximum difference between product , so sort the array and return the difference between 
( Largest * Second Largest ) - ( Smallest * Second Smallest )
class Solution {
public:
    int maxProductDifference(vector<int>& nums) {
        sort(nums.begin(),nums.end());
        
        int n=nums.size();
        
         return nums[n-1]*nums[n-2] - nums[0]*nums[1];
    }
};

Use Sort function sort()  //  Intro sort ( combination of Quick, Insertion, Heap Sort )
```
<code>sorting</code> <code>array</code>

