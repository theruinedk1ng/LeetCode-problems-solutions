2416. Sum of Prefix Scores of Strings
https://leetcode.com/problems/sum-of-prefix-scores-of-strings/description/?envType=daily-question&envId=2024-09-25


PYTHON SOLUTION USING TRIENODE:
```
from collections import defaultdict
from typing import List

class TrieNode:
    def __init__(self):
        self.children = defaultdict(TrieNode)
        self.score = 0  

class Solution:
    def sumPrefixScores(self, words: List[str]) -> List[int]:
        
        root = TrieNode()
        
        for word in words:
            node = root
            for letter in word:
                node = node.children[letter]
                node.score += 1  

        
        results = []
        for word in words:
            node = root
            total_score = 0
            for letter in word:
                node = node.children[letter]
                total_score += node.score  
            results.append(total_score)

        return results
```




PYTHON SOLUTION (TLE ERROR):

```
class Solution:
    def sumPrefixScores(self, words: List[str]) -> List[int]:

        rez = []

        if len(words) == 1:

            rez.append(len(words[0]))
        else:

            
            for i in range(len(words)):

                cnt = len(words[i])
                l = []
                aux = ''
                for let in words[i]:
                    aux += let
                    l.append(aux)

                for j in range(len(words)):
                    if j != i:
                        aux1 = ''
                        for x in words[j]:
                            aux1 += x
                            if aux1 in l:
                                cnt += 1
                rez.append(cnt)



                
                

        return rez
```
