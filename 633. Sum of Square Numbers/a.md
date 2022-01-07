
# 633. Sum of Square Numbers
Medium

Given a non-negative integer c, decide whether there're two integers a and b such that a2 + b2 = c.



<b>Example 1:</b>

<pre>
Input: c = 5
Output: true
Explanation: 1 * 1 + 2 * 2 = 5
</pre>

<b>Example 2:</b>
<pre>
Input: c = 3
Output: false
 </pre>


<b>Constraints:</b>

<pre> <li>0 <= c <= 231 - 1</li>
 </pre>

<h2>Solution</h2>
<pre>The approach of this solution is to use Two Pointer Method to solve this type of problems. The Problem is simply the variation of " Two Sum Problem " . Initilize a with 0 and b with sqrt(c) . Now run a loop and check for a*a + b*b == c. If a*a + b*b ==c return true, if a*a + b*b > c do b -- else do a ++. Finally if no pair is found return false.

 Time Complexity : O(n) or O(sqrt(c))  n = no of elements between 0 and sqrt of c.
 Space Complexity : O(1)</pre>

```cpp
 
class Solution {
public:
    bool judgeSquareSum(int c) {
        long long a=0,b=sqrt(c);
        while(a<=b)
        {
            if((a*a+b*b)==c)
                return true;
            else if((a*a+b*b)>c)
                b--;
            else
                a++;
        }
        return false;
    }
};
```


