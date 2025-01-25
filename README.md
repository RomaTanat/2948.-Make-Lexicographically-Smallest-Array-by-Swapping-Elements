# 2948.-Make-Lexicographically-Smallest-Array-by-Swapping-Elements
### Code Description:

This code solves the problem of transforming an array of integers into the lexicographically smallest possible order, while ensuring that two elements can be swapped if the absolute difference between them does not exceed a given limit.

### Solution Algorithm:
1. **Sorting the Initial Array**: 
   - First, the input array `nums` is sorted in the variable `ordered_nums`. This ensures that within each group, the elements are arranged in ascending order, which is part of achieving the lexicographically smallest array.

2. **Grouping Elements**:
   - A dictionary `num_to_group` is created, which maps each element to the group number it belongs to.
   - A list `group_start` is used to store the index of the first element of each group in the sorted array.
   - The grouping process works as follows: elements whose absolute difference from the previous element is less than or equal to `limit` are considered part of the same group. If the difference between the current element and the previous one exceeds the `limit`, a new group is started.

3. **Filling the Result Array**:
   - For each element in the original array `nums`, its group is determined using the `num_to_group` dictionary.
   - The element is then placed into the result array in the order it should appear in the lexicographically smallest array.
   - Elements within each group are picked in the order they appear in the sorted array.

4. **Returning the Result**: The `result` array contains the lexicographically smallest array that can be formed by performing the allowed swaps.

### Methods and Approaches Used:

1. **Sorting (Sorted array)**:
   - The first step is sorting the array using Python's `sorted(nums)` method. This is a crucial step to guarantee that the elements will be in ascending order, which is necessary for forming the lexicographically smallest array.

2. **Grouping**:
   - Using the dictionary `num_to_group`, elements are grouped based on their values if their absolute difference does not exceed the `limit`. This allows us to correctly group elements that can be swapped with each other.
   - The `group_start` list keeps track of the starting index of each group in the sorted array.

3. **Using a Dictionary**:
   - The dictionary `num_to_group` is used to store the group number each element belongs to. This enables quick lookup to determine the group of an element and place it in the correct position in the result array.

4. **Simple Iterative Process**:
   - The algorithm uses two main loops: one for grouping the elements and one for constructing the final result array. This keeps the problem-solving process simple and efficient with minimal intermediate data structures.

### Key Points:
- **Time Complexity**:
  - Sorting the array takes O(n log n), where n is the size of the array.
  - The process of grouping and placing elements into the result array is O(n).
  - Therefore, the overall time complexity is O(n log n), which is efficient for most cases.

- **Correctness of the Solution**:
  - After sorting the array, the algorithm iterates through the array to group the elements. This ensures that the lexicographically smallest array is obtained while adhering to the limit condition.

### Potential Improvements:
1. If the problem were more complex, such as with larger arrays or additional constraints, more advanced data structures or approaches, like **segment trees** or **Union-Find** for efficient grouping and merging, could be considered.
   
2. For additional memory or time constraints, optimizations in the sorting step or using different algorithms for grouping might be explored.

### Conclusion:
This code effectively solves the problem using sorting and grouping to achieve the lexicographically smallest array. It is a typical example of using sorting and dictionaries to group and redistribute elements in an array.
