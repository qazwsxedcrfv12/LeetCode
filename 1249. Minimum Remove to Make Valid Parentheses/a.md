
# 1249. Minimum Remove to Make Valid Parentheses
<code>Medium</code>

Given a string s of '(' , ')' and lowercase English characters.

Your task is to remove the minimum number of parentheses ( '(' or ')', in any positions ) so that the resulting parentheses string is valid and return any valid string.

Formally, a parentheses string is valid if and only if:

It is the empty string, contains only lowercase characters, or
It can be written as AB (A concatenated with B), where A and B are valid strings, or
It can be written as (A), where A is a valid string.

 

<b>Example 1:</b>

<pre>Input: s = "lee(t(c)o)de)"
Output: "lee(t(c)o)de"
Explanation: "lee(t(co)de)" , "lee(t(c)ode)" would also be accepted.
</pre>

<b>Example 2:
<pre>
Input: s = "a)b(c)d"
Output: "ab(c)d"
 </pre>
 
  <b>Example 3:</b>

<pre>
Input: s = "))(("
Output: ""
Explanation: An empty string is also valid.
</pre>

<b>Constraints:</b>

<pre> <li>1 <= s.length <= 105
<li>s[i] is either'(' , ')', or lowercase English letter. </pre>

<h2>Solution</h2>

 <pre>The question is simply a use case of "STACK" Datastructure.
The logic to this problem is storing all  '(' or ')' characters in stack which are violating valid Parentheses and their index no. Now Traverse
the string and check if current character is present in stack , pop it. Otherwise add the character to resultant string.
</pre>
  
```cpp
class Solution {
public:
    string remove_str(string str, int l)
{
   stack<pair<char,int>>s;
   for(int i=0; i<l; i++)
   {
      if(str[i]=='(' || str[i]==')')
      {
         if(s.empty())
           s.push({str[i],i});
         else
         {
              if(str[i]==')' && s.top().first=='(')
                 s.pop();
              else
                 s.push({str[i],i});
         }
      }
   }
   
  string ss;
  for(int i=l-1; i>=0; i--)
  {
      if(s.size()>0 && i==s.top().second)
       s.pop();
      else
       ss+=str[i];
  }
  reverse(ss.begin(),ss.end());
 return ss;
}
    string minRemoveToMakeValid(string str) {
         int l=str.length();
         string s=remove_str(str,l);
        return s;
    }
};
```

