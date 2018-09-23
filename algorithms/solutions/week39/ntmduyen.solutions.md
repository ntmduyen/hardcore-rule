# Problem 1 - [Reverse Integer](https://leetcode.com/problems/reverse-integer/description/)

```cpp
class Solution {
public:
    int safe_add(int a, int b) {
        if (a > 0 && b > INT_MAX - a) {
            return INT_MAX;
        } else if (a < 0 && b < INT_MIN - a) {
            return INT_MIN;
        }
        return a + b;
    }

    int safe_mul(int a, int b) {
        int c = 0;
        while (b > 0) {
            c = safe_add(c, a);
            b--;
        }
        return c;
    }

    int reverse(int x) {
        int c = 0;
        while (x != 0) {
            c = safe_mul(c, 10);
            c = safe_add(c, x % 10);
            if (c >= INT_MAX || c <= INT_MIN) {
                return 0;
            }
            x = x / 10;
        }
        return c;
    }
};
```
