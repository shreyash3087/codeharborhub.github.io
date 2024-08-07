---
id: find-the-missing-number
title: Find the Missing Number Problem 
sidebar_label: Find-The-Missing-Number
tags:
  - Intermediate
  - Array
  - Mathematical
  - GeeksforGeeks
  - CPP
  - Python
  - DSA
description: "This tutorial covers the solution to the Find the Missing Number problem from the GeeksforGeeks."
---
## Problem Description

Given an array containing `n-1` distinct numbers taken from 1 to `n`, find the one number that is missing from the array.

## Examples

**Example 1:**

```
Input: array = [3, 1, 4]
Output: 2
Explanation: The missing number is 2.
```

**Example 2:**

```
Input: array = [5, 3, 1, 2]
Output: 4
Explanation: The missing number is 4.
```

## Your Task

You don't need to read input or print anything. Your task is to complete the function `missingNumber()` which takes the size `n` of the range and the array `arr` as inputs and returns the missing number.

Expected Time Complexity: $O(n)$

Expected Auxiliary Space: $O(1)$

## Constraints

* `2 ≤ n ≤ 10^6`
* `1 ≤ array[i] ≤ n`
* All elements of the array are distinct.

## Problem Explanation

The problem is to find the missing number from an array of `n-1` elements which contains distinct numbers from 1 to `n`. The missing number is the one number that is not present in the array.

## Code Implementation

<Tabs>
  <TabItem value="Python" label="Python" default>
  <SolutionAuthor name="@Ishitamukherjee2004"/>

  ```py
  class Solution:
      def missingNumber(self, n, arr):
          # Calculate the expected sum of the first n natural numbers
          total_sum = n * (n + 1) // 2
          
          # Calculate the sum of the elements in the array
          arr_sum = sum(arr)
          
          # The missing number is the difference between the expected sum and the array sum
          return total_sum - arr_sum

  # Example usage
  if __name__ == "__main__":
      solution = Solution()
      print(solution.missingNumber(4, [3, 1, 4]))  # Expected output: 2
      print(solution.missingNumber(5, [5, 3, 1, 2]))  # Expected output: 4
  ```

  </TabItem>
  <TabItem value="C++" label="C++">
  <SolutionAuthor name="@Ishitamukherjee2004"/>

  ```cpp
  #include <iostream>
  #include <vector>
  using namespace std;

  class Solution {
  public:
      int missingNumber(int n, vector<int>& arr) {
          // Calculate the expected sum of the first n natural numbers
          int total_sum = n * (n + 1) / 2;
          
          // Calculate the sum of the elements in the array
          int arr_sum = 0;
          for (int num : arr) {
              arr_sum += num;
          }
          
          // The missing number is the difference between the expected sum and the array sum
          return total_sum - arr_sum;
      }
  };

  // Example usage
  int main() {
      int t;
      cin >> t;
      while (t--) {
          int n;
          cin >> n;

          vector<int> arr(n - 1);
          for (int i = 0; i < n - 1; ++i)
              cin >> arr[i];
          Solution obj;
          cout << obj.missingNumber(n, arr) << "\n";
      }
      return 0;
  }
  ```

  </TabItem>

  <TabItem value="Javascript" label="Javascript" default>
  <SolutionAuthor name="@Ishitamukherjee2004"/>

  ```javascript
  class Solution {
  missingNumber(n, arr) {
    let totalSum = n * (n + 1) / 2;
    let arrSum = arr.reduce((a, b) => a + b, 0);
    return totalSum - arrSum;
  }
}

let solution = new Solution();
console.log(solution.missingNumber(4, [3, 1, 4])); // Expected output: 2
console.log(solution.missingNumber(5, [5, 3, 1, 2])); // Expected output: 4

  ```

  </TabItem>

  <TabItem value="Typescript" label="Typescript" default>
  <SolutionAuthor name="@Ishitamukherjee2004"/>

  ```typescript
  class Solution {
  missingNumber(n: number, arr: number[]): number {
    let totalSum: number = n * (n + 1) / 2;
    let arrSum: number = arr.reduce((a, b) => a + b, 0);
    return totalSum - arrSum;
  }
}

let solution: Solution = new Solution();
console.log(solution.missingNumber(4, [3, 1, 4])); // Expected output: 2
console.log(solution.missingNumber(5, [5, 3, 1, 2])); // Expected output: 4

  ```

  </TabItem>

  <TabItem value="Java" label="Java" default>
  <SolutionAuthor name="@Ishitamukherjee2004"/>

  ```java
  public class Solution {
  public int missingNumber(int n, int[] arr) {
    int totalSum = n * (n + 1) / 2;
    int arrSum = 0;
    for (int num : arr) {
      arrSum += num;
    }
    return totalSum - arrSum;
  }
}

public class Main {
  public static void main(String[] args) {
    Solution solution = new Solution();
    System.out.println(solution.missingNumber(4, new int[]{3, 1, 4})); // Expected output: 2
    System.out.println(solution.missingNumber(5, new int[]{5, 3, 1, 2})); // Expected output: 4
  }
}

  ```

  </TabItem>
</Tabs>

## Example Walkthrough

For the array `array = [3, 1, 4]` with `n = 4`:

1. The expected sum of the first 4 natural numbers is `4 * (4 + 1) / 2 = 10`.
2. The sum of the array elements is `3 + 1 + 4 = 8`.
3. The missing number is `10 - 8 = 2`.

For the array `array = [5, 3, 1, 2]` with `n = 5`:

1. The expected sum of the first 5 natural numbers is `5 * (5 + 1) / 2 = 15`.
2. The sum of the array elements is `5 + 3 + 1 + 2 = 11`.
3. The missing number is `15 - 11 = 4`.

## Solution Logic:

1. Calculate the expected sum of the first `n` natural numbers using the formula `n * (n + 1) / 2`.
2. Calculate the sum of the elements in the given array.
3. The missing number is the difference between the expected sum and the sum of the array elements.

## Time Complexity

* The time complexity is $O(n)$, where n is the size of the input array.

## Space Complexity

* The auxiliary space complexity is $O(1)$ because we are not using any extra space proportional to the size of the input array.