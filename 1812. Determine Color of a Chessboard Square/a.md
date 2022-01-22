

# 1812. Determine Color of a Chessboard Square
Easy
You are given coordinates, a string that represents the <code>coordinates</code> of a square of the chessboard. Below is a chessboard for your reference.
 
![WhatsApp Image 2022-01-22 at 1 48 30 AM](https://user-images.githubusercontent.com/47034350/150633685-6acda857-37fa-4152-93bb-09ad5ad7a9a6.jpeg)

Return <code>true</code> if the square is white, and <code>false</code> if the square is black.

The coordinate will always represent a valid chessboard square. The coordinate will always have the letter first, and the number second.

<b>Example 1:</b>

<pre>Input: coordinates = "a1"
Output: false
Explanation: From the chessboard above, the square with coordinates "a1" is black, so return false.
</pre>

<b>Example 2:</b>
<pre>Input: coordinates = "h3"
Output: true
Explanation: From the chessboard above, the square with coordinates "h3" is white, so return true.
 </pre>

<b>Example 3:</b>
<pre>
Input: coordinates = "c7"
Output: false
</pre>

<b>Constraints:</b>

<pre><li>coordinates.length == 2</li>
<li>'a' <= coordinates[0] <= 'h'</li>
<li>'1' <= coordinates[1] <= '8'</li></pre>

<h2>Solution</h2>

```cpp
This question is based on observation, nothing else. If you are good at observation then you are good to go to code solution to this problem.
class Solution {
public:
    bool squareIsWhite(string str) {
        if(str[0]=='a' || str[0]=='c' || str[0]=='e' || str[0]=='g'){
            if(((str[1]-'0')&1)==0)
                return true;
            else
                return false;
        }
        if(str[0]=='b' || str[0]=='d' || str[0]=='f' || str[0]=='h'){
            if(((str[1]-'0')&1)==0)
                return false;
            else
                return true;
        }
        return true;
    }
};
```

