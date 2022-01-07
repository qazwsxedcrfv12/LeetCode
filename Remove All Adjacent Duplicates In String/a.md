
# 1047. Remove All Adjacent Duplicates In String

Easy

<pre>You are given a string s consisting of lowercase English letters. A duplicate removal consists of choosing two adjacent and equal letters and removing them.

We repeatedly make duplicate removals on s until we no longer can.

Return the final string after all such duplicate removals have been made. It can be proven that the answer is unique.
</pre>
 

<b>Example 1:</b>

<pre>Input: s = "abbaca"
Output: "ca"
Explanation: 
For example, in "abbaca" we could remove "bb" since the letters are adjacent and equal, and this is the only possible move.  The result of this move is that the string is "aaca", of which only "aa" is possible, so the final string is "ca".</pre>

<b>Example 2:</b>

<pre>Input: s = "azxxzy"
Output: "ay"</pre>
 

<b>Constraints:</b>

<pre><li>1 <= s.length <= 105</li>
<li>s consists of lowercase English letters.</li></pre>

# Solution
<pre>
  The problem is simply a use case of "STACK" data structure.
  The logic of problem is simply push the character in stack if it is empty or stack top is not same. If stack top is same
  as the current character then pop the character from stack top. ( Easy Peasy ) :)
</pre>
```cpp
class Solution {
public:
    string remove_duplicate(string str, int l)
   {
          stack<char>s;
          for(int i=0; i<l; i++)
          {
              if(s.empty())
                  s.push(str[i]);                    // if stack is empty push the character in stack
              else
             {
                   if(s.top()==str[i])               // if current character is same as stack top pop it
                                  s.pop();
                   else
                      s.push(str[i]);
             }
          }
   
        string sout;
   while(!s.empty())
   {
         sout+=s.top();
          s.pop();
   } 
   
        reverse(sout.begin(),sout.end());
   
    return sout;
}
    string removeDuplicates(string str) {
        
        int l=str.length();
        string s=remove_duplicate(str,l);
    return s;
}
      
};
```
``` Stack is best DS ;) ```
