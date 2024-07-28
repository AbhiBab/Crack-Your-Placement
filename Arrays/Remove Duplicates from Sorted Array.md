# [Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/)

Given an integer array `nums` sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same. Return the number of unique elements in `nums`.

### Example

**Input:** `nums = [1, 1, 2, 3, 3]`  
**Output:** `3, nums = [1, 2, 3, _, _]`  
**Explanation:** The function should return `3`, with the first three elements of `nums` being `1`, `2`, and `3` respectively.

## Intuition

Since the array is sorted, all duplicates will be adjacent. We can use a two-pointer technique to efficiently remove duplicates. Pointer `i` tracks the position for the next unique element, while pointer `j` scans through the array to find these unique elements.

## Approach

1. **Initialization:**
   - Set pointer `i` to `0`, which will mark the position of the last unique element.

2. **Iterate Through the Array:**
   - Use pointer `j` starting from index `1` to scan through the array.
   - Compare `nums[j]` with `nums[i]`. If they are different, increment `i` and update `nums[i]` with `nums[j]`.

3. **Return the Result:**
   - After iterating through the array, return `i + 1` which will be the number of unique elements.

## Code

```C++
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        int n=nums.size(),i=0,j=1;
        while(j<n){
            if(nums[i]!=nums[j]){
                i++;
                swap(nums[i],nums[j]);
               
            }
            j++;
        }
        return i+1;
    }
};
```

## Complexity

- **Time Complexity:** O(N)  
  We iterate through the array once, where `N` is the length of the array.

- **Space Complexity:** O(1)  
  We use constant extra space as we modify the array in place.

---

***Follow my progress and join the challenge on my*** **[GitHub](https://github.com/AbhiBab/Crack-Your-Placement), [Leetcode](https://leetcode.com/problems/remove-duplicates-from-sorted-array/solutions/5549940/best-easy-solution/) *and* [LinkedIn](https://www.linkedin.com/in/abhishek1981agarwal/)** 

`Let's tackle these coding challenges together! 🚀
`
