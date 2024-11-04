3163. String Compression III
https://leetcode.com/problems/string-compression-iii/description/?envType=daily-question&envId=2024-11-04

PYTHON SOLUTION
```
class Solution:
    def compressedString(self, word: str) -> str:
        
        comp = ''

        if len(word) == 1:
            return '1' + word

        def f(word):
            prev = ''
            p = []
            for i in word:
                if i != prev and i not in p:
                    p.append(i)
                elif i != prev and i in p:
                    return False
                prev = i
            return True
        print(f(word))
        

        if f(word) is False:

            cnt = 1
            prev = word[0]
            for i in range(1, len(word)):
                if prev == word[i] and cnt < 9:
                    cnt += 1
                elif prev == word[i] and cnt >= 9:
                    while cnt > 9:
                        comp += '9' + prev
                        cnt -= 9
                    comp += str(cnt) + prev
                    cnt = 1
                elif prev != word[i] and cnt > 9:
                    while cnt > 9:
                        comp += '9' + prev
                        cnt -= 9
                    comp += str(cnt) + prev
                    cnt = 1
                elif prev != word[i] and cnt <= 9:
                    comp += str(cnt) + prev
                    cnt = 1

                
                prev = word[i]
            if cnt > 0:
                comp += str(cnt) + prev
            return comp



        d = Counter(list(word))

        prev = ''

        for i in range(len(word)):

            if word[i] != prev:
                while d[word[i]] > 9:
                    comp += '9' + word[i]
                    d[word[i]] -= 9
                comp += str(d[word[i]]) + word[i]  
            prev = word[i]
        
        
        return comp
```
