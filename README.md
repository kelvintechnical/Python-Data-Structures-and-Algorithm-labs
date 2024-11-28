

# Python Data Structures and Algorithms labs

## Repository Overview
This repository contains a curated collection of 40 Python labs and labs designed to help developers learn and master data structures and algorithms while improving their Python programming skills. Each project is structured to build upon key concepts, gradually increasing in complexity.

---

## Table of Contents
- [Beginner Projects](#beginner-projects)
- [Intermediate Projects](#intermediate-projects)
- [Advanced Projects](#advanced-projects)
- [Additional Labs](#additional-labs)
- [How to Use This Repository](#how-to-use-this-repository)
- [Contribution Guidelines](#contribution-guidelines)
- [Contact Me](#contact-me)

---

## 📫 How to Reach Me:

**Email**: [ktobia10@wgu.edu](mailto:ktobia10@wgu.edu)  
**LinkedIn**: [Kelvin R. Tobias](https://www.linkedin.com/in/kelvin-r-tobias-211949219/)  
**Bluesky**: [@kelvintechnical.bsky.social](https://bsky.app/profile/kelvintechnical.bsky.social)  
**Instagram**: [@kelvinintech](https://www.instagram.com/kelvinintech/)  

---

## About Me

Hi, my name is **Kelvin R. Tobias**, and I’m currently a student at **Western Governors University**, pursuing my bachelor’s degree in **Software Engineering**. My curriculum has provided me with the opportunity to learn **Python**, **JavaScript**, **Java**, and **C#**.

I build a lot of projects in my free time to reinforce what I’ve learned. As you know, it’s hard to remember the syntax for so many languages, so building projects helps solidify my knowledge and skills.

---

---

## Beginner Projects
1. [**Reverse a String**](https://github.com/kelvintechnical/Reverse-a-string)
2. [**Palindrome Checker**](https://github.com/kelvintechnical/react-palindrone-checker)
3. [**Two-Sum Problem**](https://github.com/kelvintechnical/two-sum-checker)
4. **Find Maximum Element in an Array**
5. **Factorial Calculator**
6. **Binary Search Implementation**
7. **Bubble Sort Implementation**
8. **Linked List Implementation**
9. **Find Duplicates in an Array**
10. **Generate Fibonacci Numbers**

---

## Intermediate Projects
11. **Tower of Hanoi**
12. **Balanced Parentheses Checker**
13. **Merge Sort Implementation**
14. **Quick Sort Implementation**
15. **Binary Tree Implementation**
16. **Graph Representation**
17. **DFS and BFS**
18. **Find the Middle Element in a Linked List**
19. **LRU Cache Implementation**
20. **Count Inversions in an Array**

---

## Advanced Projects
21. **Dijkstra's Shortest Path Algorithm**
22. **Kruskal’s Algorithm**
23. **Trie Implementation**
24. **Heap Sort**
25. **Knapsack Problem**
26. **Topological Sort**
27. **Word Ladder Problem**
28. **Median of Two Sorted Arrays**
29. **N-Queens Problem**
30. **Design a Data Structure**

---

## Additional Labs
These labs are designed to provide hands-on practice with specific topics related to data structures and algorithms.

31. **Matrix Transposition**
    - Write a function to transpose a given matrix.
    ```python
    def transpose(matrix):
        return [[row[i] for row in matrix] for i in range(len(matrix[0]))]
    ```

32. **Anagram Checker**
    - Check if two strings are anagrams using sorting or hashing.
    ```python
    def is_anagram(str1, str2):
        return sorted(str1) == sorted(str2)
    ```

33. **Implement a Queue Using Stacks**
    - Build a queue data structure using two stacks.
    ```python
    class QueueUsingStacks:
        def __init__(self):
            self.stack1 = []
            self.stack2 = []

        def enqueue(self, item):
            self.stack1.append(item)

        def dequeue(self):
            if not self.stack2:
                while self.stack1:
                    self.stack2.append(self.stack1.pop())
            return self.stack2.pop() if self.stack2 else None
    ```

34. **Find the Longest Substring Without Repeating Characters**
    - Use sliding window and hash maps to solve.
    ```python
    def longest_unique_substring(s):
        seen = {}
        max_length = start = 0
        for i, char in enumerate(s):
            if char in seen and seen[char] >= start:
                start = seen[char] + 1
            seen[char] = i
            max_length = max(max_length, i - start + 1)
        return max_length
    ```

35. **Binary Tree Level Order Traversal**
    - Traverse a binary tree level by level using a queue.
    ```python
    def level_order_traversal(root):
        if not root:
            return []
        result, queue = [], [root]
        while queue:
            level = []
            for i in range(len(queue)):
                node = queue.pop(0)
                level.append(node.val)
                if node.left:
                    queue.append(node.left)
                if node.right:
                    queue.append(node.right)
            result.append(level)
        return result
    ```

36. **Detect a Cycle in a Linked List**
    - Use Floyd’s Cycle Detection Algorithm.
    ```python
    def has_cycle(head):
        slow, fast = head, head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
            if slow == fast:
                return True
        return False
    ```

37. **Maximum Profit from Stock Prices**
    - Use dynamic programming to find maximum profit.
    ```python
    def max_profit(prices):
        min_price = float('inf')
        max_profit = 0
        for price in prices:
            min_price = min(min_price, price)
            max_profit = max(max_profit, price - min_price)
        return max_profit
    ```

38. **Generate All Permutations of a String**
    - Use recursion to generate all permutations.
    ```python
    def permute(s, step=0):
        if step == len(s):
            print("".join(s))
        for i in range(step, len(s)):
            s_copy = [char for char in s]
            s_copy[step], s_copy[i] = s_copy[i], s_copy[step]
            permute(s_copy, step + 1)
    ```

39. **Kth Largest Element in an Array**
    - Use a min-heap or quickselect algorithm.
    ```python
    import heapq
    def find_kth_largest(nums, k):
        return heapq.nlargest(k, nums)[-1]
    ```

40. **Sudoku Solver**
    - Use backtracking to solve a Sudoku puzzle.
    ```python
    def solve_sudoku(board):
        def is_valid(num, row, col):
            for i in range(9):
                if board[row][i] == num or board[i][col] == num:
                    return False
            box_row, box_col = row // 3 * 3, col // 3 * 3
            for i in range(3):
                for j in range(3):
                    if board[box_row + i][box_col + j] == num:
                        return False
            return True

        for row in range(9):
            for col in range(9):
                if board[row][col] == '.':
                    for num in '123456789':
                        if is_valid(num, row, col):
                            board[row][col] = num
                            if solve_sudoku(board):
                                return True
                            board[row][col] = '.'
                    return False
        return True
    ```

---

## How to Use This Repository
1. Clone the repository:
   ```bash
   git clone https://github.com/yourGitHubHandle/Python-DSA-Projects.git
