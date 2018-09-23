# Problem 1 - [Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/description/)

```cpp
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        vector<int> m_nums(m+n);
        int i = 0, j = 0, k = 0;
        while (i < m && j < n) {
            if (nums1[i] == nums2[j]) {
                m_nums[k++] = nums1[i++];
                m_nums[k++] = nums2[j++];
            } else if (nums1[i] < nums2[j]) {
                m_nums[k++] = nums1[i++];
            } else {
                m_nums[k++] = nums2[j++];
            }
        }
        while (i < m) {
            m_nums[k++] = nums1[i++];
        }
        while (j < n) {
            m_nums[k++] = nums2[j++];
        }
        nums1 = m_nums;
    }
};
```
