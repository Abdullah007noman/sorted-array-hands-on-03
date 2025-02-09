# sorted-array-hands-on-03
This repository contains implementations of :
* Given K sorted arrays of sieze N and need to merge them all.(Min-heap)
* Given a sorted array of sieze N and need to remove the duplicate elements from the array.

## 1. Min-heap (for problem-1)
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

## Improvements of implementation

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



