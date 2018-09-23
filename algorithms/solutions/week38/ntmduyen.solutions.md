# Problem 2 - [Search a 2D Matrix II](https://leetcode.com/problems/search-a-2d-matrix-ii/description/)

```cpp
class Solution {
public:
    bool searchMatrix(vector<vector<int>>& matrix, int target) {
        int row = matrix.size();
        if (row == 0) {
            return false;
        }
        int col = matrix[0].size();
        int i = 0, j = col - 1;
        while (i < row && j >= 0) {
            if (target == matrix[i][j]) {
                return true;
            } else if (target > matrix[i][j]) {
                i++;
            } else {
                j--;
            }
        }
        return false;
    }
};
```
