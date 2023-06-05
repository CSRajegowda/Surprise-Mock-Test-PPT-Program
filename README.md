# Surprise-Mock-Test-PPT-Program 

Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.

Example 1:
Input: nums = [0,1,0,3,12]
Output: [1,3,12,0,0]

Example 2:
Input: nums = [0]
Output: [0]

Constraints:
a. 1 <= nums.length <= 10^4
b. -2^31 <= nums[i] <= 2^31 - 1

ANS 
class Solution:
     def moveZeroes(self, nums):
        n = len(nums)
        i = 0
        for j in range(n):
            if (nums[j] != 0):
                nums[i], nums[j] = nums[j], nums[i]
                i += 1
                
                
     Given a string s, find the first non-repeating character in it and return its index. If it does not exist, return -1.

Example 1:
Input: s = "leetcode"
Output: 0

Example 2:
Input: s = "loveleetcode"
Output: 2

Example 3:
Input: s = "aabb"
Output: -1

Constraints:
a. 1 <= s.length <= 10^5
b. s consists of only lowercase English letters.         

       class Solution:
    def firstUniqChar(self, s: str) -> int:
        
        s1 = [i for i in "".join(s)]

        d = {}
        for i in s1:
            if i not in d:
                d[i] = 1
            else:
                d[i] += 1
        
        L = []
        for key,val in d.items():
            if val == 1:
                L.append(key)

        if len(L) == 0:
            return -1 
        else:
            s1 = s1.index(L[0])
            return s1      
