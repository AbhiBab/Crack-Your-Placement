# [Two Sum](https://leetcode.com/problems/two-sum/description/)

Given an array of integers `nums` and an integer target, return indices of the two numbers such that they add up to target.

### Example

**Input:** `nums = [2, 7, 11, 15], target = 9`  
**Output:** `[0, 1]` 
**Explanation:** Because `nums[0] + nums[1] == 9`, we return `[0, 1]`. 

## Intuition

Use HashMap to keep numbers and their indices.


## Code

```C++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int,int> mp;
        for(int i=0;  i<nums.size(); i++){
            if(mp.find(target-nums[i])!=mp.end())
                return {i,mp[target-nums[i]]};
            mp[nums[i]]=i;
        }
        return {-1,-1};
    }
};
```

## Complexity

- **Time Complexity:** O(N)  
  We iterate through the array once, where `N` is the length of the array.

- **Space Complexity:** O(N)  
  We use Hashmap for storing elements and their indices.

---
