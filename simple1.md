## Merge Sorted Array
# 问题分析：
利用nums1数组后的空余空间来插入nums2的元素同时进行排序,即进行nums1数组中元素与nums2数组中元素逐个比较然后根据条件判断插入位置
需要考虑nums2中元素多于nums1中元素情况以及其他特殊情况
# 编程实现：
```C++
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        int i=m-1,j=n-1;
        int k=m+n-1;
          while(i>=0&&j>=0)
          {
              if(nums1[i]<nums2[j])
              {
                  nums1[k--]=nums2[j--];
              }
             else
             {
                 nums1[k--]=nums1[i--];
             }
         }
        if(m==0)
        {
            while(j>=0)
            nums1[k--]=nums2[j--];
        }
        if(n==0)
        {
            while(i>=0)
            nums1[k--]=nums1[i--];
        }
        while(j>=0)
        {
             nums1[k--]=nums2[j--];
         }
     }
};
```
