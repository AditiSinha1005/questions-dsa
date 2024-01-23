
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

# [Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)

## approach-> 
Quite simple code solved using maps


## code
```cpp
int removeDuplicates(vector<int>& nums) {
        map<int,int>m;
        for(int i=0;i<nums.size();i++)
        {
            m[nums[i]]++;
        }
        int count=0;
        int p=0;
        for(auto i:m)
        {
        count++;
        nums[p]=i.first;
        p++;
        }
       
        return count;
    }
```

