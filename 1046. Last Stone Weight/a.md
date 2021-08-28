# 1046. Last Stone Weight

Easy

<pre>You are given an array of integers stones where stones[i] is the weight of the ith stone.
We are playing a game with the stones. On each turn, we choose the heaviest two stones and smash them together. Suppose the heaviest two stones have weights x and y with x <= y. The result of this smash is:

If x == y, both stones are destroyed, and
If x != y, the stone of weight x is destroyed, and the stone of weight y has new weight y - x.
At the end of the game, there is at most one stone left.

Return the smallest possible weight of the left stone. If there are no stones left, return 0.
</pre>
 

<b>Example 1:</b>

<pre>Input: stones = [2,7,4,1,8,1]
Output: 1
Explanation: 
We combine 7 and 8 to get 1 so the array converts to [2,4,1,1,1] then,
we combine 2 and 4 to get 2 so the array converts to [2,1,1,1] then,
we combine 2 and 1 to get 1 so the array converts to [1,1,1] then,
we combine 1 and 1 to get 0 so the array converts to [1] then that's the value of the last stone.</pre>

<b>Example 2:</b>

<pre>Input: stones = [1]
Output: 1</pre>
 

<b>Constraints:</b>

<pre>1 <= stones.length <= 30
1 <= stones[i] <= 1000</pre>

# Solution
<pre>
The approach of this solution is to use Max Heap ( so that maximum element is always on top). If we do opeartion as given in problem statement Heap will heapify itself so that top element is always max.

* Insert all elements of array in Heap and run loop till heap size is greater than 1 and perform the operation. 
*  And finally return the Heap top. It will be the minimum element left 
</pre>
```cpp
class Solution {
public:
    int lastStoneWeight(vector<int>& arr) {
        priority_queue<int>q;     // Max Heap
   for(int i=0; i<arr.size(); i++)
     q.push(arr[i]);
   
   while(q.size()>1)
   {
      int c=q.top();   // First greatest
      q.pop();
      int d=q.top();  //Second greatest
      q.pop();
      c=c-d;           // Change greatest to ( greatest - second greatest )
       q.push(c);
   }
 return q.top();
    }
};
```
