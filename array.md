
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
# [Max Consecutive Ones](https://leetcode.com/problems/max-consecutive-ones/description/)

## approach-> 
Normal approach solved using map and normal iteration 
Time Complexity : O(n)


## code
```cpp
   int findMaxConsecutiveOnes(vector<int>& nums) {
        int max=INT_MIN;
        int count=0;
        map<int,int>m;
        for(int i=0;i<nums.size();i++)
        m[nums[i]]++;
        for(auto i:m)
        {
            if(i.first==0 && i.second==nums.size())
            return 0;
        }
        for(int i=0;i<nums.size()-1;i++)
        {
            if(nums[i]==nums[i+1] && nums[i]==1)
            count++;
            if(count>0 && nums[i]!=nums[i+1])
            {
                if(max<count)
                {
                max=count;
                }
                count=0;
            }
        }
        if(max<count)
        {
            max=count;
        }
        return max+1;
    }
```
# [152. Maximum Product Subarray](https://leetcode.com/problems/maximum-product-subarray/description/)

## approach-> 
Approach of this question is similar to that of kadane's algorithm we start from the start and
take note of the max value and again do the same from the reverse side and then find the max value of product
Time Complexity: O(n)


## code
```cpp
class Solution {
public:
    int maxProduct(vector<int>& nums) {
        int maxx = INT_MIN;
        int prod=1;

        for(int i=0;i<nums.size();i++)
        {
          prod*=nums[i];
          maxx=max(prod,maxx);
          if(prod==0)
           prod=1;
        }
        prod=1;
        for(int i=nums.size()-1;i>=0;i--)
        {
          prod*=nums[i];

          maxx=max(prod,maxx);
          if(prod==0)
           prod=1;
        }
        return maxx;
    }
};
```