# sorted-array-hands-on-03
** Time Complexity Analysis:


Let K be the number of arrays and N be the size of each array
Total number of elements = K × N
For each element:

Insertion into heap: O(log K)
Extraction from heap: O(log K)


We perform these operations for all K×N elements
Therefore, total time complexity is O(K×N × log K)
