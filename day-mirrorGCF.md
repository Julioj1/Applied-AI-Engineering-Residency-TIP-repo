Problem: Running Sum of 1d Array

leetcode link: https://leetcode.com/problems/running-sum-of-1d-array/description/

Input: An array of integers nums

Output: An array where each element is the cumulative sum up to that index

Algorithm:

1. Loop through each element in nums
2. Add the current element to the previous running sum
3. Store the result in the output array
4. Return the output array

Python Solution:

```py
def running_sum(nums):
    def runningSum(self, nums: List[int]) -> List[int]:
        result = []
        total = 0
        for num in nums:
            total += num
            result.append(total)
        return result
```

Problem: Maximum Number of Vowels in a Substring of Given Length

leetcode link: https://leetcode.com/problems/maximum-number-of-vowels-in-a-substring-of-given-length/description/

Input: A string s and an integer k representing the substring length

Output: An integer representing the maximum number of vowels in any substring of length k

Algorithm:

1. Count the vowels in the first window of size k
2. Slide the window one character at a time
3. Add 1 if the new character entering the window is a vowel
4. Subtract 1 if the character leaving the window was a vowel
5. Track the maximum vowel count seen so far
6. Return the maximum

Python Solution:

```py
class Solution:
    def maxVowels(self, s: str, k: int) -> int:
        vowels = set('aeiou')

        # Count vowels in the first window
        current = sum(1 for c in s[:k] if c in vowels)
        max_vowels = current

        # Slide the window
        for i in range(k, len(s)):
            if s[i] in vowels:
                current += 1
            if s[i - k] in vowels:
                current -= 1
            max_vowels = max(max_vowels, current)

        return max_vowels
```
