# leet-day26

# Increment Large Integer

## Problem Description

You are given a large integer represented as an integer array `digits`, where each `digits[i]` is the ith digit of the integer. The digits are ordered from most significant to least significant in left-to-right order. The large integer does not contain any leading 0's.

Your task is to increment the large integer by one and return the resulting array of digits.

## Examples

### Example 1

Input: `digits = [1,2,3]`
Output: `[1,2,4]`
Explanation: The array represents the integer 123. Incrementing by one gives 123 + 1 = 124. Thus, the result should be `[1,2,4]`.

### Example 2

Input: `digits = [4,3,2,1]`
Output: `[4,3,2,2]`
Explanation: The array represents the integer 4321. Incrementing by one gives 4321 + 1 = 4322. Thus, the result should be `[4,3,2,2]`.

### Example 3

Input: `digits = [9]`
Output: `[1,0]`
Explanation: The array represents the integer 9. Incrementing by one gives 9 + 1 = 10. Thus, the result should be `[1,0]`.

## Constraints

- 1 <= digits.length <= 100
- 0 <= digits[i] <= 9
- digits does not contain any leading 0's.

## Approach and Code

```cpp
class Solution {
public:
    vector<int> plusOne(vector<int>& digits) {
        int n = digits.size();
        
        // Iterate from the least significant digit to the most significant digit
        for (int i = n - 1; i >= 0; i--) {
            if (digits[i] < 9) {
                // If the current digit is less than 9, simply increment it and return
                digits[i]++;
                return digits;
            } else {
                // If the current digit is 9, set it to 0 and carry over to the next digit
                digits[i] = 0;
            }
        }
        
        // If all digits were 9, add an extra digit at the beginning with a value of 1
        digits.insert(digits.begin(), 1);
        return digits;
    }
};
```

## Complexity Analysis

- Time complexity: O(n), where n is the length of the `digits` array.
- Space complexity: O(1), as we are using a constant amount of extra space.
