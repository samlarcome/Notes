# Blind 75 - LeetCode

  - Blind 75 was designed by [Yangshun Tay](https://github.com/yangshun) and can be found [here](https://leetcode.com/list/xi4ci4ig/) or on the [technical interview handbook website](https://www.techinterviewhandbook.org/best-practice-questions/).
  - With this repo, I want to store my solutions, but more importantly, my thought process on how I got to them
  - I am hoping this will help me better understand the solutions to the problems, especially the ones I need assistance with

# Array
## 1) [Two Sum](https://leetcode.com/problems/two-sum/)

## 2) [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

## 3) [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)

## 4) [Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/)

## 5) [Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)

## 6) [Maximum Product Subarray](https://leetcode.com/problems/maximum-product-subarray/)

## 7) [Find Min in Rotated Sorted Array](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/)

## 8) [Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/)

## 9) [3Sum](https://leetcode.com/problems/3sum/)
  - Given an integer array nums, return all the triplets ```[nums[i], nums[j], nums[k]]``` such that ```i != j, i != k, and j != k,``` and ```nums[i] + nums[j] + nums[k] == 0```
  - Notice that the solution set must not contain duplicate triplets  
  
  **Example:**
  ```
    Input: nums = [-1,0,1,2,-1,-4]
    Output: [[-1,-1,2],[-1,0,1]]
    Explanation: 
    nums[0] + nums[1] + nums[2] = (-1) + 0 + 1 = 0.
    nums[1] + nums[2] + nums[4] = 0 + 1 + (-1) = 0.
    nums[0] + nums[3] + nums[4] = (-1) + 2 + (-1) = 0.
    The distinct triplets are [-1,0,1] and [-1,-1,2].
    Notice that the order of the output and the order of the triplets does not matter.
```
  **Solution:**
  ```Python
    print()
  ```
  
  **Explanation:**

# Binary

# Dynamic Programming

# Graph

# Interval

# Linked List

## 1) [Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/)
  - You are given the head of two sorted linked lists ```list1``` and ```list2```
  - Merge the two lists in a one sorted list. The list should be made by splicing together the nodes of the first two lists
  - Return the head of the merged linked list

  **Example**
  ```
    list1: 1 -> 2 -> 4
    list2: 1 -> 3 -> 4
    merge: 1 -> 1 -> 2 -> 3 -> 4 -> 4
  ```

  **Solution**
  ```Python
    # Definition for singly-linked list.
    # class ListNode(object):
    #     def __init__(self, val=0, next=None):
    #         self.val = val
    #         self.next = next
    class Solution(object):
        def mergeTwoLists(self, list1, list2):
          temp = merged = ListNode()
          
          while list1 and list2:
            if list1.val > list2.val:
              temp.next = list2
              temp, list2 = temp.next, list2.next
            else:
              temp.next = list1
              temp, list1 = temp.next, list1.next
              
          if list1:
            temp.next = list1
          elif list2:
            temp.next = list2
            
          return merged.next
  ```
  **Explanation:**  
  - We use a two pointer method here, where each pointer starts at head of each linked list
  - At each iteration, we just add the the node with the lesser value to the merged list, and move that pointer to the next node
  - We repeat this until one of the pointers reaches the end of its respective linked list
  - Before returning, we check if the pointer for either list has not reached the end (one should not because of while loop condition)
    - We can just add it to the end of the merged list as we know it is already sorted
  - We return ```merged.next``` because we set merged to an empty node ```merged = ListNode()``` and the first thing we set is ```merged.next```

# Matrix

# String 

# Tree

# Heap
