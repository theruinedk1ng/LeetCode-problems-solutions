1813. Sentence Similarity III


PYTHON SOLUTION #1

```
class Solution:
    def areSentencesSimilar(self, sentence1: str, sentence2: str) -> bool:

        #split the sentences in words
        sentence1 = sentence1.split()
        sentence2 = sentence2.split()


        prefix = 0
        suffix = 0

        #check from the start for prefixes
        for i in range(min(len(sentence1), len(sentence2))):
            if sentence1[i] == sentence2[i]:
                prefix += 1
            else:
                break
        
        #check from the end for suffixes
        while suffix < len(sentence1) - prefix and suffix < len(sentence2) - prefix and sentence1[-1-suffix] == sentence2[-1-suffix]:

            suffix += 1
            
        #if the sum of counts of prefixes and suffixes are equal to the minimum length of a sentence return True else return False
        return prefix + suffix == min(len(sentence1), len(sentence2))
        


```

PTYTHON SOLUTION #2

```
class Solution:
    def areSentencesSimilar(self, sentence1: str, sentence2: str) -> bool:
        # Split the sentences into words
        words1 = sentence1.split()
        words2 = sentence2.split()

        # Ensure words1 is the longer sentence
        if len(words1) < len(words2):
            words1, words2 = words2, words1
        
        start, end = 0, 0
        n1, n2 = len(words1), len(words2)
        
        # Compare from the start
        while start < n2 and words1[start] == words2[start]:
            start += 1
        
        # Compare from the end
        while end < n2 and words1[n1 - end - 1] == words2[n2 - end - 1]:
            end += 1
        
        # Check if the remaining unmatched part is in the middle
        return start + end >= n2
```
