# [Move Zeroes](https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/)

Given an integer array `nums`, move all 0s to the end of it while maintaining the relative order of the non-zero elements.

### Example

**Input:** `nums = [0, 1, 0, 3, 12]`  
**Output:** `[1, 3, 12, 0, 0]`  

## Intuition

Move all non zero numbers to left place.

## Code

```C++
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int i=0;
        for(int j=0; j<nums.size(); j++){
            if(nums[j]!=0)
            {
                swap(nums[i],nums[j]);
                i++;
            }
        }
    }
};
```

## Complexity

- **Time Complexity:** O(n)  
  We iterate through the array once, where `n` is the length of the array.

- **Space Complexity:** O(1)  
  We use constant extra space as we modify the array in place.

---
