1961. Check If String Is a Prefix of Array
https://leetcode.com/problems/check-if-string-is-a-prefix-of-array/description/


PYTHON SOLUTION:

class Solution:
    def isPrefixString(self, s: str, words: List[str]) -> bool:
        
        i = 0 
        a = ''

        while len(a) < len(s) and i < len(words):

            a += words[i]

            i += 1
        
        if s == a:
            return True
        return False


C++ SOLUTION:


class Solution {
public:
    bool isPrefixString(string s, vector<string>& words) {
        string a = "";
        int i = 0;
        while(a.length() < s.length() && i < words.size())
        {
            a += words[i];
            i++;
        }
        if(a == s)
            return true;
        return false;
    }
};
