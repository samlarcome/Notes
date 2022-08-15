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

## 2) [Remove N-th Node from End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/) (Medium)
  - Given the ```head``` of a linked list, remove the ```nth``` node from the end of the list and return its head.  
  **Example:**
  ```
  [1,2,3,4,5] and n = 2
  [1,2,3,5]
  ```

  **Solution:**
  ```Python
    # Definition for singly-linked list.
    # class ListNode(object):
    #   def __init__(self, val=0, next=None):
    #     self.val = val
    #     self.next = next
    class Solution(object):
      def removeNthFromEnd(self, head, n):
        """
        :type head: ListNode
        :type n: int
        :rtype: ListNode
        """
        dummy = ListNode(-1, head)
        left, right = dummy, head
        while n > 0 and right:
          right = right.next
          n -= 1
          
        while right:
          left = left.next
          right = right.next
          
        left.next = left.next.next
        return dummy.next
  ```
  **Explanation:**  
  - The difficulty is identifying where the nth last node is in the singly linked list
  - We can use a two pointer method, like many linked list problems
  - **The key: if we start the left and right pointer *n* nodes apart, the left points to the node to remove when right is none after shifting each by one**
  - The issue is, we are at the exact node we want to remove. If we want to remove it, we need the previous node (left.prev) to point to the next node (left.next)
  - We can solve this with the dummy node technique, inserting a 'dummy' node before the ```head``` node that we do not really use
  - But if we start our left pointer right before the head node, it will point to the node just before the node we want to remove
  - This allows us to make a call like ```left.next = left.next.next``` to remove the desired node


# Matrix

# String 

# Tree

# Heap
