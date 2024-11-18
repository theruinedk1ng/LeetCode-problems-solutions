1652. Defuse the Bomb
https://leetcode.com/problems/defuse-the-bomb/description/?envType=daily-question&envId=2024-11-18

PYTHON SOLUTION #1
```
class Solution:
    def decrypt(self, code: List[int], k: int) -> List[int]:
        
        extended = code + code
        extended = extended if k >= 0 else extended[::-1]

        for i in range(len(code)):
            code[i] = sum(extended[i + 1: i + abs(k) + 1])
        
        return code if k >= 0 else code[::-1]
```

PYTHON SOLUTION #2
```
class Solution:
    def decrypt(self, code: List[int], k: int) -> List[int]:
        
        res = []
        n = len(code)

        def func(x, cnt):
            s = 0 
            i = x + 1
            if i >= n:
                i = 0
            while i < n and cnt > 0:
                s += code[i]
                i += 1
                cnt -= 1
                if i >= n:
                    i = 0
            return s

        def fnc(x, cnt):

            s = 0 
            if x == 0:
                i = n - 1
            else:
                i = x - 1
            while i >= 0 and cnt < 0:
                s += code[i]
                print(code[i])
                i -= 1
                cnt += 1
                if i < 0:
                    i = n - 1
            return s

        if k == 0:

            return [0] * n
        
        if k > 0:

            for i in range(n):
                res.append(func(i, k))
        
        if k < 0:

            for i in range(n):
                res.append(fnc(i, k))

                
        return res
```
