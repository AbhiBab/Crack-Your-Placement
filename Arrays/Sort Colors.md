# [Sort Colors](https://leetcode.com/problems/sort-colors/description/)

Given an array `nums` with `n` objects colored `red`, `white`, or `blue`, sort them in-place so that objects of the same color are adjacent, with the colors in the order `red`, `white`, and `blue`.

We will use the integers `0`, `1`, and `2` to represent the color red, white, and blue, respectively.

### Example

**Input:** `nums = [2,0,2,1,1,0]`  
**Output:** `[0,0,1,1,2,2]` 

## Intuition

Iterate through the array with three pointers: low, mid, and high. Swap elements to ensure all 0s are before low, all 2s are after high, and 1s are between low and high. Increment low and mid for 0s, only increment mid for 1s, and decrement high for 2s. 


## Code

```C++
class Solution {
public:
   void sortColors(vector<int>& nums) {
        int r=0,b=nums.size()-1;
        for(int i=0; i<=b; i++){
            if(nums[i]==0){
                swap(nums[i],nums[r]);
                r++;
            }
            else if(nums[i]==2){
                swap(nums[b],nums[i]);
                b--;
                i--;
            }
        }
    }
};
```

## Complexity

- **Time Complexity:** O(N)  
  We iterate through the array once, where `N` is the length of the array.

- **Space Complexity:** O(1)  
We are using constant extra space.

---
