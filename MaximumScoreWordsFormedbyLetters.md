1255. Maximum Score Words Formed by Letters
https://leetcode.com/problems/maximum-score-words-formed-by-letters/description/

PYTHON SOLUTION:

```
class Solution:
    def maxScoreWords(self, words: List[str], letters: List[str], score: List[int]) -> int:
        
        letter_score = {chr(97 + i): score[i] for i in range(26)}
    
        available_count = Counter(letters)

        def word_score(word, letter_count):
            word_count = Counter(word)
            word_total_score = 0
            
          
            for char in word_count:
                if word_count[char] > letter_count[char]:
                    return 0 
                word_total_score += word_count[char] * letter_score[char]
            
            return word_total_score
        

        def backtrack(index, current_count):
            if index == len(words):
                return 0
            
        
            skip_word = backtrack(index + 1, current_count.copy())
          
            current_word = words[index]
            word_value = word_score(current_word, current_count)
            
            if word_value > 0:
                
                for char in current_word:
                    current_count[char] -= 1
                take_word = word_value + backtrack(index + 1, current_count)
            else:
                take_word = 0
            
            
            return max(skip_word, take_word)
        
  
        return backtrack(0, available_count)
```
