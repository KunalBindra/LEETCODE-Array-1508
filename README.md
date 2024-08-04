# LEETCODE-Array-1508
**Understanding the Code:**

**Problem:**
* Given an array `nums` of length `n`, find the sum of all subarray sums in the range `[left, right]`.
* The subarray sums are sorted in ascending order.

**Solution Approach:**
1. **Generate all subarray sums:**
   * Create an array `arr` to store all subarray sums.
   * Iterate through the `nums` array:
     * For each element `nums[i]`, calculate the sum of all subarrays starting from `nums[i]`.
     * Add these sums to the `arr` array.
2. **Sort the array:** Sort the `arr` array in ascending order.
3. **Calculate the range sum:**
   * Iterate from `left - 1` to `right - 1` in the sorted `arr` array.
   * Add each element to `ans` and take modulo with `mod` to handle potential overflow.
4. **Return the final sum:** Return the calculated `ans`.

**Dry Run:**

Let's take an example:
```
nums = [1, 2, 3]
n = 3
left = 1
right = 3
```

**Step 1: Generate all subarray sums:**

```
arr = [1, 3, 6, 2, 5, 3]
```
Explanation:
* Subarrays starting from index 0: [1], [1, 2], [1, 2, 3]
* Subarrays starting from index 1: [2], [2, 3]
* Subarrays starting from index 2: [3]

**Step 2: Sort the array:**

```
arr = [1, 2, 3, 3, 5, 6]
```

**Step 3: Calculate the range sum:**

```
ans = 1 + 2 + 3 = 6
```

**Step 4: Return the final sum:**

```
return 6
```

**Time Complexity:** O(n^2 * log(n^2)) due to generating all subarray sums and sorting.
**Space Complexity:** O(n^2) for storing all subarray sums.
