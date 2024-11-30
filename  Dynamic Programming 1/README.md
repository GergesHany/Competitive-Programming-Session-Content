- [session link](https://drive.google.com/file/d/1SBK278dKdTxMitwiGkFQkWBZIxbkLf1I/view?usp=sharing)
- [Presentation link](https://docs.google.com/presentation/d/1PAddKVSs-aSzfYydphF0jb4AG-_tp6zGnyMdOHq_blo/edit#slide=id.g2d38eb60ad8_0_6)

# Dynamic Programming Session Overview

This session focuses on key concepts and problem-solving approaches in **Dynamic Programming (DP)**:

## 1. Memoization

- Utilizing a top-down recursive approach to store solutions of previously computed subproblems in a memory-based data structure (e.g., array or hash table).
- Helps avoid redundant calculations by reusing stored results.

## 2. Maximization Problems

- Tackling problems aimed at **maximizing a specific value**, such as:
  - Finding the longest subsequence.
  - Achieving the highest score.
  - Maximizing profit under given constraints.

## 3. Subset Problems

- Solving problems that involve **selecting subsets** from a set of elements to achieve a target objective.
- Common examples:
  - Knapsack problem.
  - Selecting combinations under capacity limits.

## 4. Counting Problems

- Developing DP solutions to **count the number of ways** to achieve a specific outcome.
- Examples include:
  - Number of combinations or arrangements satisfying given conditions.

## 5. Build Problems

- Creating solutions where the focus is on **constructing outputs step by step**.
- Examples:
  - Building sequences.

---

<br>

# Dynamic Programming - ICPC SCU LEVEL #2

## Session Structure

- Introduction to Dynamic Programming
- Characteristics of Dynamic Programming Problems
- Types of Dynamic Programming
- Common Examples of Dynamic Programming Problems
- State Representation
- Time and Space Complexity Analysis
- Practice Problems

---

## 1 - Introduction to Dynamic Programming

- **Definition**:  
  Dynamic Programming is a method for solving complex problems by breaking them down into simpler subproblems, solving each subproblem just once, and storing their solutions — usually using a memory-based data structure (like an array or a hash table). This technique is particularly effective for optimization problems.

- **Importance**:  
  By using dynamic programming, one can achieve a more efficient algorithm compared to naive approaches, especially in cases where the same calculations would otherwise be repeated multiple times.

---

## 2 - Characteristics of Dynamic Programming Problems

- **Optimal Substructure**:  
  The optimal solution of a problem can be constructed efficiently from the optimal solutions of its subproblems.

- **Overlapping Subproblems**:  
  The problem can be broken down into subproblems that are reused several times, allowing for a significant reduction in computational effort by storing the results of these subproblems (memoization) or building up the solution iteratively (tabulation).

---

## 3 - Types of Dynamic Programming

Dynamic Programming (DP) can be broadly categorized into two main types based on how the subproblems are solved and how their solutions are stored:

1. **Top-Down Approach (Memoization)**
2. **Bottom-Up Approach (Tabulation)**

### Top-Down Approach (Memoization)

- **Definition**:  
  The top-down approach involves solving the problem recursively, starting from the original problem and breaking it down into smaller subproblems. To avoid redundant calculations, the results of subproblems are stored in a memory table (hashmap, array, etc.), so each subproblem is solved only once.

- **Process**:

  1. Start solving the original problem recursively.
  2. As subproblems are encountered, check if they have already been solved and stored.
  3. If not, compute the solution and store it.

- **Advantages**:

  - Easier to implement for those familiar with recursion.
  - Can handle only necessary subproblems, potentially avoiding unnecessary work.

- **Disadvantages**:
  - More stack memory is used due to recursion.
  - Prone to stack overflow in deep recursion.

---

## 4 - Common Examples of Dynamic Programming Problems

1. **Fibonacci Sequence (Overlapping Style)**: [LeetCode Problem](https://leetcode.com/problems/fibonacci-number/)
2. **0/1 Knapsack Problem (Maximization Style)**: [AtCoder Problem](https://atcoder.jp/contests/dp/tasks/dp_d)
3. **Longest Common Subsequence (LCS) (Maximization Style)**: [LeetCode Problem](https://leetcode.com/problems/longest-common-subsequence/description/)
4. **Edit Distance (Minimization Style)**: [CSES Problem](https://cses.fi/problemset/task/1639)

---

## 5 - State Representation

- The concept of state representation is crucial in dynamic programming (DP) as it defines how to represent the problem at each step. A state captures a subproblem, and the goal is to identify the minimum amount of information required to uniquely describe that subproblem, so we can store and reuse its solution.

- **Defining the State**:  
  The state is typically defined as a function of one or more variables where the value of the state is the solution to a subproblem.

---

## 6 - Time and Space Complexity Analysis

- **Space Complexity Analysis**:  
  The size of the DP table or memoization structure.

- **Time Complexity Analysis**:  
  Total time complexity is the product of the number of states and the time taken for each transition.

---

## 7 - Practice Problems

1. **Frog 1**: [AtCoder Problem](https://atcoder.jp/contests/dp/tasks/dp_a)
2. **Frog 2**: [AtCoder Problem](https://atcoder.jp/contests/dp/tasks/dp_b)
3. **Divide and Divide**: [AtCoder Problem](https://atcoder.jp/contests/abc340/tasks/abc340_c)
4. **Dice Combinations**: [CSES Problem](https://cses.fi/problemset/task/1633)
5. **Minimizing Coins**: [CSES Problem](https://cses.fi/problemset/task/1634/)
6. **LCS**: [AtCoder Problem](https://atcoder.jp/contests/dp/tasks/dp_f)

---
