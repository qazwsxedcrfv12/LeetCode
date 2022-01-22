

# 2119. A Number After a Double Reversal
Easy
Reversing an integer means to reverse all its digits.

<li>For example, reversing 2021 gives 1202. Reversing 12300 gives 321 <b>as the leading zeros are not retained.</b>
Given an integer num, reverse num to get reversed1, then reverse reversed1 to get reversed2. Return true if reversed2 equals num. Otherwise return false.


 

<b>Example 1:</b>

<pre>Input: num = 526
Output: true
Explanation: Reverse num to get 625, then reverse 625 to get 526, which equals num.
</pre>

<b>Example 2:</b>
<pre>
Input: num = 1800
Output: false
Explanation: Reverse num to get 81, then reverse 81 to get 18, which does not equal num.
 </pre>

<b>Example 3:</b>
<pre>
Input: num = 0
Output: true
Explanation: Reverse num to get 0, then reverse 0 to get 0, which equals num.
</pre>

<b>Constraints:</b>

<pre> <li>0 <= num <= 106</li>
</pre>

<h2>Solution</h2>

```cpp
The logic to this problem is simple and easy, first check certain condition to prevent corner cases and save time.
1). If no is ' 0 ' return true, 
2). If end digit of number before and after first reversal is 0 return false, becoz 0 is terminated as per question demand.

And if not, then do simple reversal of no and check if after 2 reversal it matches with original no.
class Solution {
public:
    bool isSameAfterReversals(int num) {
        if(num==0)
            return true;
        if(num%10==0)
            return false;
        int rev1=0,rev2=0;
        int s1=num;
        
        while(s1!=0){                                              // First Reversal
            rev1=rev1*10+s1%10;
            s1/=10;
        }
       
        if(rev1%10==0)                                         // If last digit is 0 return false
            return false;
        
        while(rev1!=0){                                        // Second Reversal
            rev2=rev2*10+rev1%10;
            rev1/=10;
        }
        
        return rev2==num;
    }
};

Easy peasy, Happy Coding :)
```

