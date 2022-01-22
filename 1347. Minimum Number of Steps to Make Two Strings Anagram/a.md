
# 1347. Minimum Number of Steps to Make Two Strings Anagram

<h4>Medium</h4>

You are given two strings of the same length s and t. In one step you can choose any character of t and replace it with another character.

Return the minimum number of steps to make t an anagram of s.

An Anagram of a string is a string that contains the same characters with a different (or the same) ordering.


 
<b>Example 1:</b>

<pre>Input: s = "bab", t = "aba"
Output: 1
Explanation: Replace the first 'a' in t with b, t = "bba" which is anagram of s.
</pre>

<b>Example 2:</b>
<pre>
Input: s = "leetcode", t = "practice"
Output: 5
Explanation: Replace 'p', 'r', 'a', 'i' and 'c' from t with proper characters to make t anagram of s.
 </pre>

<b>Example 3:</b>
<pre>
Input: s = "anagram", t = "mangaar"
Output: 0
Explanation: "anagram" and "mangaar" are anagrams. 
</pre>

<b>Constraints:</b>

<pre><li>1 <= s.length <= 5 * 104</li>
<li>s.length == t.length</li>
<li>s and t consist of lowercase English letters only.</pre>

<h2>Solution</h2>

```cpp
already occured in string "s" or not, if not then we have to change that character in order to make it anagram of string "s" (increase count ). 
class Solution {
public:
    int minSteps(string s, string t) {
        int arr[26]={0};
        int count=0;
        
        for(int i=0; i<s.length(); i++)
            arr[s[i]-'a']++;
        for(int i=0; i<t.length(); i++)
        {
            if(arr[t[i]-'a']>0)
                arr[t[i]-'a']--;
            else
                count++;
        }
        return count;
    }
};
```
<code>string</code> <code>array</code>

