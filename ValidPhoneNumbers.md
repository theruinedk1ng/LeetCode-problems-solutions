193. Valid Phone Numbers
https://leetcode.com/problems/valid-phone-numbers/

BASH SOLUTION:

 ``` grep '^\([0-9]\{3\}-\|([0-9]\{3\}) \)[0-9]\{3\}-[0-9]\{4\}$' file.txt ```

\{3\} matches exactly three digits.
\{4\} matches exactly four digits.
[0-9]\{3\} three digits from 0 to 9.
same with [0-9]\{4\}

