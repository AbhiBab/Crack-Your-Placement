# [Chocolate Distribution Problem](https://www.geeksforgeeks.org/problems/chocolate-distribution-problem3825/1)

Given an array `A[ ]` of positive integers of size `N`, where each value represents the number of chocolates in a packet. Each packet can have a variable number of chocolates. There are `M` students, the task is to distribute chocolate packets among `M` students such that `:`
`1.` Each student gets exactly one packet.
`2.` The difference between maximum number of chocolates given to a student and minimum number of chocolates given to a student is minimum.

### Example

**Input:** `N = 8, M = 5, A = {3, 4, 1, 9, 56, 7, 9, 12}`  
**Output:** `6` 
**Explanation:** The minimum difference between maximum chocolates and minimum chocolates is `9 - 3 = 6` by choosing following `M` packets :`{3, 4, 9, 7, 9}`.

## Intuition

We simply sort the array and iterate it in `'M'` sized subarray and find the `difference` of `(max number)` and `(min number)` and store minimum difference among all the `M` subarray slides.


## Code

```C++
class Solution {
public:
   long long findMinDiff(vector<long long> a, long long n, long long m){
    sort(a.begin(),a.end());
    long long ans=INT_MAX;
    for(long long i=0; i+m-1<n; i++){
        long long dif=a[i+m-1]-a[i];
        ans=min(dif,ans);
    }
    return ans;
    
    }
};
```

## Complexity

- **Time Complexity:** O(N)  
  We iterate through the array once, where `N` is the length of the array.

- **Space Complexity:** O(1)  
We are using constant extra space.

---
