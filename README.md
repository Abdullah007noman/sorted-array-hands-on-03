# hands-on-03
This repository contains implementations of :
* Implementation and debugging of the Fibonacci sequence with recursive calls tracking.
* Given K sorted arrays of sieze N and need to merge them all.(Min-heap)
* Given a sorted array of sieze N and need to remove the duplicate elements from the array.


# 1. Fibonacci Sequence
The complete call sequence can be summarized as:
  - fib(5) → fib(4) + fib(3)
  - fib(4) → fib(3) + fib(2)
  - fib(3) → fib(2) + fib(1)
  - fib(2) → fib(1) + fib(0)

Key points about the implementation:

* Followed exact return statement format: return fib(n-1) + fib(n-2)
* No optimization used as requested
* Proper base cases implemented
* Complete tracking of all recursive calls
* Indentation added to visualize the call stack depth

The final result fib(5) = 5 is calculated through multiple recursive calls, with each call building up from the base cases (fib(0) = 0 and fib(1) = 1).

## 2. Min-heap (for problem-1)
## Time Complexity:


* Let K be the number of arrays and N be the size of each array
* Total number of elements = K × N
* For each element:
  -  Insertion into heap: O(log K)
  -  Extraction from heap: O(log K)
* We perform these operations for all K×N elements
* Therefore, total time complexity is O(K×N × log K)
  
## Space Complexity:

* Heap size: O(K) - stores one element from each array
* Result array: O(K×N) - stores all elements
* Total space complexity: O(K×N)

## Improvements of the implementation

The current implementation (in this repository) using a min-heap is generally considered optimal for most practical cases, as it achieves O(K×N × log K) time complexity, which is asymptotically optimal for this problem. The choice between these improvements would depend on specific use cases and constraints (memory limitations, parallel processing availability, etc.)
There are some more way to improve the results:
* Divide and Conquer Approach
  - Instead of merging all arrays at once, we could merge pairs of arrays
  - This could be more cache-friendly for very large arrays
  - Time complexity would still be O(K×N × log K) but with better constants


* Parallel Processing:
  - For very large arrays, we could parallelize the merging process
  - Different pairs of arrays could be merged simultaneously
  - This would significantly improve performance on multi-core systems


* Memory Optimization:

  - Current implementation creates a new result array
  - Could modify to work in-place if memory is a constraint
  - Would increase time complexity but save space

## 3. Remove Duplicates from Sorted Array (for problem 02)
## How the algorithm works:
* Uses two-pointer technique
* unique_ptr keeps track of where to place next unique element
* Iterates through array once
* Returns length of array with duplicates removed

## Time Complexity:
* The algorithm uses a single pass through the array
* Each element is visited exactly once
* Time Complexity: O(n) where n is the size of the array


##  Improvements of the implementation
* Error Handling:
   - Add input validation
   - Handle negative numbers explicitly
   - Add bounds checking


* Performance Optimizations:
    - For very large arrays, could implement parallel processing for the comparison phase
    - Could add early termination if no duplicates are found after a certain point
    - Could implement batch processing for very large arrays


* Memory Optimization:
  - Current solution is already O(1) space complexity
  - Could add option to shrink array capacity after removal (trade-off with performance)


## The current implementation is optimal for the given constraints:

* It runs in O(n) time
* Uses O(1) extra space
* Modifies array in-place as required
* Maintains relative order of elements
* Doesn't use set container as specified





