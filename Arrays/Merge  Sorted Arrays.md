# [Merge Sorted Arrays](https://leetcode.com/problems/merge-sorted-array/description/)

You are given two integer arrays `nums1` and `nums2`, sorted in non-decreasing order, and two integers `m` and `n`, representing the number of elements in `nums1` and `nums2` respectively.

Merge `nums1` and `nums2` into a single array sorted in non-decreasing order.

### Example

**Input:** `nums1 = [1,2,3,0,0,0], m = 3, nums2 = [2,5,6], n = 3`  
**Output:** `[1,2,2,3,5,6]` 
**Explanation:**  The arrays we are merging are `[1,2,3]` and `[2,5,6]`.
The result of the merge is `[1,2,2,3,5,6]` with the underlined elements coming from `nums1`.


## Code

```C++
class Solution {
public:
 void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        vector<int> temp;
        int i=0,j=0;
        while(i<m&&j<n){
            if(nums1[i]<=nums2[j]){
                temp.push_back(nums1[i]);
                i++;
            }
            else
            {
                temp.push_back(nums2[j]);
                j++;
            }
        }
        while(i<m)
            temp.push_back(nums1[i++]);
        while(j<n)
            temp.push_back(nums2[j++]);
        nums1=temp;
    }
};
```

## Complexity

- **Time Complexity:** O(M+N)  
  We iterate through the array once, where `M+N` is the length of the array.

- **Space Complexity:** O(M+N)  
We are using `O(M+N)` extra space.

---
