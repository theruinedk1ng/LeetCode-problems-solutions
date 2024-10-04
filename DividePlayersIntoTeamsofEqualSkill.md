2491. Divide Players Into Teams of Equal Skill
https://leetcode.com/problems/divide-players-into-teams-of-equal-skill/description/?envType=daily-question&envId=2024-10-04


PYTHON SOLUTION

```
class Solution:
    def dividePlayers(self, skill: List[int]) -> int:

        rez = 0 

        if len(skill) == 2:
            return skill[0]*skill[1]
        
        pos = True
        k = len(skill)//2
        skill.sort()

        p1 = 1
        p2 = len(skill) - 2

        prev = skill[0] + skill[len(skill) - 1]
        rez = skill[0] * skill[len(skill) - 1 ]

        while p1 < p2:

            if skill[p1] + skill[p2] != prev:
                pos = False
                rez = -1
                break
            else:   
                prev = skill[p1] + skill[p2]
                rez += skill[p1] * skill[p2]
                p1 += 1
                p2 -= 1
        
        return rez

```
