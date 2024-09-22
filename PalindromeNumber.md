
9. Palindrome Number

https://leetcode.com/problems/palindrome-number/description/


C++ SOLUTION

class Solution {
public:
    bool isPalindrome(int x) {
        
        long long int aux = x ;
        long long int rez = 0 ;
        while( aux > 0 )
        {
            rez = rez*10 + aux%10 ;
            aux /= 10 ;
        }   
        if( x == rez )
            return true ;
        return false ;
    }
};



PYTHON SOLUTION #1

class Solution:
    def isPalindrome(self, x: int) -> bool:

        pal = False
        aux = x 
        n = 0
        while aux > 0:
            n = n*10 + aux%10
            aux //= 10
        if n == x:
            pal = True
        return pal



PYTHON SOLUTION #2

class Solution:
    def isPalindrome(self, x: int) -> bool:

        pal = False
        s = str(x)
        n = s[::-1]
        if n == s:
            pal = True
        return pal



