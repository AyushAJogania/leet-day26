# leet-day26

# Minimum Maximum Difference

## Problem Statement

You are given an array `nums` of distinct integers and an integer `p`. Your task is to find `p` pairs of indices from `nums` such that the maximum difference among all the pairs is minimized. Additionally, ensure that no index appears more than once among the `p` pairs.

The difference of a pair of elements at indices `i` and `j` is defined as the absolute value of `|nums[i] - nums[j]|`.

Your goal is to return the minimum maximum difference among all the `p` pairs. If no index appears more than once in the `p` pairs, you consider the maximum of an empty set to be zero.

## Example

Input:
```
nums = [10,1,2,7,1,3]
p = 2
```
Output:
```
1
```
Explanation:
- The first pair is formed from the indices 1 and 4, resulting in a difference of `|nums[1] - nums[4]| = |1 - 1| = 0`.
- The second pair is formed from the indices 2 and 5, resulting in a difference of `|nums[2] - nums[5]| = |2 - 1| = 1`.
- The maximum difference among the pairs is minimized to 1.

## Constraints

- 1 <= nums.length <= 10^5
- 0 <= nums[i] <= 10^9
- 0 <= p <= nums.length / 2

## Approach

To solve this problem efficiently, we can use a binary search approach. We first sort the `nums` array. Then, we perform a binary search on the possible range of the maximum difference.

1. Initialize `left` to 0 and `right` to the maximum possible difference between any two elements in the `nums` array.
2. While `left` is less than `right`, calculate `mid` as the average of `left` and `right`.
3. For each pair of adjacent elements in the sorted array, check if their difference is less than or equal to `mid`. If it is, increment the counter and skip the next element.
4. If the counter is greater than or equal to `p`, update `right` to `mid`. Otherwise, update `left` to `mid + 1`.
5. Return `left`, which represents the minimum maximum difference among all the `p` pairs.

## Complexity

- Time complexity: O(n * log(maxDiff)), where `maxDiff` is the maximum possible difference between any pair of elements in the `nums` array.
- Space complexity: O(1), as we are using a constant amount of extra space for variables.

This algorithm allows us to efficiently find the minimum maximum difference among `p` pairs of indices in the `nums` array.
