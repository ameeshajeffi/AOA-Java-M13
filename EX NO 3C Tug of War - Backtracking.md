
# EX 3C Tug of War problem - Backtracking.
## DATE: 16.10.25
## AIM:
To write a Java program to for given constraints.
Given an integer array nums, return true if you can partition the array into two subsets such that the sum of the elements in both subsets is equal or false otherwise.
Example 1:
Input: Enter the number of elements: 4
Enter the elements of the array:
1 5 11 5
Output: true
Explanation: The array can be partitioned as [1, 5, 5] and [11].

Constraints:

1 <= nums.length <= 200
1 <= nums[i] <= 100

## Algorithm
1. Add all numbers in the array.

2. If the total is odd, return false (cannot split equally).

3. Set target = total / 2.

4. Use a boolean array dp to track which sums are possible.

5. For each number, update dp to mark new reachable sums.

6. If dp[target] is true, return true; otherwise return false. 

## Program:
```
/*
Program to implement Reverse a String
Developed by: ROSHINI S
Register Number: 212223230174

import java.util.*;

public class Solution {

    public boolean canPartition(int[] nums) {
        int total = 0;
        for (int num : nums)
            total += num;

        if (total % 2 != 0)
            return false;

        int target = total / 2;
        boolean[] dp = new boolean[target + 1];
        dp[0] = true;

        for (int num : nums) {
            for (int j = target; j >= num; j--) {
                dp[j] = dp[j] || dp[j - num];
            }
        }

        return dp[target];
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] nums = new int[n];
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }
        Solution sol = new Solution();
        boolean result = sol.canPartition(nums);
        System.out.println(result);
        sc.close();
    }
}
  
*/
```

## Output:

<img width="440" height="372" alt="image" src="https://github.com/user-attachments/assets/9001f00d-e458-46fe-bca5-f6e80cf23ab9" />


## Result:
The program successfully implemented and the expected output is verified.
