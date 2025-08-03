Transform a string into a zigzag pattern on a given number of rows and return it as a single string, read row by row.

## 🧩 Problem Statement
Given:

A string s

An integer numRows

You must arrange the characters of s in a zigzag across numRows, then concatenate the characters row by row.

## 🧪 Example
Input: s = "PAYPALISHIRING", numRows = 3

Zigzag Pattern:

P   A   H   N  
A P L S I I G  
Y   I   R  

Output: "PAHNAPLSIIGYIR"

## 🧠 Intuition
Instead of drawing out a 2D grid, simulate row traversal by:

Moving vertically down the rows

Reversing direction when you reach the bottom or top

Tracking characters in each row using an array of strings


## 💻 Solution (Python)
python
class Solution(object):
    def convert(self, s, numRows):
        if numRows == 1 or numRows >= len(s):
            return s

        rows = [''] * numRows
        curr_row = 0
        going_down = False

        for char in s:
            rows[curr_row] += char
            if curr_row == 0 or curr_row == numRows - 1:
                going_down = not going_down
            curr_row += 1 if going_down else -1

        return ''.join(rows)
        
## 📈 Time & Space Complexity
Time: O(n), where n is the length of s

Space: O(n), storing characters in intermediate row strings

## ✅ Submission Details
Runtime: 14 ms — Beats 63.56% of Python submissions

Memory: 12.60 MB — Beats 55.01%

📝 Submitted on: Aug 03, 2025 🔖 LeetCode Submissionmitted on: Aug 03, 2025 🔖 LeetCode Submission
