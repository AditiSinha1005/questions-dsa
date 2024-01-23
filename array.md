
# [1752. Check if Array Is Sorted and Rotated](https://leetcode.com/problems/check-if-array-is-sorted-and-rotated/description/)

## approach-> 
the approach of the following question is simple and easy
- Approach:
if array is sorted and rotated then, there is only 1 break point where (nums[x] > nums[x+1]),
if array is only sorted then, there is 0 break point ..; and one more thing that is
important is that we will check if last element is greater than then the first element or not\


Time complexity: O(N)
Space complexity: O(1)


## code
```cpp
 bool check(vector<int>& nums) {
        int count=0;
        for(int i=0;i<nums.size();i++)
        {
            if(nums[i]>nums[(i+1)%nums.size()])
            count++;
        }
        if(count<=1)
        return true;
        else
        return false;
    }
```


