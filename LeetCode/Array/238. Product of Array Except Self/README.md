## 238. Product of Array Except Self
🔗  Link: [Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/description/)<br>
💡 Difficulty: Medium<br>
🛠️ Topics: Array<br>

=======================================================================================<br>
Given an integer array `nums`, return an array `answer` such that `answer[i]` is equal to the product of all the elements of `nums` except `nums[i]`.

The product of any prefix or suffix of `nums` is **guaranteed** to fit in a **32-bit** integer.

You must write an algorithm that runs in `O(n)` time and without using the division operation.

 

Example 1:

Input: nums = [1,2,3,4]<br>
Output: [24,12,8,6]<br>

Example 2:

Input: nums = [-1,1,0,-3,3]<br>
Output: [0,0,9,0,0]<br>

 
Constraints:
- 2 <= nums.length <= 10<sup>5</sup>
- -30 <= nums[i] <= 30
- The input is generated such that `answer[i]` is **guaranteed** to fit in a **32-bit** integer.
 

Follow up: Can you solve the problem in `O(1)` extra space complexity? (The output array does not count as extra space for space complexity analysis.)<br>
=======================================================================================<br>
### UMPIRE Method:
#### Understand

> - Ask clarifying questions and use examples to understand what the interviewer wants out of this problem.
> - Choose a “happy path” test input, different than the one provided, and a few edge case inputs. 
> - Verify that you and the interviewer are aligned on the expected inputs and outputs.
1. Can the `nums` array be empty?<br>
   No, at least two elements in the array.<br>
2. Any requirements on time/space complexity?<br>
   You must write an algorithm that runs in O(n) time and without using the division operation.<br>
3. Happy path - Input: nums = [1,5,3,2]; Output: [30,6,10,15]
4. Edge case - Input: nums = [0,1]; Output: [1,0]
5. Edge case - Input: nums = [0,0]; Output: [0,0]

### Match
> - See if this problem matches a problem category (e.g. Strings/Arrays) and strategies or patterns within the category
1. Array<br>
   This problem falls under the Arrays category because it involves manipulating elements based on their positions and computing prefix/suffix products.
2. Prefix/suffix product<br>
   This problem aligns with the prefix-suffix product pattern, which is commonly used for solving array-based multiplication problems without division.<br>
3. Strategy<br>
   A common approach to solving this type of problem is using a two-pass prefix and suffix product method, which works well because it efficiently computes the results in O(n) time with O(1) extra space. (This approach will appear in the second part of the solution.)

### Plan
> - Sketch visualizations and write pseudocode
> - Walk through a high level implementation with an existing diagram

General Idea: Compute prefix and suffix products first, then use these values to construct the `answer` array

1) Compute prefix product and suffix products, each having a length of `len(nums) + 1`
2) Update the `answer` array with the corresponding values of prefix and suffix products 
    
### Implement
> - Implement the solution (make sure to know what level of detail the interviewer wants)

see solution.py

### Review
> - Re-check that your algorithm solves the problem by running through important examples
> - Go through it as if you are debugging it, assuming there is a bug
### Evaluate
> - Finish by giving space and run-time complexity
> - Discuss any pros and cons of the solution

Assume N represents the number of items in the array.


- Time Complexity: O(N) for computing prefix and suffix products, and constructing the answer array.
- Space Complexity: O(N)

---------------------------------------------------------------------------------------------------------------------------------------------<br>
Follow up: Can you solve the problem in `O(1)` extra space complexity?

### Plan
General Idea: Use variable `curr` as running product to store prefix and suffix products of `nums`, then update the `answer` array with `curr`

1) Initialize an `answer` array with a length of `len(nums)`
2) Use `curr` to store the prefix products in the first for loop and update the `answer` array
3) In the second for loop, use `curr` to store the suffix products while updating the `answer` array  
    
### Implement
> - Implement the solution (make sure to know what level of detail the interviewer wants)

see solution.py

### Evaluate
Assume N represents the number of items in the array.

- Time Complexity: O(N) for computing prefix products, and constructing the answer array
- Space Complexity: O(1)
