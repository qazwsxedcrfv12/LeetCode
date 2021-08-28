# Reduce Array Size to The Half 
Medium

You are given an integer array <code>arr</code> . You can choose a set of integers and remove all the occurrences of these integers in the array.

Return the minimum size of the set so that at least half of the integers of the array are removed.

 

**Example 1:**

<pre>Input: arr = [3,3,3,3,5,5,5,2,2,7]
Output: 2
Explanation: Choosing {3,7} will make the new array [5,5,5,2,2] which has size 5 (i.e equal to half of the size of the old array).
Possible sets of size 2 are {3,5},{3,2},{5,2}.
Choosing set {2,7} is not possible as it will make the new array [3,3,3,3,5,5,5] which has size greater than half of the size of the old array.</pre>

<b>Example 2:</b>

<pre>Input: arr = [7,7,7,7,7,7]
Output: 1
Explanation: The only possible set you can choose is {7}. This will make the new array empty.</pre>

<b>Example 3:</b>

<pre>Input: arr = [1,9]
Output: 1</pre>

<b>Example 4:</b>

<pre>Input: arr = [1000,1000,3,7]
Output: 1</pre>

<b>Example 5:</b>

<pre>Input: arr = [1,2,3,4,5,6,7,8,9,10]
Output: 5</pre>
 

<b>Constraints:</b>

<pre>1 <= arr.length <= 105
arr.length is even.
1 <= arr[i] <= 105</pre>


<h1>Solution</h1>
<pre>
The approach of this solution is simple and easy to understand, So we can use unordered map in C++ and Hash Map in Java to store frequency of elements. 
Then store that frequency in Max Heap to sort it in decreasing order. Now run a loop on heap till its size becomes zero or size of vector reduces to half. 
In loop start decreasing the size of vector by substracting the heap top.
</pre>
<br>

```cpp
class Solution {
public:
    int reduce_to_half(vector<int>&v)
    {
         unordered_map<int,int>mp;  //Unordered map to store frequency of elements
          for(int i=0; i<v.size(); i++)
              mp[v[i]]++;
    
	priority_queue<int>q;       // Max heap to store frequency in decreasing order
	     for(auto it: mp)
             q.push(it.second);
     
	    int c=0,var;
        var=v.size();
         while(!q.empty() && var>v.size()/2)
         { 
		     var-=q.top(); 
			 c++;                                  // Count sets
			 q.pop();  
	    }
        return c;
    }
    int minSetSize(vector<int>& arr) {
        int count = reduce_to_half(arr);
        return count;
    }
}
```
