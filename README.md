Question 1: Big O Notation Rules

Big O notation is used to describe the upper bound of an algorithm's runtime or space complexity as the input size grows. It provides a way to classify algorithms based on how their performance scales. Here are the main rules with examples:

1. Constant Rule:

If an algorithm performs a fixed number of operations regardless of the input size, it's considered O(1).
Example: Accessing an element in an array by its index.

    ```java
    int[] arr = {1, 2, 3, 4, 5};
    int element = arr[0]; // Accessing the first element
    ```

    This operation takes the same amount of time regardless of the size of the array.

2. Dominant Term Rule:

When an algorithm has multiple terms in its complexity, only the dominant term (the one that grows the fastest) is considered.
Example: O(n^2 + n) simplifies to O(n^2).

    ```java
    for (int i = 0; i < n; i++) { // O(n)
        // some operation
    }
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) { // O(n^2)
            // some operation
        }
    }
    ```

    The nested loop dominates, so the complexity is O(n^2).

3. Multiplication Rule:

If an algorithm has nested loops, the complexities of the loops are multiplied.
Example: A nested loop where both loops iterate n times has a complexity of O(n * n) = O(n^2).

    ```java
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            // some operation
        }
    }
    ```

4. Addition Rule:

If an algorithm performs operations sequentially, the complexities of the operations are added.
Example: If one part of an algorithm takes O(n) time and another takes O(m) time, the total complexity is O(n + m). If n and m are equal, then the complexity is O(2n) which simplifies to O(n). If m is constant, then the complexity is O(n).

    ```java
    for (int i = 0; i < n; i++) {
        // some operation (O(n))
    }
    for (int i = 0; i < m; i++) {
        // some operation (O(m))
    }
    ```

5. Ignoring Constant Factors:

Constant factors are ignored in Big O notation. O(2n) is simplified to O(n).
Example:

    ```java
    for (int i = 0; i < 2 * n; i++) {
        // some operation
    }
    ```

    This loop has a complexity of O(2n), but it's simplified to O(n).

Question 2: Arrays vs. Linked Lists

1. Memory Allocation.

Arrays:
    1. Arrays use contiguous memory blocks.
    2. The size of an array must be known at compile time or during allocation.
    3. Memory is allocated statically or dynamically, but the size remains fixed after allocation.
Linked Lists.
    1. Linked lists use non-contiguous memory locations.
    2. Each node in a linked list stores a data element and a pointer to the next node.
    3. Memory is allocated dynamically as needed.

2. Performance.

Arrays:
    1. Accessing elements by index is O(1) because of contiguous memory allocation.
    2. Searching an unsorted array is O(n) in the worst case.
    3. Searching a sorted array can be O(log n) using binary search.
Linked Lists.
    1. Accessing elements by index is O(n) because you need to traverse the list from the head.
    2. Searching a linked list is O(n).
    3. Insertion and Deletion Operations.

Arrays.
    1 Insertion or deletion at the beginning or middle of an array requires shifting elements, resulting in O(n) time complexity.
    2. Insertion or deletion at the end of an array is O(1) if there's available space.
    
Linked Lists.
    1. Insertion or deletion at the beginning of a linked list is O(1).
    2. Insertion or deletion at the end requires traversing the list to the last node, resulting in O(n) time complexity.
    3. Insertion or deletion at a know node is O(1) if you have a pointer to the node before the target node.

Summary Table.

| Feature           | Arrays                               | Linked Lists                         |
| :---------------- | :----------------------------------- | :----------------------------------- |
| Memory Allocation | Contiguous                           | Non-contiguous                       |
| Access            | O(1) by index                       | O(n)                               |
| Search            | O(n) (unsorted), O(log n) (sorted) | O(n)                               |
| Insertion/Deletion (Beginning/Middle) | O(n)                               | O(1) (beginning), O(n) (end) |
| Insertion/Deletion (End) | O(1) if space available | O(n) |
