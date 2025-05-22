**Enhanced and Completed Data Structures and Algorithms Revision Guide**

## Table of Contents

1.  [Time & Space Complexity](#time--space-complexity)
2.  [Arrays & Strings](#arrays--strings)
    *   [Key Array Techniques](#key-array-techniques)
        *   [Two Pointers Technique](#two-pointers-technique)
        *   [Sliding Window Technique](#sliding-window-technique)
        *   [Prefix Sum Technique](#prefix-sum-technique)
    *   [Advanced Array Problems](#advanced-array-problems)
3.  [Linked Lists](#linked-lists)
    *   [Singly Linked Lists](#singly-linked-lists)
    *   [Doubly Linked Lists (Conceptual)](#doubly-linked-lists-conceptual)
    *   [Circular Linked Lists (Conceptual)](#circular-linked-lists-conceptual)
    *   [Basic Linked List Operations](#basic-linked-list-operations)
    *   [Classic Linked List Problems](#classic-linked-list-problems)
    *   [Advanced Linked List Problems](#advanced-linked-list-problems)
4.  [Stacks & Queues](#stacks--queues)
    *   [Stacks](#stacks)
        *   [Stack Implementation and Applications](#stack-implementation-and-applications)
        *   [Advanced Stack Applications](#advanced-stack-applications)
    *   [Queues](#queues)
        *   [Queue Implementation and Applications](#queue-implementation-and-applications)
        *   [Circular Queues](#circular-queues)
        *   [Deques (Double-Ended Queues)](#deques-double-ended-queues)
        *   [Priority Queues (Conceptual Overview)](#priority-queues-conceptual-overview)
5.  [Trees](#trees)
    *   [Basic Tree Terminologies](#basic-tree-terminologies)
    *   [Binary Trees (BT)](#binary-trees-bt)
        *   [Binary Tree Properties and Validation](#binary-tree-properties-and-validation)
    *   [Binary Search Trees (BST)](#binary-search-trees-bst)
        *   [BST Operations](#binary-search-tree-operations)
    *   [Balanced Binary Trees (Conceptual)](#balanced-binary-trees-conceptual)
        *   [AVL Trees](#avl-trees)
        *   [Red-Black Trees](#red-black-trees)
    *   [Heaps](#heaps)
        *   [Min-Heap & Max-Heap](#min-heap--max-heap)
        *   [Heap Operations](#heap-operations)
    *   [Tries (Prefix Trees)](#tries-prefix-trees)
    *   [Advanced Tree Problems](#advanced-tree-problems)
6.  [Graphs](#graphs)
    *   [Graph Terminologies](#graph-terminologies)
    *   [Graph Representation](#graph-representation)
    *   [Graph Traversal Algorithms](#graph-traversal-algorithms)
    *   [Cycle Detection](#cycle-detection)
    *   [Topological Sorting](#topological-sorting)
    *   [Shortest Path Algorithms](#shortest-path-algorithms)
    *   [Minimum Spanning Trees (MST) - Conceptual](#minimum-spanning-trees-mst---conceptual)
7.  [Sorting Algorithms](#sorting-algorithms)
    *   [Basic Sorting Algorithms](#basic-sorting-algorithms)
    *   [Advanced Sorting Algorithms](#advanced-sorting-algorithms)
    *   [Specialized Sorting Algorithms](#specialized-sorting-algorithms)
8.  [Searching Algorithms](#searching-algorithms)
    *   [Linear Search](#linear-search)
    *   [Binary Search and Variations](#binary-search-and-variations)
    *   [Advanced Search Problems](#advanced-search-problems)
9.  [Hashing](#hashing)
    *   [Hash Functions](#hash-functions)
    *   [Collision Resolution Techniques](#collision-resolution-techniques)
    *   [HashMap/Hashtable Implementation Concepts](#hashmaphashtable-implementation-concepts)
10. [Recursion and Backtracking](#recursion-and-backtracking)
    *   [Recursion](#recursion)
    *   [Backtracking](#backtracking)
11. [Dynamic Programming (DP)](#dynamic-programming-dp)
    *   [Core DP Concepts](#core-dp-concepts)
    *   [Basic DP Problems (1D DP)](#basic-dp-problems-1d-dp)
    *   [2D Dynamic Programming](#2d-dynamic-programming)
    *   [Advanced DP Problems](#advanced-dp-problems)
12. [Greedy Algorithms](#greedy-algorithms)
    *   [Concept](#concept)
    *   [Examples](#examples)
13. [Advanced Topics (Continued)](#advanced-topics-continued)
    *   [Union-Find (Disjoint Set Union)](#union-find-disjoint-set-union)
    *   [Bit Manipulation (Overview)](#bit-manipulation-overview)

---

## 1. Time & Space Complexity

Understanding algorithmic complexity is crucial for technical interviews. It helps you analyze the efficiency of your solutions in terms of time taken and memory used, especially as input size grows.

**Conceptual Explanation:**
*   **Time Complexity:** Measures the amount of time an algorithm takes to run as a function of the length of the input. We aim for algorithms that are fast even for large inputs.
*   **Space Complexity:** Measures the amount of memory space an algorithm requires as a function of the length of the input. This includes both the space for input values and any auxiliary space used by the algorithm.
*   **Why Big O?** Big O notation describes the limiting behavior of a function when the argument tends towards a particular value or infinity. In algorithm analysis, it describes the worst-case scenario, providing an upper bound on the growth rate of the algorithm's resource consumption.

### Big O Notation Hierarchy

This hierarchy helps to quickly compare the efficiency of different algorithms.
*   **O(1) - Constant Time:** The algorithm takes the same amount of time regardless of the input size.
    *   *Explanation:* Operations like accessing an array element by index, arithmetic operations, or a fixed number of statements.
*   **O(log n) - Logarithmic Time:** The time taken increases logarithmically with the input size. Common in algorithms that divide the problem into smaller pieces, like binary search.
    *   *Explanation:* If each step reduces the problem size by a constant factor (e.g., halves it), the number of steps will be proportional to log n.
*   **O(n) - Linear Time:** The time taken is directly proportional to the input size.
    *   *Explanation:* Algorithms that iterate through the input once, like a simple loop.
*   **O(n log n) - Linearithmic Time:** A common complexity for efficient sorting algorithms like Merge Sort and Quick Sort.
    *   *Explanation:* Typically involves dividing the problem (log n levels) and doing linear work at each level (n).
*   **O(n²) - Quadratic Time:** The time taken is proportional to the square of the input size. Common with nested loops.
    *   *Explanation:* For each element, you might iterate through the entire list again.
*   **O(n³) - Cubic Time:** The time taken is proportional to the cube of the input size. Often involves three nested loops.
*   **O(2ⁿ) - Exponential Time:** The time taken doubles with each addition to the input size. Extremely slow for even moderately sized inputs.
    *   *Explanation:* Often seen in recursive solutions that solve multiple subproblems for each input, like finding all subsets.
*   **O(n!) - Factorial Time:** The time taken grows factorially with the input size. Unsuitable for all but the smallest inputs.
    *   *Explanation:* Algorithms that try every permutation of the input, like the brute-force traveling salesman problem.

**Analyzing Complexity:**
*   **Loops:** A single loop iterating `n` times is O(n). Nested loops are generally O(n^k) where k is the number of nested loops (if each iterates `n` times).
*   **Consecutive Statements:** Add complexities. O(A) + O(B) = O(max(A,B)).
*   **Conditional Statements (if/else):** Take the complexity of the worst-case branch.
*   **Recursive Calls:** Depends on the number of recursive calls and the work done in each call. The Master Theorem or recursion tree method can be used for analysis.

### Space Complexity Considerations
Space complexity includes both **auxiliary space** (extra space used by the algorithm, beyond the input) and **input space** (space taken by the input itself). In interviews, we typically focus on **auxiliary space** when "space complexity" is mentioned, unless specified otherwise.

*   **O(1) Space (Constant):** Algorithm uses a fixed amount of extra space, regardless of input size (e.g., a few variables).
*   **O(n) Space (Linear):** Extra space grows linearly with input size (e.g., creating a copy of an array, recursion stack depth in some cases).
*   **O(log n) Space (Logarithmic):** Extra space grows logarithmically (e.g., recursion stack depth for some divide-and-conquer algorithms like binary search recursion if tail call optimization isn't present, or certain tree algorithms).

```java
// Example: O(1) Time, O(1) Space - Constant extra space
// Finds the maximum element in an array.
public int findMax(int[] arr) {
    if (arr == null || arr.length == 0) {
        throw new IllegalArgumentException("Input array cannot be null or empty.");
    }
    int max = arr[0]; // O(1) space for 'max' variable
    // Loop runs 'n-1' times, where n is arr.length. This is O(n) time.
    for (int i = 1; i < arr.length; i++) { // O(1) space for 'i'
        if (arr[i] > max) { // O(1) time for comparison and assignment
            max = arr[i];
        }
    }
    return max; // O(1) time
}
// Overall Time: O(n)
// Overall Auxiliary Space: O(1)

// Example: O(n) Time, O(n) Space - Linear extra space due to recursion stack
// Calculates factorial of n.
public int factorial(int n) {
    if (n < 0) {
        throw new IllegalArgumentException("Input cannot be negative.");
    }
    // Base case
    if (n <= 1) return 1; // O(1) time
    // Recursive step. Each call adds a frame to the call stack.
    // There will be 'n' active calls on the stack in the worst case.
    return n * factorial(n - 1); // O(1) time for multiplication per call
}
// Overall Time: O(n) - n recursive calls, O(1) work per call.
// Overall Auxiliary Space: O(n) - for the recursion call stack.

// Example: O(n) Time, O(n) Space - Explicit extra space with data structure
// Finds two numbers in an array that sum up to a target.
public int[] twoSum(int[] nums, int target) {
    // HashMap can store up to 'n' elements in the worst case.
    Map<Integer, Integer> map = new HashMap<>(); // O(n) auxiliary space
    // Loop runs 'n' times.
    for (int i = 0; i < nums.length; i++) { // O(1) space for 'i' and 'complement'
        int complement = target - nums[i]; // O(1) time
        // map.containsKey() and map.get() are O(1) on average for HashMap.
        if (map.containsKey(complement)) {
            return new int[]{map.get(complement), i}; // O(1) time
        }
        map.put(nums[i], i); // O(1) time on average
    }
    return new int[]{-1, -1}; // Should not be reached if a solution always exists as per problem
}
// Overall Time: O(n) - single pass through the array.
// Overall Auxiliary Space: O(n) - for the HashMap.
```

---

## 2. Arrays & Strings

Arrays and Strings are fundamental contiguous data structures. Arrays store elements of the same type in a fixed-size block of memory, while strings are typically arrays of characters. Mastering their manipulation techniques is essential.

**Conceptual Explanation (Arrays):**
*   **Definition:** A linear data structure that stores a collection of elements of the same data type at contiguous memory locations.
*   **Indexing:** Elements are accessed using an index (usually 0-based). `array[i]` gives the element at the i-th position.
*   **Fixed Size:** In many languages (like Java's primitive arrays), the size of an array is fixed upon creation. Dynamic arrays (like `ArrayList` in Java) can resize.
*   **Advantages:**
    *   O(1) access time to elements if the index is known.
    *   Good for storing and accessing sequential data.
    *   Memory locality can lead to good cache performance.
*   **Disadvantages:**
    *   Fixed size (for primitive arrays) can lead to wastage or overflow.
    *   O(n) time for insertion or deletion in the middle, as elements may need to be shifted.
    *   Searching takes O(n) time for unsorted arrays.

**Conceptual Explanation (Strings):**
*   **Definition:** A sequence of characters. In Java, strings are objects and immutable (their values cannot be changed after creation).
*   **Internal Representation:** Often backed by a character array.
*   **Operations:** Concatenation, substring, length, character access, comparison, etc.
*   **Immutability (Java):** When you "modify" a string in Java (e.g., concatenate), a new string object is created. This has performance implications for frequent modifications (use `StringBuilder` or `StringBuffer` instead).

### Key Array Techniques

#### Two Pointers Technique
**Conceptual Explanation:**
This technique involves using two integer pointers that typically traverse an array or list. The way they move (towards each other, one fast one slow, both in the same direction but spaced apart) depends on the problem. It's often used to find pairs, subarrays, or specific elements efficiently, usually reducing complexity from O(n²) to O(n).

**When to Use:**
*   Problems involving finding pairs in a sorted array.
*   Problems requiring comparison of elements from opposite ends of a sequence (e.g., palindrome).
*   Problems where you need to process elements in a specific relative order.

**Code Snippets & Explanations:**

```java
// Classic Two Pointers - Palindrome Check
// Checks if a string is a palindrome, ignoring non-alphanumeric characters and case.
public boolean isPalindrome(String s) {
    if (s == null) return false; // Or true, depending on definition for null
    int left = 0, right = s.length() - 1; // Pointers at the start and end

    while (left < right) {
        // Move 'left' pointer to the right until an alphanumeric character is found
        while (left < right && !Character.isLetterOrDigit(s.charAt(left))) {
            left++;
        }
        // Move 'right' pointer to the left until an alphanumeric character is found
        while (left < right && !Character.isLetterOrDigit(s.charAt(right))) {
            right--;
        }

        // Compare characters (case-insensitive)
        if (Character.toLowerCase(s.charAt(left)) !=
            Character.toLowerCase(s.charAt(right))) {
            return false; // Characters don't match
        }
        left++;  // Move pointers inward
        right--;
    }
    return true; // All checked pairs matched
}
// Time Complexity: O(n) - Each pointer traverses at most n/2 characters.
// Space Complexity: O(1) - Only a few variables are used.

// Two Pointers (Same Direction, Different Speeds) - Container With Most Water
// Given an array of non-negative integers representing heights of vertical lines,
// find two lines that, together with the x-axis, form a container that holds the most water.
public int maxArea(int[] height) {
    if (height == null || height.length < 2) return 0;

    int left = 0, right = height.length - 1; // Pointers at the start and end
    int maxWater = 0;

    while (left < right) {
        // Calculate current area: width * min_height
        int currentHeight = Math.min(height[left], height[right]);
        int currentWidth = right - left;
        int currentWater = currentHeight * currentWidth;
        maxWater = Math.max(maxWater, currentWater);

        // Move the pointer pointing to the shorter line inward.
        // Why? The area is limited by the shorter line. Moving the shorter line's pointer
        // gives a chance to find a taller line, potentially increasing the height and thus area.
        // Moving the taller line's pointer inward will definitely decrease the width,
        // and the height will either stay the same or decrease, so the area cannot increase.
        if (height[left] < height[right]) {
            left++;
        } else {
            right--;
        }
    }
    return maxWater;
}
// Time Complexity: O(n) - Each pointer traverses the array once.
// Space Complexity: O(1) - Constant extra space.
```

#### Sliding Window Technique
**Conceptual Explanation:**
The sliding window technique is used for problems that involve finding a subarray or substring satisfying certain conditions. A "window" of a certain size (fixed or variable) slides over the data. Instead of re-computing for every possible subarray (which could be O(n²)), we efficiently update the result by adding a new element to one end of the window and removing an element from the other end.

**When to Use:**
*   Problems asking for the longest/shortest subarray/substring with a property.
*   Problems involving finding a subarray/substring with a specific sum or count of elements.
*   Problems where you need to analyze contiguous segments of data.

**Types:**
1.  **Fixed-Size Window:** The window size `k` is predetermined.
2.  **Variable-Size Window:** The window size changes based on conditions within the window. The goal is often to find the smallest or largest window that satisfies a property.

**Code Snippets & Explanations:**

```java
// Fixed Size Sliding Window - Maximum Sum Subarray of Size K
// Finds the maximum sum of any contiguous subarray of size 'k'.
public int maxSumSubarrayFixed(int[] arr, int k) {
    if (arr == null || arr.length < k || k <= 0) {
        // Or throw IllegalArgumentException for invalid inputs
        return (arr == null || arr.length == 0) ? 0 : -1; // Example error handling
    }

    // Calculate sum of the first window
    int windowSum = 0;
    for (int i = 0; i < k; i++) {
        windowSum += arr[i];
    }

    int maxSum = windowSum; // Initialize maxSum with the sum of the first window

    // Slide the window from left to right
    // windowStart is the index of the element being removed from the window
    // windowEnd is the index of the element being added to the window
    for (int windowEnd = k; windowEnd < arr.length; windowEnd++) {
        // Subtract the element going out of the window, add the element coming into the window
        windowSum = windowSum - arr[windowEnd - k] + arr[windowEnd];
        maxSum = Math.max(maxSum, windowSum); // Update maxSum
    }

    return maxSum;
}
// Time Complexity: O(n) - We iterate through the array once.
// Space Complexity: O(1) - Constant extra space.

// Variable Size Sliding Window - Longest Substring Without Repeating Characters
// Finds the length of the longest substring without repeating characters.
public int lengthOfLongestSubstring(String s) {
    if (s == null || s.length() == 0) return 0;

    Set<Character> windowChars = new HashSet<>(); // Stores characters in the current window
    int windowStart = 0; // Left pointer of the window
    int maxLength = 0;

    // windowEnd is the right pointer of the window
    for (int windowEnd = 0; windowEnd < s.length(); windowEnd++) {
        char charToAdd = s.charAt(windowEnd);

        // If the character is already in the window, shrink the window from the left
        // until the duplicate character is removed.
        while (windowChars.contains(charToAdd)) {
            char charToRemove = s.charAt(windowStart);
            windowChars.remove(charToRemove);
            windowStart++;
        }

        // Add the new character to the window
        windowChars.add(charToAdd);
        // Update maxLength with the size of the current valid window
        maxLength = Math.max(maxLength, windowEnd - windowStart + 1);
    }

    return maxLength;
}
// Time Complexity: O(n) - Although there's a nested while loop, each character is added to
// and removed from the set at most once. So, both windowStart and windowEnd pointers
// traverse the string at most 'n' times.
// Space Complexity: O(min(m, n)) - Where 'n' is the length of the string and 'm' is the
// size of the character set (e.g., 26 for lowercase English letters, or up to 'n' if all
// characters are unique). This is for storing characters in the HashSet.
```

#### Prefix Sum Technique
**Conceptual Explanation:**
The prefix sum technique involves pre-calculating the cumulative sum of elements in an array. A new array (the prefix sum array) is created where `prefixSum[i]` stores the sum of all elements from the original array's index 0 up to `i-1` (or `i`, depending on implementation). This preprocessing allows for O(1) time calculation of the sum of any subarray.

**When to Use:**
*   Problems requiring frequent calculation of sums of subarrays (range sum queries).
*   Problems where the difference between two prefix sums can reveal a property (e.g., subarray sum equals K).

**Preprocessing:** `prefixSum[i] = array + array + ... + array[i-1]`
**Range Sum Query (sum from index `L` to `R` inclusive):** `array[L] + ... + array[R] = prefixSum[R+1] - prefixSum[L]`

**Code Snippets & Explanations:**
```java
// Class for Prefix Sum operations
class PrefixSum {
    private int[] prefixSumArray; // Stores the prefix sums

    // Constructor: Preprocesses the input array to create the prefix sum array.
    // prefixSumArray[0] = 0 (optional, but simplifies rangeSum calculation)
    // prefixSumArray[i] stores sum of nums[0]...nums[i-1]
    public PrefixSum(int[] nums) {
        if (nums == null) {
            // Or initialize with an empty array, or throw exception
            this.prefixSumArray = new int[1];
            return;
        }
        this.prefixSumArray = new int[nums.length + 1];
        // prefixSumArray[0] is typically 0 to make range sum calculation easier.
        // prefixSumArray[i] will store the sum of elements from index 0 to i-1 in `nums`.
        for (int i = 0; i < nums.length; i++) {
            prefixSumArray[i + 1] = prefixSumArray[i] + nums[i];
        }
    }

    // Get sum of elements from index left to right (inclusive) in the original array.
    // This corresponds to prefixSumArray[right + 1] - prefixSumArray[left].
    public int rangeSum(int left, int right) {
        if (left < 0 || right + 1 >= prefixSumArray.length || left > right) {
            throw new IllegalArgumentException("Invalid range.");
        }
        // Sum(nums[left...right]) = Sum(nums[0...right]) - Sum(nums[0...left-1])
        // This translates to prefixSumArray[right+1] - prefixSumArray[left]
        return prefixSumArray[right + 1] - prefixSumArray[left];
    }
}
// Preprocessing Time: O(n) - To build the prefixSumArray.
// Range Sum Query Time: O(1) - After preprocessing.
// Space Complexity: O(n) - To store the prefixSumArray.

// Example: Subarray Sum Equals K
// Given an array of integers and an integer k, find the total number of continuous
// subarrays whose sum equals to k.
public int subarraySum(int[] nums, int k) {
    if (nums == null || nums.length == 0) return 0;

    // Stores the frequency of each prefix sum encountered.
    // Key: prefix sum, Value: count of occurrences of this prefix sum.
    Map<Integer, Integer> prefixSumCount = new HashMap<>();
    // Important: A prefix sum of 0 has occurred once (the empty prefix).
    // This handles cases where a subarray starting from index 0 sums to k.
    prefixSumCount.put(0, 1);

    int count = 0;         // Result: number of subarrays summing to k
    int currentSum = 0;    // Current prefix sum as we iterate through nums

    for (int num : nums) {
        currentSum += num; // Update current prefix sum

        // We are looking for previous prefix sums `prevSum` such that:
        // currentSum - prevSum = k
        // Which means: prevSum = currentSum - k
        // If such `prevSum` exists in our map, it means there were `prefixSumCount.get(currentSum - k)`
        // subarrays ending just before the start of the current element, which, when combined with
        // the elements up to the current one, form a subarray summing to k.
        if (prefixSumCount.containsKey(currentSum - k)) {
            count += prefixSumCount.get(currentSum - k);
        }

        // Add/update the frequency of the currentSum in the map.
        prefixSumCount.put(currentSum, prefixSumCount.getOrDefault(currentSum, 0) + 1);
    }

    return count;
}
// Time Complexity: O(n) - We iterate through the array once. HashMap operations (put, get, containsKey)
// take O(1) on average.
// Space Complexity: O(n) - In the worst case, the HashMap can store up to 'n' distinct prefix sums.
```

### Advanced Array Problems

These problems often combine basic techniques or require clever insights.

```java
// Rotate Array - Multiple Approaches
// Rotate an array to the right by k steps.
public void rotate(int[] nums, int k) {
    if (nums == null || nums.length == 0 || k < 0) {
        // Or throw IllegalArgumentException
        return;
    }
    int n = nums.length;
    k = k % n; // Handle cases where k >= n. Rotation by n is same as 0.

    // Approach 1: Reverse entire array, then reverse parts (most common and efficient in-place)
    // 1. Reverse all numbers:      nums becomes [n, n-1, ..., k+1, k, ..., 1]
    // 2. Reverse first k numbers:  [k, ..., 1] portion becomes [1, ..., k]
    //                            Resulting in [1, ..., k, n, n-1, ..., k+1] (incorrect state for right rotate)
    // Let's adjust for right rotation:
    // Original: [1, 2, 3, 4, 5, 6, 7], k = 3 -> Expected: [5, 6, 7, 1, 2, 3, 4]
    // 1. Reverse all: [7, 6, 5, 4, 3, 2, 1]
    // 2. Reverse first k elements (0 to k-1): [5, 6, 7, 4, 3, 2, 1] (Here k is 3, elements are 7,6,5)
    // 3. Reverse last n-k elements (k to n-1): [5, 6, 7, 1, 2, 3, 4] (Elements 4,3,2,1 reversed)
    reverse(nums, 0, n - 1);       // Reverse entire array
    reverse(nums, 0, k - 1);       // Reverse first k elements
    reverse(nums, k, n - 1);       // Reverse remaining n-k elements
}

// Helper function to reverse a portion of an array in place.
private void reverse(int[] nums, int start, int end) {
    while (start < end) {
        int temp = nums[start];
        nums[start] = nums[end];
        nums[end] = temp;
        start++;
        end--;
    }
}
// Time Complexity: O(n) - Each element is reversed a constant number of times (at most 3 times).
// Space Complexity: O(1) - In-place modification.

/* Other approaches for Rotate Array (less common in interviews if O(1) space is required):
   1. Using an auxiliary array: Copy elements to a new array at their rotated positions. O(n) time, O(n) space.
   2. Cyclic Replacements: Move elements one by one to their correct rotated position. This can be tricky to implement correctly to handle all cycles. O(n) time, O(1) space.
*/

// Product of Array Except Self - No Division Allowed
// Given an integer array nums, return an array answer such that answer[i] is equal to
// the product of all the elements of nums except nums[i].
// Constraint: Do not use the division operator.
public int[] productExceptSelf(int[] nums) {
    if (nums == null || nums.length == 0) return new int[0];
    int n = nums.length;
    int[] result = new int[n];

    // First pass: Calculate left products
    // result[i] will store the product of all elements to the left of nums[i].
    // result[0] has no elements to its left, so its left product is 1.
    result[0] = 1;
    for (int i = 1; i < n; i++) {
        result[i] = result[i - 1] * nums[i - 1];
    }

    // Second pass: Calculate right products and multiply with left products
    // rightProduct stores the product of all elements to the right of the current nums[i].
    int rightProduct = 1;
    // Iterate from right to left.
    for (int i = n - 1; i >= 0; i--) {
        // result[i] currently holds the product of elements to its left.
        // Multiply it by the product of elements to its right (rightProduct).
        result[i] = result[i] * rightProduct;
        // Update rightProduct for the next element to the left.
        rightProduct *= nums[i];
    }

    return result;
}
// Time Complexity: O(n) - Two passes through the array.
// Space Complexity: O(1) - If the output array `result` is not counted as extra space (common interview assumption).
// If it is counted, then O(n) space.
```

---
## 3. Linked Lists

Linked lists are fundamental linear data structures composed of nodes, where each node contains data and a pointer (or link) to the next node in the sequence. They are dynamic in size and offer efficient insertions/deletions compared to arrays, but lack O(1) random access.

**Conceptual Explanation:**
*   **Node:** The basic building block, typically containing:
    *   `data`: The value stored in the node.
    *   `next`: A reference/pointer to the next node in the list. For the last node, `next` is usually `null`.
*   **Head:** A special pointer that points to the first node of the list. If the list is empty, `head` is `null`.
*   **Dynamic Size:** Linked lists can grow or shrink during runtime as nodes are added or removed.
*   **Non-contiguous Memory:** Unlike arrays, nodes in a linked list can be scattered in memory; they are linked together by pointers.

### Singly Linked Lists
Each node has data and a pointer to the *next* node only. Traversal is unidirectional (forward).

### Doubly Linked Lists (Conceptual)
Each node has data, a pointer to the *next* node, and a pointer to the *previous* node. This allows for bidirectional traversal.
*   **Node Structure:** `data`, `next`, `prev`.
*   **Advantages:**
    *   Can be traversed in both forward and backward directions.
    *   Deletion can be more efficient if a pointer to the node to be deleted is given (don't need to find the previous node).
*   **Disadvantages:**
    *   Requires more space per node (for the `prev` pointer).
    *   Insertions and deletions are slightly more complex due to managing two pointers per node.

### Circular Linked Lists (Conceptual)
The `next` pointer of the last node points back to the `head` node, forming a circle.
*   Can be singly or doubly circular.
*   **Advantages:**
    *   Any node can be a starting point.
    *   Useful for applications that require round-robin scheduling or a continuous loop of items.
*   **Disadvantages:**
    *   Care must be taken to avoid infinite loops during traversal if not handled correctly.

### Basic Linked List Operations (for Singly Linked List)

```java
// Definition for a singly-linked list node.
class ListNode {
    int val;      // Data stored in the node
    ListNode next; // Pointer to the next node

    ListNode() {} // Default constructor
    ListNode(int val) { this.val = val; this.next = null; } // Constructor with value
    ListNode(int val, ListNode next) { this.val = val; this.next = next; } // Constructor with value and next node
}

// Basic LinkedList class demonstrating operations
class LinkedList {
    private ListNode head; // Head of the list

    public LinkedList() {
        this.head = null;
    }

    // Insert at the beginning of the list
    // Time Complexity: O(1)
    public void insertAtBeginning(int val) {
        ListNode newNode = new ListNode(val); // Create a new node
        newNode.next = head;                  // New node points to the current head
        head = newNode;                       // Update head to be the new node
    }

    // Insert at the end of the list
    // Time Complexity: O(n) - requires traversal to the last node
    public void insertAtEnd(int val) {
        ListNode newNode = new ListNode(val);
        if (head == null) { // If the list is empty, new node becomes the head
            head = newNode;
            return;
        }
        ListNode current = head;
        while (current.next != null) { // Traverse to the last node
            current = current.next;
        }
        current.next = newNode; // Last node points to the new node
    }

    // Delete a node with a given value (first occurrence)
    // Time Complexity: O(n) - requires traversal to find the node
    public void delete(int val) {
        if (head == null) return; // List is empty

        // If the head node itself holds the value to be deleted
        if (head.val == val) {
            head = head.next; // Change head
            return;
        }

        // Search for the node to be deleted, keep track of the previous node
        ListNode current = head;
        ListNode prev = null;
        while (current != null && current.val != val) {
            prev = current;
            current = current.next;
        }

        // If the value was not present in the list
        if (current == null) return;

        // Unlink the node from the linked list
        if (prev != null) {
            prev.next = current.next;
        }
    }

    // Search for a node with a given value
    // Time Complexity: O(n)
    public ListNode search(int val) {
        ListNode current = head;
        while(current != null) {
            if (current.val == val) {
                return current; // Node found
            }
            current = current.next;
        }
        return null; // Node not found
    }

    // Display the contents of the list
    // Time Complexity: O(n)
    public void display() {
        ListNode current = head;
        while (current != null) {
            System.out.print(current.val + " -> ");
            current = current.next;
        }
        System.out.println("null");
    }
}
```

**Advantages of Linked Lists (over arrays):**
*   **Dynamic Size:** Can easily grow and shrink.
*   **Efficient Insertions/Deletions:** O(1) if the pointer to the previous node (or the node itself for some operations) is known, as no shifting of elements is needed.

**Disadvantages of Linked Lists (compared to arrays):**
*   **No Random Access:** O(n) to access an element at a specific index, as traversal from the head is required.
*   **Extra Memory:** Each node requires extra space for the `next` pointer (and `prev` for doubly linked lists).
*   **Cache Performance:** Nodes may not be in contiguous memory locations, potentially leading to poorer cache performance compared to arrays.

### Classic Linked List Problems

#### Reverse Linked List
**Conceptual Explanation:** This involves changing the direction of `next` pointers for all nodes so the list flows in the opposite direction. The last node becomes the new head.

```java
// Iterative Approach - Reverse Linked List
// Time Complexity: O(n) - Traverses the list once.
// Space Complexity: O(1) - Uses a few pointers, constant extra space.
public ListNode reverseListIterative(ListNode head) {
    ListNode prev = null;    // Will store the previous node, initially null (new tail)
    ListNode current = head; // Start with the current head
    ListNode nextTemp = null;  // Temporary store for the next node

    while (current != null) {
        nextTemp = current.next; // Store the next node before overwriting current.next
        current.next = prev;      // Reverse the link: current node now points to 'prev'
        prev = current;           // Move 'prev' one step forward to the current node
        current = nextTemp;       // Move 'current' one step forward to the originally next node
    }

    return prev; // 'prev' is now the new head of the reversed list
}

// Recursive Approach - Reverse Linked List
// Time Complexity: O(n) - Visits each node once.
// Space Complexity: O(n) - Due to the recursion call stack (depth of n).
public ListNode reverseListRecursive(ListNode head) {
    // Base case: If the list is empty or has only one node, it's already reversed.
    if (head == null || head.next == null) {
        return head;
    }

    // Recursively reverse the rest of the list (from head.next onwards).
    // `newHead` will be the head of the reversed sublist.
    ListNode newHead = reverseListRecursive(head.next);

    // After the recursive call returns, `head.next` is the last node of the reversed sublist.
    // We want this node (which was originally head.next) to point back to `head`.
    head.next.next = head;
    // `head` should now be the new tail of this part, so its `next` should be null.
    head.next = null;

    return newHead; // The `newHead` obtained from the deepest recursion is the overall new head.
}
```

#### Detect Cycle in Linked List
**Conceptual Explanation:** Floyd's Cycle Detection Algorithm (also known as the "Tortoise and Hare" algorithm) uses two pointers, one moving one step at a time (slow) and the other moving two steps at a time (fast). If there's a cycle, the fast pointer will eventually lap the slow pointer.

```java
// Detect if a cycle exists in a linked list.
// Time Complexity: O(n) - In the worst case (list with no cycle), fast pointer reaches the end.
// If there is a cycle, they meet within the cycle.
// Space Complexity: O(1) - Constant extra space for two pointers.
public boolean hasCycle(ListNode head) {
    if (head == null || head.next == null) return false; // No cycle if 0 or 1 node

    ListNode slow = head;    // Tortoise: moves one step
    ListNode fast = head;    // Hare: moves two steps

    // Traverse until fast pointer reaches the end or meets slow pointer
    while (fast != null && fast.next != null) {
        slow = slow.next;        // Move slow pointer by one
        fast = fast.next.next;   // Move fast pointer by two

        if (slow == fast) {      // If pointers meet, a cycle is detected
            return true;
        }
    }

    return false; // If fast pointer reaches null, no cycle
}

// Find the starting node of the cycle if one exists.
// Time Complexity: O(n)
// Space Complexity: O(1)
public ListNode detectCycleStartNode(ListNode head) {
    if (head == null || head.next == null) return null;

    ListNode slow = head;
    ListNode fast = head;
    boolean cycleExists = false;

    // Phase 1: Detect if a cycle exists and find the meeting point.
    while (fast != null && fast.next != null) {
        slow = slow.next;
        fast = fast.next.next;
        if (slow == fast) {
            cycleExists = true;
            break;
        }
    }

    if (!cycleExists) {
        return null; // No cycle
    }

    // Phase 2: Find the start of the cycle.
    // Reset one pointer (e.g., slow) to the head. Keep the other (fast) at the meeting point.
    // Move both pointers one step at a time. They will meet at the cycle's start node.
    // Why this works:
    // Let L = length of non-cyclic part, C = length of cycle.
    // Let k = distance from cycle start to meeting point.
    // When they meet:
    // Distance by slow = L + k
    // Distance by fast = L + k + m*C (m full cycles)
    // Also, Distance by fast = 2 * Distance by slow
    // So, L + k + m*C = 2 * (L + k)  => L + k = m*C
    // This means L = m*C - k.
    // If we move one pointer from head (L steps to cycle start) and another from meeting point
    // (which is k steps into cycle, so C-k steps to cycle start, or m*C - k steps), they meet.
    slow = head;
    while (slow != fast) {
        slow = slow.next;
        fast = fast.next;
    }

    return slow; // This is the start of the cycle
}
```

#### Merge Two Sorted Lists
**Conceptual Explanation:** Given two sorted linked lists, merge them into a single sorted linked list.

```java
// Iterative approach to merge two sorted linked lists.
// Time Complexity: O(m + n) - where m and n are the lengths of list1 and list2.
// We traverse each list once.
// Space Complexity: O(1) - If we reuse existing nodes. O(m+n) if we create new nodes for result.
// The dummy node itself is O(1).
public ListNode mergeTwoListsIterative(ListNode list1, ListNode list2) {
    // Create a dummy node to act as a placeholder for the head of the merged list.
    // This simplifies edge cases like an empty merged list or inserting the first element.
    ListNode dummy = new ListNode(0);
    ListNode current = dummy; // 'current' will build the new list.

    // Traverse both lists as long as neither is exhausted.
    while (list1 != null && list2 != null) {
        if (list1.val <= list2.val) {
            current.next = list1; // Append smaller node from list1
            list1 = list1.next;   // Move list1 pointer
        } else {
            current.next = list2; // Append smaller node from list2
            list2 = list2.next;   // Move list2 pointer
        }
        current = current.next;   // Move current pointer in the merged list
    }

    // If one list is exhausted, append the remaining part of the other list.
    // At most one of these will be non-null.
    current.next = (list1 != null) ? list1 : list2;

    return dummy.next; // The merged list starts after the dummy node.
}

// Recursive approach to merge two sorted linked lists.
// Time Complexity: O(m + n)
// Space Complexity: O(m + n) - Due to the recursion call stack.
public ListNode mergeTwoListsRecursive(ListNode list1, ListNode list2) {
    // Base cases: if one list is empty, return the other.
    if (list1 == null) return list2;
    if (list2 == null) return list1;

    ListNode result;
    if (list1.val <= list2.val) {
        result = list1; // list1's current node is smaller
        // Recursively merge the rest of list1 with list2.
        result.next = mergeTwoListsRecursive(list1.next, list2);
    } else {
        result = list2; // list2's current node is smaller
        // Recursively merge list1 with the rest of list2.
        result.next = mergeTwoListsRecursive(list1, list2.next);
    }
    return result;
}
```

### Advanced Linked List Problems

```java
// Remove Nth Node From End of List - One Pass Solution
// Conceptual Explanation: Use two pointers. Advance the first pointer `n+1` steps.
// Then, advance both pointers simultaneously until the first pointer reaches the end.
// The second pointer will then be at the node just before the Nth node from the end.
public ListNode removeNthFromEnd(ListNode head, int n) {
    // Dummy node helps handle edge cases, like removing the head itself.
    ListNode dummy = new ListNode(0);
    dummy.next = head;

    ListNode first = dummy;  // Fast pointer
    ListNode second = dummy; // Slow pointer, will point to node before target

    // Move 'first' pointer n+1 steps ahead.
    // This creates a gap of 'n' nodes between 'first' and 'second'.
    for (int i = 0; i <= n; i++) {
        if (first == null) { // Should not happen if n is valid (<= list length)
            // Or throw exception for invalid n if n > length
            return head; // Or dummy.next if problem statement guarantees valid n
        }
        first = first.next;
    }

    // Move both pointers until 'first' reaches the end of the list (null).
    // When 'first' is null, 'second' will be pointing to the (n+1)th node from the end,
    // which is the node *before* the Nth node from the end.
    while (first != null) {
        first = first.next;
        second = second.next;
    }

    // 'second' is now at the node before the one to be removed.
    // Skip the Nth node from the end.
    if (second != null && second.next != null) {
        second.next = second.next.next;
    }

    return dummy.next; // Return the head of the modified list.
}
// Time Complexity: O(L) - where L is the length of the list. Single pass.
// Space Complexity: O(1) - Constant extra space.

// Add Two Numbers (represented as linked lists in reverse order)
// Each node contains a single digit. The digits are stored in reverse order.
// Example: l1 = [2,4,3] (represents 342), l2 = [5,6,4] (represents 465)
// Output: [7,0,8] (represents 807)
public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
    ListNode dummyHead = new ListNode(0); // Dummy head for the result list
    ListNode current = dummyHead;      // Pointer to build the result list
    int carry = 0;                     // Carry-over from the previous sum

    // Iterate as long as there are digits in l1 or l2, or there's a carry.
    while (l1 != null || l2 != null || carry != 0) {
        int sum = carry; // Start sum with the carry from the previous digit addition

        if (l1 != null) {
            sum += l1.val; // Add l1's digit if available
            l1 = l1.next;  // Move to next digit in l1
        }

        if (l2 != null) {
            sum += l2.val; // Add l2's digit if available
            l2 = l2.next;  // Move to next digit in l2
        }

        carry = sum / 10;          // Calculate the new carry (0 or 1)
        int digit = sum % 10;      // Calculate the digit for the current position
        current.next = new ListNode(digit); // Create a new node with the digit
        current = current.next;          // Move current pointer in the result list
    }

    return dummyHead.next; // The result list starts after the dummy head.
}
// Time Complexity: O(max(m, n)) - where m and n are the lengths of l1 and l2.
// We iterate up to the length of the longer list.
// Space Complexity: O(max(m, n)) - The length of the new list is at most max(m,n) + 1.
```

---
## 4. Stacks & Queues

Stacks and Queues are linear data structures that follow specific ordering principles for adding and removing elements.

### Stacks
**Conceptual Explanation:**
A Stack is a Last-In, First-Out (LIFO) data structure. The last element added to the stack is the first one to be removed. Think of a stack of plates.
*   **Operations:**
    *   `push(item)`: Adds an item to the top of the stack. (O(1))
    *   `pop()`: Removes and returns the item from the top of the stack. (O(1))
    *   `peek()` or `top()`: Returns the item at the top without removing it. (O(1))
    *   `isEmpty()`: Checks if the stack is empty. (O(1))
    *   `size()`: Returns the number of items in the stack. (O(1))
*   **Applications:**
    *   Function call management (call stack).
    *   Parsing expressions (e.g., checking for balanced parentheses).
    *   Undo/Redo functionality in applications.
    *   Depth-First Search (DFS) in graphs.
    *   Backtracking algorithms.

**Implementations:**
1.  **Array-based:** Uses an array to store elements. A `top` pointer tracks the index of the top element. Can suffer from overflow if fixed-size or require resizing if dynamic.
2.  **Linked List-based:** Each element is a node. `push` adds to the head, `pop` removes from the head. More flexible with size.

#### Stack Implementation and Applications

```java
// Stack implementation using array (fixed capacity for simplicity)
class ArrayStack<T> {
    private T[] stackArray;
    private int top;          // Index of the top element
    private int capacity;     // Maximum capacity of the stack

    @SuppressWarnings("unchecked") // Suppress warning for generic array creation
    public ArrayStack(int capacity) {
        this.capacity = capacity;
        this.stackArray = (T[]) new Object[capacity]; // Generic array creation
        this.top = -1; // Stack is initially empty
    }

    // Pushes an item onto the top of this stack.
    public void push(T item) {
        if (isFull()) {
            throw new RuntimeException("Stack overflow: Cannot push item, stack is full.");
        }
        stackArray[++top] = item; // Increment top, then add item
    }

    // Removes the object at the top of this stack and returns that object.
    public T pop() {
        if (isEmpty()) {
            throw new RuntimeException("Stack underflow: Cannot pop item, stack is empty.");
        }
        T item = stackArray[top];
        stackArray[top--] = null; // Dereference to help garbage collector, then decrement top
        return item;
    }

    // Looks at the object at the top of this stack without removing it.
    public T peek() {
        if (isEmpty()) {
            throw new RuntimeException("Stack is empty: Cannot peek item.");
        }
        return stackArray[top];
    }

    // Tests if this stack is empty.
    public boolean isEmpty() {
        return top == -1;
    }

    // Tests if this stack is full.
    public boolean isFull() {
        return top == capacity - 1;
    }

    // Returns the number of elements in this stack.
    public int size() {
        return top + 1;
    }
}

// --- Stack Applications ---

// Valid Parentheses - Classic Stack Problem
// Given a string s containing just the characters '(', ')', '{', '}', '[' and ']',
// determine if the input string is valid.
public boolean isValidParentheses(String s) {
    if (s == null) return false;
    Stack<Character> stack = new Stack<>(); // Use Java's built-in Stack
    // Map closing brackets to their corresponding opening brackets
    Map<Character, Character> mapping = new HashMap<>();
    mapping.put(')', '(');
    mapping.put('}', '{');
    mapping.put(']', '[');

    for (char c : s.toCharArray()) {
        if (mapping.containsKey(c)) { // If it's a closing bracket
            // Pop the top element from the stack if it's not empty, otherwise assign a dummy value
            char topElement = stack.isEmpty() ? '#' : stack.pop();
            // If the popped opening bracket doesn't match the current closing bracket, it's invalid
            if (topElement != mapping.get(c)) {
                return false;
            }
        } else { // If it's an opening bracket, push it onto the stack
            stack.push(c);
        }
    }
    // If the stack is empty at the end, all opening brackets had matching closing brackets.
    return stack.isEmpty();
}
// Time Complexity: O(n) - We iterate through the string once. Stack operations are O(1).
// Space Complexity: O(n) - In the worst case (e.g., "((((("))), the stack can store all opening brackets.

// Daily Temperatures - Monotonic Stack Application
// Given an array of integers temperatures representing daily temperatures, return an array answer
// such that answer[i] is the number of days you have to wait after the ith day to get a
// warmer temperature. If there is no future day for which this is possible, keep answer[i] == 0.
public int[] dailyTemperatures(int[] temperatures) {
    int n = temperatures.length;
    int[] result = new int[n]; // Initialize with 0s by default
    // Stack stores indices of temperatures for which we are still seeking a warmer day.
    // It maintains indices of temperatures in decreasing order (monotonic decreasing stack).
    Stack<Integer> stack = new Stack<>();

    for (int i = 0; i < n; i++) {
        // While stack is not empty and current temperature is warmer than temperature at stack's top index
        while (!stack.isEmpty() && temperatures[i] > temperatures[stack.peek()]) {
            int prevIndex = stack.pop(); // Index of the day for which we found a warmer day
            result[prevIndex] = i - prevIndex; // Calculate the number of days to wait
        }
        // Push current day's index onto the stack. It might be a candidate for a future warmer day.
        stack.push(i);
    }
    // Any indices remaining in the stack didn't find a warmer day, result[index] remains 0.
    return result;
}
// Time Complexity: O(n) - Each element is pushed and popped from the stack at most once.
// Space Complexity: O(n) - In the worst case (e.g., temperatures are strictly decreasing),
// the stack can store all indices.
```

#### Advanced Stack Applications

```java
// Largest Rectangle in Histogram - Advanced Stack Problem
// Given an array of integers heights representing the histogram's bar height where the width of each bar is 1,
// return the area of the largest rectangle in the histogram.
public int largestRectangleArea(int[] heights) {
    if (heights == null || heights.length == 0) return 0;

    // Stack stores indices of bars. The heights corresponding to these indices
    // are maintained in increasing order (monotonic increasing stack).
    Stack<Integer> stack = new Stack<>();
    int maxArea = 0;
    int n = heights.length;

    // Iterate through all bars, including a conceptual bar of height 0 at the end
    // to process any remaining bars in the stack.
    for (int i = 0; i <= n; i++) {
        // If i == n, currentHeight is 0 (the conceptual bar).
        // Otherwise, it's the height of the current bar.
        int currentHeight = (i == n) ? 0 : heights[i];

        // While stack is not empty AND the bar at stack.peek() is taller than currentHeight:
        // This means the bar at stack.peek() cannot extend further to the right with its current height.
        // So, we pop it and calculate the area of the rectangle with this bar as the smallest height.
        while (!stack.isEmpty() && heights[stack.peek()] > currentHeight) {
            int height = heights[stack.pop()]; // Height of the popped bar (smallest in this rectangle)
            // Width calculation:
            // If stack is empty, the rectangle extends from index 0 to i-1. Width = i.
            // Else, the rectangle extends from (stack.peek() + 1) to (i-1). Width = i - stack.peek() - 1.
            int width = stack.isEmpty() ? i : i - stack.peek() - 1;
            maxArea = Math.max(maxArea, height * width);
        }
        // Push the current bar's index onto the stack.
        stack.push(i);
    }
    return maxArea;
}
// Time Complexity: O(n) - Each bar index is pushed and popped at most once.
// Space Complexity: O(n) - Stack can store up to n indices in the worst case (e.g., heights are sorted).

// Implement Queue using Stacks
// Implement a first in first out (FIFO) queue using only two stacks.
class MyQueue {
    private Stack<Integer> inputStack;  // Used for enqueue operations
    private Stack<Integer> outputStack; // Used for dequeue and peek operations

    public MyQueue() {
        inputStack = new Stack<>();
        outputStack = new Stack<>();
    }

    // Push element x to the back of queue.
    // Time Complexity: O(1)
    public void push(int x) {
        inputStack.push(x);
    }

    // Removes the element from in front of queue and returns that element.
    // Time Complexity: Amortized O(1). Worst case O(n) if outputStack is empty and needs refilling.
    public int pop() {
        peek(); // Ensure outputStack has elements if needed
        return outputStack.pop();
    }

    // Get the front element.
    // Time Complexity: Amortized O(1). Worst case O(n) if outputStack is empty and needs refilling.
    public int peek() {
        // If outputStack is empty, transfer all elements from inputStack to outputStack.
        // This reverses the order, making the oldest element in inputStack the top of outputStack.
        if (outputStack.isEmpty()) {
            while (!inputStack.isEmpty()) {
                outputStack.push(inputStack.pop());
            }
        }
        if (outputStack.isEmpty()) { // Should not happen if queue was not empty
            throw new RuntimeException("Queue is empty");
        }
        return outputStack.peek();
    }

    // Returns whether the queue is empty.
    // Time Complexity: O(1)
    public boolean empty() {
        return inputStack.isEmpty() && outputStack.isEmpty();
    }
}
// Amortized Analysis for pop/peek: Each element is pushed onto inputStack once (O(1)),
// popped from inputStack once (O(1)), pushed onto outputStack once (O(1)), and
// popped from outputStack once (O(1)). So, over 'n' operations, the total time is O(n).
// Thus, the amortized time per operation is O(1).
```

### Queues
**Conceptual Explanation:**
A Queue is a First-In, First-Out (FIFO) data structure. The first element added to the queue is the first one to be removed. Think of a checkout line at a store.
*   **Operations:**
    *   `enqueue(item)` or `offer(item)`: Adds an item to the rear (end) of the queue. (O(1))
    *   `dequeue()` or `poll()`: Removes and returns the item from the front of the queue. (O(1))
    *   `peek()` or `element()`: Returns the item at the front without removing it. (O(1))
    *   `isEmpty()`: Checks if the queue is empty. (O(1))
    *   `size()`: Returns the number of items in the queue. (O(1))
*   **Applications:**
    *   Breadth-First Search (BFS) in graphs.
    *   Task scheduling in operating systems.
    *   Print job queuing.
    *   Buffering data streams.

**Implementations:**
1.  **Array-based (Circular Queue):** Uses an array and two pointers, `front` and `rear`. To avoid wastage and handle wrap-around, it's implemented as a circular array.
2.  **Linked List-based:** Uses a linked list with `head` (front) and `tail` (rear) pointers. `enqueue` adds to the tail, `dequeue` removes from the head.

#### Queue Implementation and Applications

```java
// --- Queue Applications ---
// (Using Java's built-in LinkedList as a Queue for simplicity in applications)
// For custom implementation, see CircularQueue below.

// Sliding Window Maximum - Deque Application
// Given an array nums, there is a sliding window of size k which is moving from the
// very left of the array to the very right. You can only see the k numbers in the window.
// Each time the sliding window moves right by one position. Return the max sliding window.
public int[] maxSlidingWindow(int[] nums, int k) {
    if (nums == null || nums.length == 0 || k <= 0 || k > nums.length) {
        return new int[0]; // Or throw exception for invalid input
    }

    int n = nums.length;
    int[] result = new int[n - k + 1]; // Number of windows
    int resultIndex = 0;

    // Deque stores indices of elements in the current window.
    // It's maintained such that elements are in decreasing order of their values in nums.
    // The front of the deque always holds the index of the maximum element in the current window.
    Deque<Integer> deque = new LinkedList<>();

    for (int i = 0; i < n; i++) {
        // 1. Remove indices from the front that are out of the current window's bounds.
        // The window is [i - k + 1, i].
        if (!deque.isEmpty() && deque.peekFirst() < i - k + 1) {
            deque.pollFirst();
        }

        // 2. Maintain decreasing order in deque: Remove indices from the rear whose
        // corresponding elements are smaller than or equal to the current element nums[i].
        // These smaller elements can no longer be the maximum in any future window that includes nums[i].
        while (!deque.isEmpty() && nums[deque.peekLast()] < nums[i]) {
            deque.pollLast();
        }

        // 3. Add the current element's index to the rear of the deque.
        deque.offerLast(i);

        // 4. Once the window is fully formed (i.e., i >= k - 1),
        // the maximum for the current window is at the front of the deque.
        if (i >= k - 1) {
            result[resultIndex++] = nums[deque.peekFirst()];
        }
    }
    return result;
}
// Time Complexity: O(n) - Each element is added to and removed from the deque at most once.
// Space Complexity: O(k) - The deque stores at most 'k' indices.
```

#### Circular Queues
**Conceptual Explanation:** An array-based queue where the `rear` pointer wraps around to the beginning of the array if it reaches the end, effectively making the array circular. This avoids the issue of a "full" queue that still has empty slots at the beginning after several dequeues (which happens in a naive array queue). It uses `front` and `rear` pointers, and often a `size` variable or careful modulo arithmetic.

```java
// Queue implementation using a circular array.
class CircularQueue<T> {
    private T[] queueArray;
    private int front;      // Index of the front element
    private int rear;       // Index of the position *after* the last element
    private int size;       // Current number of elements in the queue
    private int capacity;   // Maximum capacity of the queue

    @SuppressWarnings("unchecked")
    public CircularQueue(int capacity) {
        this.capacity = capacity;
        this.queueArray = (T[]) new Object[capacity];
        this.front = 0;
        this.rear = 0;  // rear points to the next available slot for enqueue
        this.size = 0;
    }

    // Adds an item to the rear of the queue.
    // Time Complexity: O(1)
    public boolean enqueue(T item) {
        if (isFull()) {
            // throw new RuntimeException("Queue overflow");
            return false; // Or handle resizing
        }
        queueArray[rear] = item;
        rear = (rear + 1) % capacity; // Wrap around if necessary
        size++;
        return true;
    }

    // Removes and returns the item from the front of the queue.
    // Time Complexity: O(1)
    public T dequeue() {
        if (isEmpty()) {
            throw new RuntimeException("Queue underflow");
            // return null;
        }
        T item = queueArray[front];
        queueArray[front] = null; // Help GC
        front = (front + 1) % capacity; // Wrap around if necessary
        size--;
        return item;
    }

    // Returns the item at the front without removing it.
    // Time Complexity: O(1)
    public T peek() {
        if (isEmpty()) {
            throw new RuntimeException("Queue is empty");
            // return null;
        }
        return queueArray[front];
    }

    // Checks if the queue is empty.
    public boolean isEmpty() {
        return size == 0;
    }

    // Checks if the queue is full.
    public boolean isFull() {
        return size == capacity;
    }

    // Returns the number of items in the queue.
    public int size() {
        return size;
    }
}
```

#### Deques (Double-Ended Queues)
**Conceptual Explanation:**
A Deque (pronounced "deck") is a generalization of a queue that allows adding and removing elements from both the front and the rear.
*   **Operations:**
    *   `addFirst(item)`, `removeFirst()`
    *   `addLast(item)`, `removeLast()`
    *   `peekFirst()`, `peekLast()`
*   **Implementations:** Typically with a doubly linked list or a resizable array. Java's `java.util.Deque` interface is implemented by `ArrayDeque` and `LinkedList`.
*   **Applications:** Sliding window maximum/minimum, palindromic checks, job scheduling algorithms that require adding/removing from both ends.

#### Priority Queues (Conceptual Overview)
**Conceptual Explanation:**
A Priority Queue is an abstract data type similar to a regular queue, but each element has an associated "priority." Elements with higher priority are served before elements with lower priority. If two elements have the same priority, their order depends on the implementation (e.g., FIFO).
*   **Key Operations:**
    *   `insert(item, priority)` or `add(item)` (if priority is inherent to the item)
    *   `extractMax()` or `deleteMax()` (for max-priority queue)
    *   `extractMin()` or `deleteMin()` (for min-priority queue)
    *   `peekMax()` or `peekMin()`
*   **Implementation:** Commonly implemented using a **Heap** (see Trees section), which allows for O(log n) insertion and extraction of the min/max element. Can also be implemented with sorted/unsorted arrays or lists, but with worse time complexities for some operations.
*   **Java:** `java.util.PriorityQueue` implements a min-priority queue by default. You can provide a custom `Comparator` for max-priority or other ordering.
*   **Applications:**
    *   Dijkstra's algorithm (shortest path).
    *   Prim's algorithm (Minimum Spanning Tree).
    *   Huffman coding (data compression).
    *   Event-driven simulations.
    *   Operating system task scheduling based on priority.

```java
// Example: Using Java's PriorityQueue (Min-Heap by default)
// import java.util.PriorityQueue;
// import java.util.Comparator;

// PriorityQueue<Integer> minHeap = new PriorityQueue<>();
// minHeap.add(5);
// minHeap.add(1);
// minHeap.add(3);
// System.out.println(minHeap.poll()); // Output: 1

// PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Comparator.reverseOrder());
// maxHeap.add(5);
// maxHeap.add(1);
// maxHeap.add(3);
// System.out.println(maxHeap.poll()); // Output: 5
```


---

## 5. Trees

Trees are non-linear hierarchical data structures consisting of nodes connected by edges. They are fundamental in computer science for representing hierarchical relationships, efficient searching, and more.

### Basic Tree Terminologies

*   **Node:** A fundamental part of a tree that can store data and links to other nodes.
*   **Root:** The topmost node in a tree. It's the only node without a parent.
*   **Edge:** A link between two nodes.
*   **Parent:** A node that has an edge to a child node. A node can have at most one parent.
*   **Child:** A node that has an edge from a parent node.
*   **Siblings:** Nodes that share the same parent.
*   **Leaf Node (External Node):** A node with no children.
*   **Internal Node:** A node with at least one child.
*   **Path:** A sequence of nodes and edges connecting a node with a descendant.
*   **Depth of a Node:** The number of edges from the root to the node. The depth of the root is 0.
*   **Height of a Node:** The number of edges on the longest path from the node to a leaf. The height of a leaf node is 0.
*   **Height of a Tree:** The height of its root node (or the maximum depth of any node).
*   **Degree of a Node:** The number of children a node has.
*   **Degree of a Tree:** The maximum degree of a node in the tree.
*   **Subtree:** A tree consisting of a node and its descendants.
*   **Forest:** A collection of disjoint trees.

**Types of Trees (Overview):**
*   **General Tree:** No constraints on the number of children a node can have.
*   **Binary Tree (BT):** Each node has at most two children (left and right).
*   **Binary Search Tree (BST):** A binary tree with a specific ordering property.
*   **Balanced Trees (e.g., AVL, Red-Black):** BSTs that automatically keep their height small.
*   **Heaps:** Complete binary trees satisfying the heap property.
*   **Tries (Prefix Trees):** Trees used for efficient string operations.
*   And many more (B-Trees, B+ Trees, Segment Trees, Fenwick Trees, etc.)

**Advantages of Trees:**
*   Represent hierarchical data naturally (e.g., file systems, organization charts).
*   Efficient searching, insertion, and deletion (especially in balanced trees like BSTs).
*   Used in various algorithms for sorting, searching, and data compression.

**Disadvantages of Trees:**
*   Can be complex to implement and manage, especially self-balancing trees.
*   Some operations can be slow if the tree is not balanced (e.g., a skewed BST).
*   May require more memory than linear structures due to pointers.

### Binary Trees (BT)

**Conceptual Explanation:**
A binary tree is a tree data structure in which each node has at most two children, referred to as the left child and the right child.

**Node Structure (Typical):**
```java
class TreeNode {
    int val;        // Data stored in the node
    TreeNode left;  // Reference to the left child
    TreeNode right; // Reference to the right child

    TreeNode() {}
    TreeNode(int val) { this.val = val; }
    TreeNode(int val, TreeNode left, TreeNode right) {
        this.val = val;
        this.left = left;
        this.right = right;
    }
}
```

**Properties:**
*   A binary tree with `n` nodes has exactly `n-1` edges.
*   The maximum number of nodes at depth `d` is `2^d`.
*   The maximum number of nodes in a binary tree of height `h` is `2^(h+1) - 1`.
*   A binary tree with `n` nodes has a minimum height of `floor(log2(n))`.

**Types of Binary Trees:**
*   **Full (or Proper) Binary Tree:** Every node has either 0 or 2 children.
*   **Complete Binary Tree:** All levels are completely filled except possibly the last level, which is filled from left to right. Heaps are often complete binary trees.
*   **Perfect Binary Tree:** A full binary tree where all leaf nodes are at the same depth.
*   **Skewed Binary Tree:** Each node has only one child (or none), resembling a linked list. (Worst-case for many BT operations).

#### Binary Tree Traversals
Traversal is the process of visiting each node in the tree exactly once in a specific order.

**1. Inorder Traversal (Left -> Visit Root -> Right)**
*   **Use Case:** In a Binary Search Tree (BST), inorder traversal visits nodes in non-decreasing order.
*   **Complexity:** Time O(n), Space O(h) (for recursion stack, where h is height; O(n) in worst case for skewed tree).

```java
// Inorder Traversal (Recursive)
public List<Integer> inorderTraversalRecursive(TreeNode root) {
    List<Integer> result = new ArrayList<>();
    inorderHelper(root, result);
    return result;
}

private void inorderHelper(TreeNode node, List<Integer> result) {
    if (node == null) {
        return;
    }
    inorderHelper(node.left, result);   // 1. Visit left subtree
    result.add(node.val);               // 2. Process current node (add to list)
    inorderHelper(node.right, result);  // 3. Visit right subtree
}

// Inorder Traversal (Iterative using Stack)
public List<Integer> inorderTraversalIterative(TreeNode root) {
    List<Integer> result = new ArrayList<>();
    if (root == null) return result;

    Stack<TreeNode> stack = new Stack<>();
    TreeNode current = root;

    // Traverse until current is null AND stack is empty
    while (current != null || !stack.isEmpty()) {
        // 1. Go to the leftmost node of the current subtree
        while (current != null) {
            stack.push(current); // Push node onto stack before going left
            current = current.left;
        }

        // At this point, current is null. The top of the stack is the leftmost unvisited node.
        // 2. Process the node at the top of the stack
        current = stack.pop();
        result.add(current.val);

        // 3. Move to the right subtree
        current = current.right;
    }
    return result;
}
```

**2. Preorder Traversal (Visit Root -> Left -> Right)**
*   **Use Case:** Creating a copy of the tree, getting prefix expressions (e.g., expression trees).
*   **Complexity:** Time O(n), Space O(h) (recursion stack).

```java
// Preorder Traversal (Recursive)
public List<Integer> preorderTraversalRecursive(TreeNode root) {
    List<Integer> result = new ArrayList<>();
    preorderHelper(root, result);
    return result;
}

private void preorderHelper(TreeNode node, List<Integer> result) {
    if (node == null) {
        return;
    }
    result.add(node.val);               // 1. Process current node
    preorderHelper(node.left, result);  // 2. Visit left subtree
    preorderHelper(node.right, result); // 3. Visit right subtree
}

// Preorder Traversal (Iterative using Stack)
public List<Integer> preorderTraversalIterative(TreeNode root) {
    List<Integer> result = new ArrayList<>();
    if (root == null) return result;

    Stack<TreeNode> stack = new Stack<>();
    stack.push(root); // Start with the root

    while (!stack.isEmpty()) {
        TreeNode node = stack.pop(); // 1. Process current node
        result.add(node.val);

        // Push right child first, then left child (so left is processed before right due to LIFO)
        if (node.right != null) {
            stack.push(node.right); // 3. (effectively)
        }
        if (node.left != null) {
            stack.push(node.left);  // 2. (effectively)
        }
    }
    return result;
}
```

**3. Postorder Traversal (Left -> Right -> Visit Root)**
*   **Use Case:** Deleting nodes in a tree (process children before parent), getting postfix expressions.
*   **Complexity:** Time O(n), Space O(h) (recursion stack).

```java
// Postorder Traversal (Recursive)
public List<Integer> postorderTraversalRecursive(TreeNode root) {
    List<Integer> result = new ArrayList<>();
    postorderHelper(root, result);
    return result;
}

private void postorderHelper(TreeNode node, List<Integer> result) {
    if (node == null) {
        return;
    }
    postorderHelper(node.left, result);  // 1. Visit left subtree
    postorderHelper(node.right, result); // 2. Visit right subtree
    result.add(node.val);                // 3. Process current node
}

// Postorder Traversal (Iterative using Two Stacks)
public List<Integer> postorderTraversalIterativeTwoStacks(TreeNode root) {
    List<Integer> result = new ArrayList<>();
    if (root == null) return result;

    Stack<TreeNode> s1 = new Stack<>();
    Stack<TreeNode> s2 = new Stack<>(); // This stack will store nodes in reverse postorder

    s1.push(root);
    while (!s1.isEmpty()) {
        TreeNode node = s1.pop();
        s2.push(node); // Push to s2 (will be reversed later)

        // Push left child then right child to s1 (so right is processed before left by s1)
        if (node.left != null) {
            s1.push(node.left);
        }
        if (node.right != null) {
            s1.push(node.right);
        }
    }
    // Pop all elements from s2 to get postorder
    while (!s2.isEmpty()) {
        result.add(s2.pop().val);
    }
    return result;
}

// Postorder Traversal (Iterative using One Stack)
// This is more complex: track the last visited node to know if right child has been processed.
public List<Integer> postorderTraversalIterativeOneStack(TreeNode root) {
    List<Integer> result = new ArrayList<>();
    if (root == null) return result;

    Stack<TreeNode> stack = new Stack<>();
    TreeNode current = root;
    TreeNode lastVisited = null;

    while (current != null || !stack.isEmpty()) {
        while (current != null) {
            stack.push(current);
            current = current.left; // Go as left as possible
        }

        TreeNode peekNode = stack.peek();
        // If right child exists and hasn't been visited yet
        if (peekNode.right != null && peekNode.right != lastVisited) {
            current = peekNode.right; // Move to right child
        } else {
            // Process current node (peekNode)
            result.add(peekNode.val);
            lastVisited = stack.pop();
            // current remains null, so loop continues by peeking stack
        }
    }
    return result;
}
```

**4. Level Order Traversal (Breadth-First Search - BFS)**
*   **Use Case:** Visiting nodes level by level. Shortest path in terms of edges from root to a node.
*   **Complexity:** Time O(n), Space O(W) (where W is the maximum width of the tree; O(n) in worst case for a complete tree).

```java
// Level Order Traversal (BFS using a Queue)
public List<List<Integer>> levelOrder(TreeNode root) {
    List<List<Integer>> result = new ArrayList<>();
    if (root == null) return result;

    Queue<TreeNode> queue = new LinkedList<>();
    queue.offer(root); // Add root to the queue

    while (!queue.isEmpty()) {
        int levelSize = queue.size(); // Number of nodes at the current level
        List<Integer> currentLevelNodes = new ArrayList<>();

        for (int i = 0; i < levelSize; i++) {
            TreeNode node = queue.poll(); // Dequeue a node
            currentLevelNodes.add(node.val); // Process the node

            // Enqueue its children (if they exist)
            if (node.left != null) {
                queue.offer(node.left);
            }
            if (node.right != null) {
                queue.offer(node.right);
            }
        }
        result.add(currentLevelNodes); // Add the processed level to the result
    }
    return result;
}
```

#### Binary Tree Properties and Validation

```java
// Maximum Depth (or Height) of Binary Tree
// The number of nodes along the longest path from the root node down to the farthest leaf node.
public int maxDepth(TreeNode root) {
    if (root == null) {
        return 0; // Depth of an empty tree or null node is 0
    }
    int leftDepth = maxDepth(root.left);   // Recursively find depth of left subtree
    int rightDepth = maxDepth(root.right); // Recursively find depth of right subtree
    return Math.max(leftDepth, rightDepth) + 1; // Depth is max of sub-depths + 1 (for current node)
}
// Time Complexity: O(n) - Visits each node once.
// Space Complexity: O(h) - For recursion stack (h is height, O(n) in worst case).

// Check if a Binary Tree is Balanced
// A binary tree is balanced if for every node, the difference between the heights
// of its left and right subtrees is at most 1.
public boolean isBalanced(TreeNode root) {
    return checkBalanceHelper(root) != -1; // Helper returns -1 if unbalanced, height otherwise.
}

// Helper function: returns height if balanced, -1 if not.
private int checkBalanceHelper(TreeNode node) {
    if (node == null) {
        return 0; // Height of a null node is 0, considered balanced.
    }

    int leftHeight = checkBalanceHelper(node.left);
    if (leftHeight == -1) return -1; // Left subtree is unbalanced

    int rightHeight = checkBalanceHelper(node.right);
    if (rightHeight == -1) return -1; // Right subtree is unbalanced

    // Check if current node is balanced
    if (Math.abs(leftHeight - rightHeight) > 1) {
        return -1; // Current node is unbalanced
    }

    // If balanced, return height of current node's subtree
    return Math.max(leftHeight, rightHeight) + 1;
}
// Time Complexity: O(n) - Each node is visited once (bottom-up).
// Space Complexity: O(h) - For recursion stack.

// Diameter of Binary Tree
// The length of the longest path between any two nodes in a tree.
// This path may or may not pass through the root.
private int maxDiameter; // Using a field to store max diameter found so far

public int diameterOfBinaryTree(TreeNode root) {
    maxDiameter = 0; // Reset for multiple calls if object is reused
    calculateHeightForDiameter(root);
    return maxDiameter;
}

// Helper function: returns the height of the node's subtree,
// and updates maxDiameter if a longer path through this node is found.
private int calculateHeightForDiameter(TreeNode node) {
    if (node == null) return 0;

    int leftHeight = calculateHeightForDiameter(node.left);
    int rightHeight = calculateHeightForDiameter(node.right);

    // The diameter through the current node is leftHeight + rightHeight
    // (number of edges is sum of nodes in left and right longest paths from this node).
    maxDiameter = Math.max(maxDiameter, leftHeight + rightHeight);

    // Return the height of the subtree rooted at 'node'
    // (longest path from 'node' downwards)
    return Math.max(leftHeight, rightHeight) + 1;
}
// Time Complexity: O(n) - Visits each node once.
// Space Complexity: O(h) - For recursion stack.
```

### Binary Search Trees (BST)

**Conceptual Explanation:**
A Binary Search Tree is a special type of binary tree where nodes are arranged in a specific order:
1.  The value of all nodes in the left subtree of a node is less than or equal to the value of the node.
2.  The value of all nodes in the right subtree of a node is greater than the value of the node.
3.  Both the left and right subtrees must also be binary search trees.
4.  Typically, BSTs do not allow duplicate values (or have a consistent rule for handling them, e.g., always in the right subtree).

**Advantages:**
*   **Efficient Searching:** Average time complexity for search, insert, delete is O(log n) if the tree is balanced.
*   **Ordered Data:** Inorder traversal yields elements in sorted order.
*   Efficient for range queries (finding all numbers between X and Y).

**Disadvantages:**
*   **Worst-case Performance:** If the tree becomes unbalanced (skewed, resembling a linked list), operations can degrade to O(n). This happens if elements are inserted in sorted or reverse-sorted order.
*   Requires careful implementation for deletion to maintain BST property.

#### Binary Search Tree Operations

```java
// (Assuming TreeNode class definition from Binary Trees section)

class BSTOperations {
    // Search for a value in BST
    // Time Complexity: O(h) - where h is height. O(log n) average, O(n) worst.
    // Space Complexity: O(h) for recursive, O(1) for iterative.
    public TreeNode searchBST(TreeNode root, int val) {
        if (root == null || root.val == val) {
            return root; // Found or tree is empty
        }
        if (val < root.val) {
            return searchBST(root.left, val); // Search in left subtree
        } else {
            return searchBST(root.right, val); // Search in right subtree
        }
    }

    public TreeNode searchBSTIterative(TreeNode root, int val) {
        TreeNode current = root;
        while (current != null && current.val != val) {
            if (val < current.val) {
                current = current.left;
            } else {
                current = current.right;
            }
        }
        return current;
    }

    // Insert a value into BST
    // Time Complexity: O(h) - O(log n) average, O(n) worst.
    // Space Complexity: O(h) for recursive, O(1) for iterative (if parent tracking is simple).
    public TreeNode insertIntoBST(TreeNode root, int val) {
        if (root == null) {
            return new TreeNode(val); // Found the spot, create new node
        }
        if (val < root.val) {
            root.left = insertIntoBST(root.left, val); // Insert in left subtree
        } else if (val > root.val) { // Assuming no duplicates, or duplicates go right
            root.right = insertIntoBST(root.right, val); // Insert in right subtree
        }
        // if val == root.val, do nothing (or handle duplicates as per requirement)
        return root; // Return the (possibly modified) root
    }

    // Delete a node from BST
    // Time Complexity: O(h) - O(log n) average, O(n) worst.
    // Space Complexity: O(h) for recursive calls.
    public TreeNode deleteNode(TreeNode root, int key) {
        if (root == null) return null; // Key not found

        if (key < root.val) {
            root.left = deleteNode(root.left, key); // Recurse left
        } else if (key > root.val) {
            root.right = deleteNode(root.right, key); // Recurse right
        } else {
            // Node with the key to be deleted found (root is the node)

            // Case 1: Node has no children (leaf node)
            if (root.left == null && root.right == null) {
                return null; // Simply remove it
            }
            // Case 2: Node has one child
            else if (root.left == null) {
                return root.right; // Replace with right child
            } else if (root.right == null) {
                return root.left; // Replace with left child
            }
            // Case 3: Node has two children
            else {
                // Find the inorder successor (smallest value in the right subtree)
                TreeNode successor = findMin(root.right);
                // Copy the successor's value to this node
                root.val = successor.val;
                // Delete the inorder successor from the right subtree
                root.right = deleteNode(root.right, successor.val);
                // Alternatively, find inorder predecessor (largest in left subtree)
                // TreeNode predecessor = findMax(root.left);
                // root.val = predecessor.val;
                // root.left = deleteNode(root.left, predecessor.val);
            }
        }
        return root;
    }

    // Helper to find the node with the minimum value in a BST (leftmost node)
    private TreeNode findMin(TreeNode node) {
        while (node != null && node.left != null) {
            node = node.left;
        }
        return node;
    }

    // Helper to find the node with the maximum value in a BST (rightmost node)
    private TreeNode findMax(TreeNode node) {
        while (node != null && node.right != null) {
            node = node.right;
        }
        return node;
    }

    // Validate Binary Search Tree
    // Checks if a given binary tree is a valid BST.
    public boolean isValidBST(TreeNode root) {
        // Use Long.MIN_VALUE and Long.MAX_VALUE for initial bounds to handle Integer.MIN/MAX in node values.
        return validateBSTHelper(root, Long.MIN_VALUE, Long.MAX_VALUE);
    }

    private boolean validateBSTHelper(TreeNode node, long lowerBound, long upperBound) {
        if (node == null) return true; // An empty tree is a valid BST

        // Check current node's value against bounds
        if (node.val <= lowerBound || node.val >= upperBound) {
            return false;
        }

        // Recursively validate left and right subtrees with updated bounds:
        // Left child's value must be less than current node's value (new upper bound).
        // Right child's value must be greater than current node's value (new lower bound).
        return validateBSTHelper(node.left, lowerBound, node.val) &&
               validateBSTHelper(node.right, node.val, upperBound);
    }
    // Time Complexity: O(n) - Visits each node once.
    // Space Complexity: O(h) - For recursion stack.

    // Kth Smallest Element in a BST
    // Perform an inorder traversal and stop at the kth element.
    public int kthSmallest(TreeNode root, int k) {
        Stack<TreeNode> stack = new Stack<>();
        TreeNode current = root;
        int count = 0;

        while (current != null || !stack.isEmpty()) {
            while (current != null) {
                stack.push(current);
                current = current.left; // Go to the leftmost node
            }
            current = stack.pop(); // This is the next smallest element
            count++;
            if (count == k) {
                return current.val;
            }
            current = current.right; // Move to the right subtree
        }
        return -1; // Should not happen if k is valid and tree has at least k nodes
    }
    // Time Complexity: O(h + k) in the best/average case (if k is small or tree balanced).
    // O(n) in the worst case (skewed tree or k=n).
    // Space Complexity: O(h) for the stack.

    // Lowest Common Ancestor (LCA) in BST
    // Given a BST and two nodes p and q, find their LCA.
    // The LCA is the deepest node that has both p and q as descendants.
    public TreeNode lowestCommonAncestorBST(TreeNode root, TreeNode p, TreeNode q) {
        if (root == null) return null;

        // If both p and q are smaller than root, LCA must be in the left subtree.
        if (p.val < root.val && q.val < root.val) {
            return lowestCommonAncestorBST(root.left, p, q);
        }
        // If both p and q are larger than root, LCA must be in the right subtree.
        else if (p.val > root.val && q.val > root.val) {
            return lowestCommonAncestorBST(root.right, p, q);
        }
        // Otherwise, the current root is the LCA. This happens when:
        // 1. root is p or q.
        // 2. p is in one subtree and q is in the other (root is the split point).
        else {
            return root;
        }
    }
    // Iterative LCA in BST
    public TreeNode lowestCommonAncestorBSTIterative(TreeNode root, TreeNode p, TreeNode q) {
        TreeNode current = root;
        while (current != null) {
            if (p.val < current.val && q.val < current.val) {
                current = current.left;
            } else if (p.val > current.val && q.val > current.val) {
                current = current.right;
            } else {
                return current; // Found LCA (split point or one of nodes is LCA)
            }
        }
        return null; // Should not happen if p and q are in the tree
    }
    // Time Complexity: O(h) - Traverses from root down to LCA.
    // Space Complexity: O(h) for recursive, O(1) for iterative.
}
```

### Balanced Binary Trees (Conceptual)

**Why needed?**
Standard BSTs can become unbalanced if data is inserted in a sorted or nearly sorted order. In the worst case (a skewed tree), the height becomes O(n), making operations like search, insert, and delete take O(n) time, negating the main advantage of BSTs. Balanced binary trees are self-balancing variants that perform rotations to maintain a height of O(log n).

**Rotations:**
Rotations are local transformations that restructure the tree to maintain balance while preserving the BST property. Common rotations are Left Rotation and Right Rotation.

#### AVL Trees
*   **Concept:** An AVL tree is a self-balancing BST where for every node, the heights of its left and right subtrees differ by at most 1 (the "balance factor" is -1, 0, or 1).
*   **Balancing:** Achieved through single rotations (LL, RR) or double rotations (LR, RL) when an insertion or deletion violates the balance factor.
*   **Advantages:** Guaranteed O(log n) time for search, insert, delete. Stricter balance leads to faster lookups than Red-Black trees.
*   **Disadvantages:** More complex to implement due to stricter balancing rules and potentially more rotations than Red-Black trees. Insertions/deletions can be slightly slower due to rebalancing.

#### Red-Black Trees
*   **Concept:** A self-balancing BST where each node has an extra bit for color (Red or Black). Balancing is maintained by enforcing a set of rules regarding node colors and arrangements.
    1.  Every node is either Red or Black.
    2.  The root is Black.
    3.  All leaves (NIL nodes, often conceptual) are Black.
    4.  If a node is Red, then both its children are Black. (No two consecutive Red nodes on a path).
    5.  For each node, all simple paths from the node to descendant leaves contain the same number of Black nodes (the "black-height").
*   **Balancing:** Achieved through rotations and color changes.
*   **Advantages:** Guaranteed O(log n) time for search, insert, delete. Generally faster insertions/deletions than AVL trees because they require fewer rotations on average.
*   **Disadvantages:** Lookups can be slightly slower than AVL trees because the height can be up to `2 * log2(n+1)`. More complex to implement than standard BSTs.
*   **Use Cases:** Widely used in practice, e.g., Java's `TreeMap` and `TreeSet`, C++ STL's `map` and `set`.

*(Implementation details of AVL and Red-Black tree balancing are complex and usually beyond the scope of typical interview coding questions unless specifically asked, but understanding the concepts and trade-offs is important.)*

### Heaps

**Conceptual Explanation:**
A Heap is a specialized tree-based data structure that is a **complete binary tree** and satisfies the **heap property**.
*   **Complete Binary Tree:** A binary tree in which every level, except possibly the last, is completely filled, and all nodes in the last level are as far left as possible. This property allows heaps to be efficiently represented using an array.
*   **Heap Property:**
    *   **Min-Heap:** The value of each parent node is less than or equal to the values of its children. The root node contains the minimum value in the heap.
    *   **Max-Heap:** The value of each parent node is greater than or equal to the values of its children. The root node contains the maximum value in the heap.

**Array Representation:**
For a node at index `i` in an array:
*   Parent: `(i-1) / 2`
*   Left Child: `2*i + 1`
*   Right Child: `2*i + 2`

**Advantages:**
*   Efficiently find min/max element (O(1) for peek).
*   Efficient insertion and deletion of min/max (O(log n)).
*   Space efficient (array representation).
*   Foundation for Priority Queues and Heap Sort.

**Disadvantages:**
*   Searching for an arbitrary element takes O(n) as the heap property doesn't order elements beyond parent-child relationships.
*   Not ideal if frequent searching for non-min/max elements is needed.

#### Min-Heap & Max-Heap
Discussed above. The choice depends on whether you need quick access to the smallest or largest element.

#### Heap Operations (Illustrating with Min-Heap using `PriorityQueue`)
Java's `java.util.PriorityQueue` is implemented as a min-heap by default.

```java
// Using Java's PriorityQueue to demonstrate Min-Heap operations
// (Custom implementation would involve array manipulations and heapifyUp/heapifyDown)

public class MinHeapExample {
    private PriorityQueue<Integer> minHeap;

    public MinHeapExample() {
        // By default, PriorityQueue is a Min-Heap for natural ordering
        minHeap = new PriorityQueue<>();
    }

    // Insert an element into the heap
    // Time Complexity: O(log n)
    public void insert(int value) {
        minHeap.add(value); // or minHeap.offer(value);
    }

    // Get the minimum element without removing it
    // Time Complexity: O(1)
    public int peekMin() {
        if (minHeap.isEmpty()) {
            throw new RuntimeException("Heap is empty");
        }
        return minHeap.peek();
    }

    // Remove and return the minimum element
    // Time Complexity: O(log n)
    public int extractMin() {
        if (minHeap.isEmpty()) {
            throw new RuntimeException("Heap is empty");
        }
        return minHeap.poll();
    }

    // Check if the heap is empty
    public boolean isEmpty() {
        return minHeap.isEmpty();
    }

    // Get the size of the heap
    public int size() {
        return minHeap.size();
    }

    // Build heap from an array (Heapify)
    // Time Complexity: O(n) - although it involves log n operations n/2 times,
    // a tighter analysis shows O(n).
    public void buildHeap(int[] arr) {
        minHeap.clear(); // Clear existing elements
        for (int val : arr) {
            minHeap.add(val); // Adding one by one is O(n log n)
        }
        // A more optimal way to build a heap in O(n) if implementing manually
        // would be to place all elements in array and then call heapifyDown
        // starting from the last non-leaf node up to the root.
        // PriorityQueue's constructor `new PriorityQueue<>(Arrays.asList(arr))` does this efficiently.
    }

    // Example of Max-Heap using PriorityQueue
    public void maxHeapOperations() {
        PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Comparator.reverseOrder());
        maxHeap.add(3);
        maxHeap.add(10);
        maxHeap.add(1);
        System.out.println("Max element: " + maxHeap.peek()); // 10
        System.out.println("Extracted max: " + maxHeap.poll()); // 10
    }
}

// For a manual Heap implementation:
// heapifyUp (or percolateUp, siftUp): After insertion, move new element up to maintain heap property.
// heapifyDown (or percolateDown, siftDown): After deletion (root replaced by last element),
// move the new root down to maintain heap property.
```

**Heap Sort:**
1.  Build a Max-Heap from the input array (O(n)).
2.  Repeatedly extract the maximum element (root of the Max-Heap) and place it at the end of the sorted portion of the array.
    *   Swap root with the last element in the heap.
    *   Reduce heap size by 1.
    *   Call `heapifyDown` on the new root.
    *   Repeat n-1 times. (Each extraction is O(log n), so n-1 extractions take O(n log n)).
*   **Time Complexity:** O(n log n) for both best, average, and worst cases.
*   **Space Complexity:** O(1) (in-place sorting algorithm).

### Tries (Prefix Trees)

**Conceptual Explanation:**
A Trie (derived from "re**trie**val", often pronounced "try") is a tree-like data structure that stores a dynamic set of strings, typically used for efficient prefix-based searching.
*   Each node represents a character or part of a string.
*   Paths from the root to a node represent a prefix.
*   A node might have a flag (`isEndOfWord`) to indicate if the path to it forms a complete word.
*   Children of a node correspond to the next possible characters in the strings.

**Node Structure (Typical):**
```java
class TrieNode {
    Map<Character, TrieNode> children; // Or TrieNode[] children = new TrieNode[26] for lowercase English
    boolean isEndOfWord;

    public TrieNode() {
        children = new HashMap<>(); // Flexible for any character set
        isEndOfWord = false;
    }
}
```

**Advantages:**
*   **Efficient Prefix Searching:** `startsWith()` operation is very fast (O(L) where L is prefix length).
*   **Efficient Word Searching:** `search()` is O(L) where L is word length.
*   Can store many strings that share common prefixes space-efficiently (compared to storing them separately in a hash set, for example, if many prefixes overlap).
*   Useful for lexicographical sorting.

**Disadvantages:**
*   Can consume a lot of memory if strings are long and have few common prefixes. Each node might store many child pointers.
*   Not as cache-friendly as some other structures due to scattered memory.

**Operations:**

```java
class Trie {
    private TrieNode root;

    public Trie() {
        root = new TrieNode();
    }

    // Insert a word into the trie
    // Time Complexity: O(L) where L is the length of the word.
    public void insert(String word) {
        TrieNode current = root;
        for (char ch : word.toCharArray()) {
            // Get child node for char 'ch'. If it doesn't exist, create it.
            current.children.putIfAbsent(ch, new TrieNode());
            current = current.children.get(ch); // Move to the child node
        }
        current.isEndOfWord = true; // Mark the end of the word
    }

    // Search for an exact word in the trie
    // Time Complexity: O(L)
    public boolean search(String word) {
        TrieNode node = searchPrefixNode(word);
        return node != null && node.isEndOfWord; // Word exists if node found AND it's an end of word
    }

    // Check if any word in the trie starts with the given prefix
    // Time Complexity: O(L) where L is the length of the prefix.
    public boolean startsWith(String prefix) {
        return searchPrefixNode(prefix) != null; // Prefix exists if a node for it is found
    }

    // Helper function to search for a node corresponding to a prefix/word
    private TrieNode searchPrefixNode(String wordOrPrefix) {
        TrieNode current = root;
        for (char ch : wordOrPrefix.toCharArray()) {
            if (!current.children.containsKey(ch)) {
                return null; // Character not found, so prefix/word doesn't exist
            }
            current = current.children.get(ch);
        }
        return current; // Return the node corresponding to the last char of wordOrPrefix
    }

    // Get all words with a given prefix (DFS approach)
    public List<String> getWordsWithPrefix(String prefix) {
        List<String> results = new ArrayList<>();
        TrieNode prefixNode = searchPrefixNode(prefix);
        if (prefixNode != null) {
            collectWords(prefixNode, new StringBuilder(prefix), results);
        }
        return results;
    }

    private void collectWords(TrieNode node, StringBuilder currentWord, List<String> results) {
        if (node.isEndOfWord) {
            results.add(currentWord.toString());
        }
        for (Map.Entry<Character, TrieNode> entry : node.children.entrySet()) {
            currentWord.append(entry.getKey());
            collectWords(entry.getValue(), currentWord, results);
            currentWord.deleteCharAt(currentWord.length() - 1); // Backtrack
        }
    }
}
```
**Applications:**
*   Autocomplete / Typeahead suggestions.
*   Spell checkers.
*   IP routing (longest prefix match).
*   Dictionary implementations.

### Advanced Tree Problems

(Referencing the problems from your provided example, with enhanced explanations where needed)

```java
// Construct Binary Tree from Preorder and Inorder Traversal
// Conceptual Explanation:
// Preorder gives the root first. Inorder shows elements to the left and right of the root.
// 1. The first element of preorder is the root of the current (sub)tree.
// 2. Find this root in the inorder traversal. All elements to its left in inorder belong to the
//    left subtree, and all elements to its right belong to the right subtree.
// 3. Recursively build the left and right subtrees using the appropriate segments of
//    preorder and inorder arrays. The number of elements in the left subtree (from inorder)
//    tells you how many elements from the preorder array (after the root) belong to the left subtree.
public TreeNode buildTreeFromPreorderInorder(int[] preorder, int[] inorder) {
    if (preorder == null || inorder == null || preorder.length == 0 || inorder.length == 0 || preorder.length != inorder.length) {
        return null;
    }
    // Create a map for quick lookup of inorder indices
    Map<Integer, Integer> inorderMap = new HashMap<>();
    for (int i = 0; i < inorder.length; i++) {
        inorderMap.put(inorder[i], i);
    }
    return buildTreeHelperPI(preorder, 0, preorder.length - 1,
                             inorder, 0, inorder.length - 1, inorderMap);
}

private TreeNode buildTreeHelperPI(int[] preorder, int preStart, int preEnd,
                                   int[] inorder, int inStart, int inEnd,
                                   Map<Integer, Integer> inorderMap) {
    // Base case: If pointers cross, the subtree is empty
    if (preStart > preEnd || inStart > inEnd) {
        return null;
    }

    // 1. The current root is the first element in the current preorder segment
    int rootVal = preorder[preStart];
    TreeNode root = new TreeNode(rootVal);

    // 2. Find the root's index in the inorder traversal
    int inorderRootIndex = inorderMap.get(rootVal);

    // 3. Determine the number of elements in the left subtree
    int leftSubtreeSize = inorderRootIndex - inStart;

    // 4. Recursively build left and right subtrees
    // Left subtree:
    // Preorder: from (preStart + 1) up to (preStart + leftSubtreeSize)
    // Inorder: from inStart up to (inorderRootIndex - 1)
    root.left = buildTreeHelperPI(preorder, preStart + 1, preStart + leftSubtreeSize,
                                  inorder, inStart, inorderRootIndex - 1, inorderMap);

    // Right subtree:
    // Preorder: from (preStart + leftSubtreeSize + 1) up to preEnd
    // Inorder: from (inorderRootIndex + 1) up to inEnd
    root.right = buildTreeHelperPI(preorder, preStart + leftSubtreeSize + 1, preEnd,
                                   inorder, inorderRootIndex + 1, inEnd, inorderMap);
    return root;
}
// Time Complexity: O(n) - Each node is processed once. HashMap lookups are O(1).
// Space Complexity: O(n) for the HashMap and O(h) for the recursion stack (h can be n). So O(n).

// Serialize and Deserialize Binary Tree
// Serialization: Convert a tree to a string.
// Deserialization: Reconstruct the tree from the string.
// Approach: Use preorder traversal for serialization. Mark null children with a special string.
public class Codec {
    private static final String NULL_MARKER = "null";
    private static final String DELIMITER = ",";

    // Encodes a tree to a single string (using preorder traversal).
    public String serialize(TreeNode root) {
        StringBuilder sb = new StringBuilder();
        serializeHelper(root, sb);
        // Remove trailing delimiter if any
        if (sb.length() > 0 && sb.charAt(sb.length() -1) == DELIMITER.charAt(0)) {
            sb.deleteCharAt(sb.length() -1);
        }
        return sb.toString();
    }

    private void serializeHelper(TreeNode node, StringBuilder sb) {
        if (node == NULL_MARKER) { // Should be node == null
            sb.append(NULL_MARKER).append(DELIMITER);
            return;
        }
         if (node == null) { // Corrected condition
            sb.append(NULL_MARKER).append(DELIMITER);
            return;
        }

        sb.append(node.val).append(DELIMITER); // Append current node's value
        serializeHelper(node.left, sb);        // Serialize left subtree
        serializeHelper(node.right, sb);       // Serialize right subtree
    }

    // Decodes your encoded data to tree.
    public TreeNode deserialize(String data) {
        if (data == null || data.isEmpty()) return null;
        String[] nodesStr = data.split(DELIMITER);
        // Use a Queue or a global index to consume nodes in order
        Queue<String> nodesQueue = new LinkedList<>(Arrays.asList(nodesStr));
        return deserializeHelper(nodesQueue);
    }

    private TreeNode deserializeHelper(Queue<String> nodesQueue) {
        if (nodesQueue.isEmpty()) return null;

        String valStr = nodesQueue.poll(); // Get the next value string

        if (valStr.equals(NULL_MARKER)) {
            return null; // This node is null
        }

        TreeNode node = new TreeNode(Integer.parseInt(valStr));
        node.left = deserializeHelper(nodesQueue);  // Reconstruct left subtree
        node.right = deserializeHelper(nodesQueue); // Reconstruct right subtree

        return node;
    }
}
// Time Complexity: O(n) for both serialize and deserialize (each node visited once).
// Space Complexity: O(n) for StringBuilder/String array and O(h) for recursion stack. So O(n).

// Path Sum I - Root to Leaf Path
// Given root and targetSum, check if there's a root-to-leaf path where node values sum to targetSum.
public boolean hasPathSum(TreeNode root, int targetSum) {
    if (root == null) {
        return false; // No path in an empty tree
    }

    // If it's a leaf node, check if its value equals the remaining targetSum
    if (root.left == null && root.right == null) {
        return targetSum == root.val;
    }

    // Recursively check left and right subtrees with updated targetSum
    // (subtract current node's value from targetSum)
    boolean leftPathFound = hasPathSum(root.left, targetSum - root.val);
    boolean rightPathFound = hasPathSum(root.right, targetSum - root.val);

    return leftPathFound || rightPathFound;
}
// Time Complexity: O(n) - Visits each node at most once.
// Space Complexity: O(h) - For recursion stack.

// Path Sum II - All Root-to-Leaf Paths with Target Sum
// Return all root-to-leaf paths where each path's sum equals targetSum.
public List<List<Integer>> pathSumII(TreeNode root, int targetSum) {
    List<List<Integer>> allPaths = new ArrayList<>();
    List<Integer> currentPath = new ArrayList<>();
    pathSumIIHelper(root, targetSum, currentPath, allPaths);
    return allPaths;
}

private void pathSumIIHelper(TreeNode node, int remainingSum,
                             List<Integer> currentPath, List<List<Integer>> allPaths) {
    if (node == null) return;

    currentPath.add(node.val); // Add current node to path

    // If it's a leaf node and its value makes the path sum equal to targetSum
    if (node.left == null && node.right == null && remainingSum == node.val) {
        allPaths.add(new ArrayList<>(currentPath)); // Add a copy of the valid path
    } else {
        // Recursively explore left and right subtrees
        pathSumIIHelper(node.left, remainingSum - node.val, currentPath, allPaths);
        pathSumIIHelper(node.right, remainingSum - node.val, currentPath, allPaths);
    }

    // Backtrack: Remove current node from path before returning to explore other branches
    currentPath.remove(currentPath.size() - 1);
}
// Time Complexity: O(N*h) in worst case (N nodes, height h, copying paths).
// More precisely, if there are P paths of average length L, it's O(N + P*L).
// In a full tree, O(N log N) to O(N^2) in skewed.
// Space Complexity: O(h) for recursion, plus space for storing paths (can be O(N*h)).

// Binary Tree Maximum Path Sum - Any node to any node
// A path is a sequence of nodes connected by parent-child connections.
// The path must contain at least one node and does not need to go through the root.
private int maxPathGlobal; // Global variable to store the maximum path sum found

public int maxPathSum(TreeNode root) {
    maxPathGlobal = Integer.MIN_VALUE; // Initialize with a very small number
    maxPathSumHelper(root);
    return maxPathGlobal;
}

// Helper function:
// Returns the maximum path sum STARTING at 'node' and going downwards (can only choose one child branch).
// Updates 'maxPathGlobal' if a path including 'node' as the "highest" point (curve point) is larger.
private int maxPathSumHelper(TreeNode node) {
    if (node == null) return 0; // Base case: sum for a null node is 0

    // Recursively get max path sum from left and right children (going downwards)
    // If a child's path sum is negative, don't include it (take 0 instead).
    int leftMaxGain = Math.max(maxPathSumHelper(node.left), 0);
    int rightMaxGain = Math.max(maxPathSumHelper(node.right), 0);

    // Calculate the maximum path sum that "curves" at the current node:
    // node.val + leftMaxGain (from left child) + rightMaxGain (from right child)
    // This path is a candidate for the overall maximum path sum.
    int priceNewPath = node.val + leftMaxGain + rightMaxGain;
    maxPathGlobal = Math.max(maxPathGlobal, priceNewPath);

    // For the recursion (to be used by the parent of 'node'):
    // Return the maximum gain if we extend the path upwards from 'node'.
    // This means 'node' can only connect to one of its children (or neither).
    return node.val + Math.max(leftMaxGain, rightMaxGain);
}
// Time Complexity: O(n) - Visits each node once.
// Space Complexity: O(h) - For recursion stack.
```

---


## 6. Graphs

Graphs are versatile non-linear data structures used to represent relationships (connections) between entities (nodes). They consist of a set of **vertices** (or nodes) and a set of **edges** that connect pairs of vertices.

### Graph Terminologies

*   **Vertex (Node):** A fundamental part of a graph that can store data or represent an entity.
*   **Edge (Link, Arc):** A connection between two vertices. Edges can be:
    *   **Undirected:** A two-way connection (e.g., `(A, B)` is the same as `(B, A)`).
    *   **Directed (Arc):** A one-way connection (e.g., `A -> B` is different from `B -> A`).
*   **Weighted Edge:** An edge that has a numerical weight or cost associated with it (e.g., distance, time, cost).
*   **Unweighted Edge:** An edge without an associated weight (often assumed to have a weight of 1).
*   **Adjacent Vertices (Neighbors):** Two vertices are adjacent if there is an edge connecting them.
*   **Degree of a Vertex (Undirected Graph):** The number of edges incident to the vertex.
*   **In-degree of a Vertex (Directed Graph):** The number of incoming edges to the vertex.
*   **Out-degree of a Vertex (Directed Graph):** The number of outgoing edges from the vertex.
*   **Path:** A sequence of vertices where each adjacent pair in the sequence is connected by an edge.
*   **Simple Path:** A path where all vertices are distinct (no repeated vertices).
*   **Cycle:** A path that starts and ends at the same vertex, and contains at least one edge.
    *   **Acyclic Graph:** A graph with no cycles.
    *   **Directed Acyclic Graph (DAG):** A directed graph with no directed cycles.
*   **Connected Graph (Undirected):** There is a path between every pair of vertices.
*   **Disconnected Graph (Undirected):** Contains at least two vertices that are not connected by a path.
*   **Strongly Connected Graph (Directed):** There is a directed path from every vertex to every other vertex.
*   **Weakly Connected Graph (Directed):** The underlying undirected graph (ignoring edge directions) is connected.
*   **Subgraph:** A graph whose vertices and edges are subsets of another graph.
*   **Spanning Tree (of a connected undirected graph):** A subgraph that is a tree and connects all vertices together.
*   **Minimum Spanning Tree (MST):** In a weighted, connected, undirected graph, a spanning tree with the minimum possible total edge weight.
*   **Self-loop:** An edge that connects a vertex to itself.
*   **Multigraph:** A graph that allows multiple edges between the same pair of vertices.

**Applications of Graphs:**
*   Social networks (users as vertices, friendships as edges).
*   Navigation systems (locations as vertices, roads as edges with weights like distance/time).
*   The internet (web pages as vertices, hyperlinks as directed edges).
*   Recommendation systems.
*   Modeling dependencies (e.g., task scheduling, prerequisites).
*   Circuit design.

### Graph Representation

Choosing the right representation depends on the graph's properties (dense vs. sparse) and the operations to be performed.

**1. Adjacency Matrix**
*   **Concept:** A 2D matrix `adj[V][V]` where `V` is the number of vertices.
    *   For an unweighted graph: `adj[i][j] = 1` if there is an edge from vertex `i` to vertex `j`, otherwise `0`.
    *   For a weighted graph: `adj[i][j] = weight` if there is an edge from `i` to `j`, otherwise `infinity` (or a special value indicating no edge, like 0 if weights are positive).
*   **Space Complexity:** O(V²) - regardless of the number of edges. Suitable for dense graphs.
*   **Pros:**
    *   O(1) to check if an edge exists between two vertices `(i, j)`.
    *   O(1) to add/remove an edge (if no weights or simple updates).
*   **Cons:**
    *   Consumes a lot of space for sparse graphs (where E << V²).
    *   Iterating over all neighbors of a vertex takes O(V) time.
    *   Adding/removing a vertex can be costly (O(V²)) as it might require resizing the matrix.

```java
// Adjacency Matrix Representation for an Unweighted, Undirected Graph
class AdjacencyMatrixGraph {
    private int numVertices;
    private boolean[][] adjMatrix; // true if edge exists, false otherwise

    public AdjacencyMatrixGraph(int numVertices) {
        this.numVertices = numVertices;
        this.adjMatrix = new boolean[numVertices][numVertices];
        // Initialize all to false (no edges initially)
    }

    // Add an edge (for undirected graph, add in both directions)
    public void addEdge(int i, int j) {
        if (isValidVertex(i) && isValidVertex(j)) {
            adjMatrix[i][j] = true;
            adjMatrix[j][i] = true; // For undirected graph
        } else {
            System.out.println("Invalid vertices for edge: " + i + ", " + j);
        }
    }

    // Remove an edge
    public void removeEdge(int i, int j) {
        if (isValidVertex(i) && isValidVertex(j)) {
            adjMatrix[i][j] = false;
            adjMatrix[j][i] = false; // For undirected graph
        }
    }

    // Check if an edge exists
    public boolean hasEdge(int i, int j) {
        if (isValidVertex(i) && isValidVertex(j)) {
            return adjMatrix[i][j];
        }
        return false;
    }

    private boolean isValidVertex(int v) {
        return v >= 0 && v < numVertices;
    }

    public void printGraph() {
        System.out.println("Adjacency Matrix:");
        for (int i = 0; i < numVertices; i++) {
            for (int j = 0; j < numVertices; j++) {
                System.out.print((adjMatrix[i][j] ? 1 : 0) + " ");
            }
            System.out.println();
        }
    }

    public int getNumVertices() {
        return numVertices;
    }

    // Get neighbors of a vertex (requires iterating a row) - O(V)
    public List<Integer> getNeighbors(int v) {
        List<Integer> neighbors = new ArrayList<>();
        if (isValidVertex(v)) {
            for (int j = 0; j < numVertices; j++) {
                if (adjMatrix[v][j]) {
                    neighbors.add(j);
                }
            }
        }
        return neighbors;
    }
}
```

**2. Adjacency List**
*   **Concept:** An array of lists (or list of lists). `adjList[i]` contains a list of all vertices adjacent to vertex `i`.
    *   For a weighted graph, the list stores pairs `(neighbor, weight)`.
*   **Space Complexity:** O(V + E) - where E is the number of edges. Efficient for sparse graphs.
*   **Pros:**
    *   Space efficient for sparse graphs.
    *   Iterating over all neighbors of a vertex `v` is efficient (O(degree(v))).
    *   Adding a new vertex is relatively easy.
*   **Cons:**
    *   Checking if an edge exists between `(i, j)` can take O(degree(i)) time (linear scan of `i`'s list). For very dense graphs, this can be O(V).

```java
// Adjacency List Representation for an Unweighted Graph (can be directed or undirected)
class AdjacencyListGraph {
    private int numVertices;
    private List<List<Integer>> adjList;
    private boolean isDirected;

    public AdjacencyListGraph(int numVertices, boolean isDirected) {
        this.numVertices = numVertices;
        this.isDirected = isDirected;
        adjList = new ArrayList<>(numVertices);
        for (int i = 0; i < numVertices; i++) {
            adjList.add(new LinkedList<>()); // Using LinkedList for efficient add/remove at ends
        }
    }

    // Add an edge from source (src) to destination (dest)
    public void addEdge(int src, int dest) {
        if (isValidVertex(src) && isValidVertex(dest)) {
            adjList.get(src).add(dest);
            if (!isDirected && src != dest) { // For undirected, add reverse edge if not a self-loop
                adjList.get(dest).add(src);
            }
        } else {
            System.out.println("Invalid vertices for edge: " + src + " -> " + dest);
        }
    }

    // Remove an edge (more complex than matrix, requires searching in the list)
    public void removeEdge(int src, int dest) {
        if (isValidVertex(src) && isValidVertex(dest)) {
            adjList.get(src).remove(Integer.valueOf(dest)); // Must use Integer.valueOf for object removal
            if (!isDirected && src != dest) {
                adjList.get(dest).remove(Integer.valueOf(src));
            }
        }
    }

    // Check if an edge exists
    public boolean hasEdge(int src, int dest) {
        if (isValidVertex(src) && isValidVertex(dest)) {
            return adjList.get(src).contains(dest); // O(degree(src))
        }
        return false;
    }

    private boolean isValidVertex(int v) {
        return v >= 0 && v < numVertices;
    }

    public List<Integer> getNeighbors(int v) {
        if (isValidVertex(v)) {
            return new ArrayList<>(adjList.get(v)); // Return a copy to prevent external modification
        }
        return Collections.emptyList();
    }

    public int getNumVertices() {
        return numVertices;
    }

    public void printGraph() {
        System.out.println("Adjacency List:");
        for (int i = 0; i < numVertices; i++) {
            System.out.print("Vertex " + i + " -> ");
            for (Integer neighbor : adjList.get(i)) {
                System.out.print(neighbor + " ");
            }
            System.out.println();
        }
    }
}

// Adjacency List Representation for a Weighted Graph
class WeightedGraphAdjList {
    static class Edge {
        int destination;
        int weight;

        Edge(int destination, int weight) {
            this.destination = destination;
            this.weight = weight;
        }

        @Override
        public String toString() {
            return "(" + destination + ", w:" + weight + ")";
        }
    }

    private int numVertices;
    private List<List<Edge>> adjList; // List of lists of Edges
    private boolean isDirected;

    public WeightedGraphAdjList(int numVertices, boolean isDirected) {
        this.numVertices = numVertices;
        this.isDirected = isDirected;
        adjList = new ArrayList<>(numVertices);
        for (int i = 0; i < numVertices; i++) {
            adjList.add(new LinkedList<>());
        }
    }

    public void addEdge(int src, int dest, int weight) {
        if (isValidVertex(src) && isValidVertex(dest)) {
            adjList.get(src).add(new Edge(dest, weight));
            if (!isDirected && src != dest) {
                adjList.get(dest).add(new Edge(src, weight)); // Add reverse edge for undirected
            }
        }
    }

    private boolean isValidVertex(int v) {
        return v >= 0 && v < numVertices;
    }

    public List<Edge> getNeighborsWithWeights(int v) {
        if (isValidVertex(v)) {
            return new ArrayList<>(adjList.get(v));
        }
        return Collections.emptyList();
    }

    public int getNumVertices() { return numVertices; }

    public void printGraph() {
        System.out.println("Weighted Adjacency List:");
        for (int i = 0; i < numVertices; i++) {
            System.out.print("Vertex " + i + " -> ");
            for (Edge edge : adjList.get(i)) {
                System.out.print(edge + " ");
            }
            System.out.println();
        }
    }
}
```

### Graph Traversal Algorithms

Traversal means visiting every vertex and edge exactly once in some well-defined order.

**1. Breadth-First Search (BFS)**
*   **Concept:** Explores the graph level by level. It starts at a source vertex, explores all its immediate neighbors, then their unvisited neighbors, and so on.
*   **Data Structure Used:** Queue (FIFO).
*   **Algorithm:**
    1.  Initialize a queue and a `visited` array/set.
    2.  Mark the starting vertex `s` as visited and enqueue it.
    3.  While the queue is not empty:
        a.  Dequeue a vertex `u`.
        b.  Process `u` (e.g., print it).
        c.  For each unvisited neighbor `v` of `u`:
            i.  Mark `v` as visited.
            ii. Enqueue `v`.
*   **Applications:**
    *   Finding the shortest path in an unweighted graph (in terms of number of edges).
    *   Web crawlers.
    *   Finding connected components.
    *   Network broadcasting.
*   **Complexity (using Adjacency List):**
    *   **Time:** O(V + E) - Each vertex is enqueued/dequeued once (O(V)), and every edge is explored once (O(E)).
    *   **Space:** O(V) - For the `visited` array and the queue (in the worst case, the queue can hold all vertices at a level).

```java
// BFS Traversal for an AdjacencyListGraph
public class BFSTraversal {
    public void bfs(AdjacencyListGraph graph, int startVertex) {
        int numVertices = graph.getNumVertices();
        if (startVertex < 0 || startVertex >= numVertices) {
            System.out.println("Invalid start vertex.");
            return;
        }

        boolean[] visited = new boolean[numVertices]; // Keep track of visited vertices
        Queue<Integer> queue = new LinkedList<>();    // Queue for BFS

        visited[startVertex] = true; // Mark the start vertex as visited
        queue.offer(startVertex);    // Enqueue the start vertex

        System.out.print("BFS Traversal starting from vertex " + startVertex + ": ");

        while (!queue.isEmpty()) {
            int currentVertex = queue.poll(); // Dequeue a vertex
            System.out.print(currentVertex + " "); // Process the vertex

            // Get all adjacent vertices of the dequeued vertex currentVertex
            // If a neighbor has not been visited, mark it visited and enqueue it
            for (int neighbor : graph.getNeighbors(currentVertex)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.offer(neighbor);
                }
            }
        }
        System.out.println();
    }

    // BFS to handle disconnected graphs (visits all components)
    public void bfsDisconnected(AdjacencyListGraph graph) {
        int numVertices = graph.getNumVertices();
        boolean[] visited = new boolean[numVertices];
        System.out.print("BFS Traversal for all components: ");

        for (int i = 0; i < numVertices; i++) {
            if (!visited[i]) { // If vertex i is not visited, start BFS from it
                Queue<Integer> queue = new LinkedList<>();
                visited[i] = true;
                queue.offer(i);

                while(!queue.isEmpty()) {
                    int currentVertex = queue.poll();
                    System.out.print(currentVertex + " ");

                    for (int neighbor : graph.getNeighbors(currentVertex)) {
                        if (!visited[neighbor]) {
                            visited[neighbor] = true;
                            queue.offer(neighbor);
                        }
                    }
                }
            }
        }
        System.out.println();
    }
}
```

**2. Depth-First Search (DFS)**
*   **Concept:** Explores as far as possible along each branch before backtracking. It starts at a source vertex, explores one of its neighbors, then that neighbor's neighbor, and so on, until it reaches a dead end or an already visited node. Then it backtracks.
*   **Data Structure Used:** Stack (LIFO) - either explicitly using a `Stack` object or implicitly via the recursion call stack.
*   **Algorithm (Recursive):**
    1.  Initialize a `visited` array/set.
    2.  Define a `dfsUtil(vertex u, visited)` function:
        a.  Mark `u` as visited.
        b.  Process `u`.
        c.  For each unvisited neighbor `v` of `u`:
            i.  Call `dfsUtil(v, visited)`.
*   **Algorithm (Iterative using Stack):**
    1.  Initialize a stack and a `visited` array/set.
    2.  Push the starting vertex `s` onto the stack.
    3.  While the stack is not empty:
        a.  Pop a vertex `u` from the stack.
        b.  If `u` has not been visited:
            i.   Mark `u` as visited.
            ii.  Process `u`.
            iii. For each neighbor `v` of `u` (usually in reverse order of how you want to visit them, to mimic recursion):
                Push `v` onto the stack.
*   **Applications:**
    *   Detecting cycles in a graph.
    *   Topological sorting for DAGs.
    *   Finding connected components.
    *   Solving puzzles like mazes.
    *   Pathfinding.
*   **Complexity (using Adjacency List):**
    *   **Time:** O(V + E) - Each vertex is visited once, and every edge is explored once.
    *   **Space:** O(V) - For the `visited` array and the recursion stack (worst case O(V) for skewed paths) or explicit stack.

```java
// DFS Traversal for an AdjacencyListGraph
public class DFSTraversal {

    // DFS - Recursive Implementation
    public void dfsRecursive(AdjacencyListGraph graph, int startVertex) {
        int numVertices = graph.getNumVertices();
        if (startVertex < 0 || startVertex >= numVertices) {
            System.out.println("Invalid start vertex.");
            return;
        }
        boolean[] visited = new boolean[numVertices];
        System.out.print("DFS Recursive Traversal starting from vertex " + startVertex + ": ");
        dfsRecursiveUtil(graph, startVertex, visited);
        System.out.println();
    }

    private void dfsRecursiveUtil(AdjacencyListGraph graph, int vertex, boolean[] visited) {
        visited[vertex] = true;         // Mark current node as visited
        System.out.print(vertex + " "); // Process the vertex

        // Recur for all the vertices adjacent to this vertex
        for (int neighbor : graph.getNeighbors(vertex)) {
            if (!visited[neighbor]) {
                dfsRecursiveUtil(graph, neighbor, visited);
            }
        }
    }

    // DFS - Iterative Implementation using Stack
    public void dfsIterative(AdjacencyListGraph graph, int startVertex) {
        int numVertices = graph.getNumVertices();
         if (startVertex < 0 || startVertex >= numVertices) {
            System.out.println("Invalid start vertex.");
            return;
        }
        boolean[] visited = new boolean[numVertices];
        Stack<Integer> stack = new Stack<>();

        stack.push(startVertex); // Push the starting vertex
        System.out.print("DFS Iterative Traversal starting from vertex " + startVertex + ": ");

        while (!stack.isEmpty()) {
            int currentVertex = stack.pop();

            if (!visited[currentVertex]) {
                visited[currentVertex] = true;
                System.out.print(currentVertex + " "); // Process the vertex

                // Get all adjacent vertices. Push them onto the stack.
                // To match recursive DFS order for typical adjacency list (smaller index first),
                // push neighbors in reverse order of how they appear in the adj list.
                List<Integer> neighbors = graph.getNeighbors(currentVertex);
                for (int i = neighbors.size() - 1; i >= 0; i--) {
                    int neighbor = neighbors.get(i);
                    if (!visited[neighbor]) {
                        stack.push(neighbor);
                    }
                }
            }
        }
        System.out.println();
    }

    // DFS to handle disconnected graphs (visits all components)
    public void dfsRecursiveDisconnected(AdjacencyListGraph graph) {
        int numVertices = graph.getNumVertices();
        boolean[] visited = new boolean[numVertices];
        System.out.print("DFS Recursive Traversal for all components: ");
        for (int i = 0; i < numVertices; i++) {
            if (!visited[i]) {
                dfsRecursiveUtil(graph, i, visited);
            }
        }
        System.out.println();
    }
}
```

### Cycle Detection

**1. Cycle Detection in an Undirected Graph**
*   **Using DFS:** During DFS traversal, if we encounter a visited vertex that is not the immediate parent of the current vertex in the DFS tree, then there is a cycle.
*   **Using BFS:** Not as straightforward as DFS for cycle detection alone, often combined with parent tracking.
*   **Using Union-Find (Disjoint Set Union - DSU):**
    1.  Iterate through all edges `(u, v)`.
    2.  For each edge, find the sets (or parents) of `u` and `v`.
    3.  If `find(u)` is the same as `find(v)`, then adding this edge forms a cycle.
    4.  Otherwise, `union(u, v)`.
    *   **Time Complexity:** O(E * α(V)) where α is the Inverse Ackermann function (nearly constant). Very efficient.

```java
// Cycle Detection in Undirected Graph using DFS
public class UndirectedCycleDetectionDFS {
    public boolean hasCycle(AdjacencyListGraph graph) {
        int numVertices = graph.getNumVertices();
        boolean[] visited = new boolean[numVertices];

        for (int i = 0; i < numVertices; i++) {
            if (!visited[i]) {
                // Parent is -1 for the initial call from a new component
                if (dfsHasCycleUtil(graph, i, visited, -1)) {
                    return true; // Cycle found
                }
            }
        }
        return false; // No cycle found in any component
    }

    // u: current vertex, visited: visited array, parent: parent of u in DFS tree
    private boolean dfsHasCycleUtil(AdjacencyListGraph graph, int u, boolean[] visited, int parent) {
        visited[u] = true;

        for (int v : graph.getNeighbors(u)) {
            if (!visited[v]) { // If v is not visited, recurse
                if (dfsHasCycleUtil(graph, v, visited, u)) {
                    return true;
                }
            } else if (v != parent) {
                // If v is visited and not the parent of u, then there is a back edge, hence a cycle.
                return true;
            }
            // If v is visited and v IS the parent, it's just the edge we came from, so ignore.
        }
        return false;
    }
}
// Time Complexity: O(V + E) - Standard DFS traversal.
// Space Complexity: O(V) - For visited array and recursion stack.
```

**2. Cycle Detection in a Directed Graph**
*   **Using DFS:** Keep track of vertices currently in the recursion stack (active path). If DFS encounters a vertex that is already in the recursion stack, a back edge is found, indicating a cycle.
    *   We need three states for vertices:
        1.  Unvisited (e.g., 0)
        2.  Visiting (in recursion stack, e.g., 1)
        3.  Visited (fully processed, left recursion stack, e.g., 2)
    *   A cycle exists if we encounter a vertex in state "Visiting".

```java
// Cycle Detection in Directed Graph using DFS
public class DirectedCycleDetectionDFS {
    private static final int UNVISITED = 0;
    private static final int VISITING = 1; // Currently in recursion stack
    private static final int VISITED = 2;  // Finished processing (left recursion stack)

    public boolean hasCycle(AdjacencyListGraph graph) {
        int numVertices = graph.getNumVertices();
        int[] states = new int[numVertices]; // 0: unvisited, 1: visiting, 2: visited

        for (int i = 0; i < numVertices; i++) {
            if (states[i] == UNVISITED) {
                if (dfsHasCycleUtil(graph, i, states)) {
                    return true; // Cycle found
                }
            }
        }
        return false; // No cycle found
    }

    private boolean dfsHasCycleUtil(AdjacencyListGraph graph, int u, int[] states) {
        states[u] = VISITING; // Mark as currently visiting

        for (int v : graph.getNeighbors(u)) {
            if (states[v] == VISITING) {
                // Found a back edge to a node currently in the recursion stack
                return true;
            }
            if (states[v] == UNVISITED) {
                if (dfsHasCycleUtil(graph, v, states)) {
                    return true;
                }
            }
            // If states[v] == VISITED, it means v has been fully processed and
            // is not part of the current path, so it's a forward or cross edge, not a cycle from here.
        }
        states[u] = VISITED; // Mark as fully visited (removed from recursion stack)
        return false;
    }
}
// Time Complexity: O(V + E) - Standard DFS traversal.
// Space Complexity: O(V) - For states array and recursion stack.
```

### Topological Sorting

*   **Concept:** A linear ordering of vertices in a **Directed Acyclic Graph (DAG)** such that for every directed edge `u -> v`, vertex `u` comes before vertex `v` in the ordering.
*   If a graph has a cycle, it cannot have a topological sort.
*   Topological sort is not unique if multiple valid orderings exist.
*   **Applications:**
    *   Task scheduling with dependencies (e.g., course prerequisites, build systems).
    *   Dependency resolution in software.
    *   Data serialization.

**1. Kahn's Algorithm (BFS-based)**
*   **Algorithm:**
    1.  Compute the in-degree (number of incoming edges) for all vertices.
    2.  Initialize a queue with all vertices having an in-degree of 0.
    3.  Initialize a list `topologicalOrder` to store the result.
    4.  While the queue is not empty:
        a.  Dequeue a vertex `u` and add it to `topologicalOrder`.
        b.  For each neighbor `v` of `u`:
            i.  Decrement the in-degree of `v`.
            ii. If the in-degree of `v` becomes 0, enqueue `v`.
    5.  If `topologicalOrder.size()` is not equal to `V` (number of vertices), the graph has a cycle, and topological sort is not possible. Otherwise, `topologicalOrder` contains a valid sort.
*   **Complexity:**
    *   **Time:** O(V + E) - In-degree calculation is O(V+E). Queue operations and edge traversals are O(V+E).
    *   **Space:** O(V) - For in-degree array, queue, and result list.

```java
// Topological Sort using Kahn's Algorithm (BFS-based)
public class TopologicalSortKahn {
    public List<Integer> topologicalSort(AdjacencyListGraph graph) {
        int numVertices = graph.getNumVertices();
        int[] inDegree = new int[numVertices]; // Store in-degree of each vertex
        List<Integer> topologicalOrder = new ArrayList<>();
        Queue<Integer> queue = new LinkedList<>(); // Queue for vertices with in-degree 0

        // 1. Calculate in-degrees
        for (int u = 0; u < numVertices; u++) {
            for (int v : graph.getNeighbors(u)) {
                inDegree[v]++;
            }
        }

        // 2. Enqueue all vertices with in-degree 0
        for (int i = 0; i < numVertices; i++) {
            if (inDegree[i] == 0) {
                queue.offer(i);
            }
        }

        int visitedCount = 0; // Count of visited vertices for cycle detection

        // 3. Process the queue
        while (!queue.isEmpty()) {
            int u = queue.poll();
            topologicalOrder.add(u); // Add to result
            visitedCount++;

            // 4. Decrement in-degree of neighbors
            for (int v : graph.getNeighbors(u)) {
                inDegree[v]--;
                if (inDegree[v] == 0) { // If in-degree becomes 0, enqueue it
                    queue.offer(v);
                }
            }
        }

        // 5. Check for cycles
        if (visitedCount != numVertices) {
            System.out.println("Graph has a cycle! Topological sort not possible.");
            return Collections.emptyList(); // Or throw an exception
        }

        return topologicalOrder;
    }
}
```

**2. DFS-based Topological Sort**
*   **Algorithm:**
    1.  Initialize a `visited` array/set and a `Stack` (or list to be reversed).
    2.  For each vertex `u` from `0` to `V-1`:
        If `u` is not visited, call `dfsTopologicalUtil(u, visited, stack)`.
    3.  The `dfsTopologicalUtil(u, visited, stack)` function:
        a.  Mark `u` as visited.
        b.  For each unvisited neighbor `v` of `u`:
            Call `dfsTopologicalUtil(v, visited, stack)`.
        c.  After visiting all descendants of `u`, push `u` onto the stack.
    4.  Pop elements from the stack to get the topological order (or reverse the list if using a list).
*   **Key Idea:** A vertex is pushed onto the stack only after all its descendants have been pushed. So, popping from the stack gives vertices with no outgoing edges to unvisited nodes first.
*   **Cycle Detection:** This DFS approach can also be combined with cycle detection for directed graphs. If a cycle is detected, topological sort isn't possible.
*   **Complexity:**
    *   **Time:** O(V + E) - Standard DFS.
    *   **Space:** O(V) - For visited array, recursion stack, and result stack/list.

```java
// Topological Sort using DFS-based approach
public class TopologicalSortDFS {
    public List<Integer> topologicalSort(AdjacencyListGraph graph) {
        int numVertices = graph.getNumVertices();
        boolean[] visited = new boolean[numVertices];
        // For cycle detection (if needed, can integrate the 3-state DFS here)
        // boolean[] recursionStack = new boolean[numVertices];
        Stack<Integer> stack = new Stack<>(); // Stores the topological order in reverse

        for (int i = 0; i < numVertices; i++) {
            if (!visited[i]) {
                // If cycle detection is added and returns true, stop and report.
                dfsUtil(graph, i, visited, stack /*, recursionStack */);
            }
        }

        List<Integer> topologicalOrder = new ArrayList<>();
        while (!stack.isEmpty()) {
            topologicalOrder.add(stack.pop());
        }
        return topologicalOrder;
    }

    private void dfsUtil(AdjacencyListGraph graph, int u, boolean[] visited, Stack<Integer> stack
                         /*, boolean[] recursionStack */) {
        visited[u] = true;
        // recursionStack[u] = true; // For cycle detection

        for (int v : graph.getNeighbors(u)) {
            /* For cycle detection:
            if (!visited[v]) {
                if (dfsUtil(graph, v, visited, stack, recursionStack)) return true; // Cycle found
            } else if (recursionStack[v]) {
                return true; // Cycle found (back edge)
            }
            */
            if (!visited[v]) {
                dfsUtil(graph, v, visited, stack /*, recursionStack */);
            }
        }
        // recursionStack[u] = false; // Backtrack for cycle detection
        stack.push(u); // Push current vertex to stack after all its descendants are processed
        // return false; // For cycle detection
    }
}
```

### Shortest Path Algorithms

Finds a path between two vertices such that the sum of the weights of its constituent edges is minimized.

**1. Breadth-First Search (BFS) - For Unweighted Graphs**
*   Already discussed. BFS naturally finds the shortest path in terms of the number of edges because it explores level by level. To reconstruct the path, you can store parent pointers during BFS.

**2. Dijkstra's Algorithm**
*   **Concept:** Finds the shortest path from a single source vertex to all other vertices in a **weighted graph with non-negative edge weights**.
*   **Greedy Approach:** At each step, it picks the unvisited vertex with the smallest known distance from the source, marks it as visited, and updates the distances to its neighbors.
*   **Data Structures Used:**
    *   `dist[]`: An array to store the shortest distance from the source to each vertex (initialized to infinity, source to 0).
    *   `visited[]` (or `sptSet[]` - Shortest Path Tree Set): A boolean array to mark visited vertices.
    *   **Priority Queue (Min-Heap):** To efficiently select the unvisited vertex with the minimum distance. Stores pairs `(distance, vertex)`.
*   **Algorithm:**
    1.  Initialize `dist[src] = 0` and `dist[v] = infinity` for all other `v`.
    2.  Add `(0, src)` to a min-priority queue.
    3.  While the priority queue is not empty:
        a.  Extract `(d, u)` with the minimum distance `d` from the priority queue.
        b.  If `u` has already been visited (or `d > dist[u]`), continue (optimization for some PQ implementations).
        c.  Mark `u` as visited.
        d.  For each neighbor `v` of `u` with edge weight `w(u,v)`:
            If `dist[u] + w(u,v) < dist[v]` (a shorter path to `v` is found through `u`):
                `dist[v] = dist[u] + w(u,v)`
                Add/update `(dist[v], v)` in the priority queue.
*   **Complexity:**
    *   **Using Binary Heap (PriorityQueue):** O((V + E) log V) or simply O(E log V) if E > V.
        Each vertex extraction is O(log V). Each edge relaxation might lead to a PQ update (O(log V)). V extractions, E relaxations.
    *   **Using Fibonacci Heap:** O(E + V log V) (amortized).
    *   **Using simple array for PQ (less efficient):** O(V²)
*   **Limitation:** Does not work correctly if the graph has negative edge weights (it might finalize a path too early).

```java
// Dijkstra's Algorithm using PriorityQueue for a WeightedGraphAdjList
public class DijkstraAlgorithm {

    // Represents a node in the priority queue: vertex and its distance from source
    static class Node implements Comparable<Node> {
        int vertex;
        int distance;

        Node(int vertex, int distance) {
            this.vertex = vertex;
            this.distance = distance;
        }

        @Override
        public int compareTo(Node other) {
            // For Min-PriorityQueue
            return Integer.compare(this.distance, other.distance);
        }
    }

    public int[] dijkstra(WeightedGraphAdjList graph, int sourceVertex) {
        int numVertices = graph.getNumVertices();
        if (sourceVertex < 0 || sourceVertex >= numVertices) {
            throw new IllegalArgumentException("Invalid source vertex");
        }

        int[] dist = new int[numVertices]; // Shortest distances from sourceVertex
        // int[] parent = new int[numVertices]; // To reconstruct path (optional)
        Arrays.fill(dist, Integer.MAX_VALUE); // Initialize all distances to infinity
        // Arrays.fill(parent, -1);

        dist[sourceVertex] = 0; // Distance from source to itself is 0

        // Min-PriorityQueue to store {vertex, distance} pairs, ordered by distance
        PriorityQueue<Node> pq = new PriorityQueue<>();
        pq.offer(new Node(sourceVertex, 0));

        while (!pq.isEmpty()) {
            Node currentNode = pq.poll();
            int u = currentNode.vertex;
            int d_u = currentNode.distance;

            // Optimization: If we have already found a shorter path to u, skip processing this one.
            // This can happen if multiple entries for the same vertex exist in PQ with different distances.
            if (d_u > dist[u]) {
                continue;
            }

            // Iterate over all neighbors of u
            for (WeightedGraphAdjList.Edge edge : graph.getNeighborsWithWeights(u)) {
                int v = edge.destination;
                int weight_uv = edge.weight;

                // Relaxation step: If a shorter path to v is found through u
                if (dist[u] != Integer.MAX_VALUE && dist[u] + weight_uv < dist[v]) {
                    dist[v] = dist[u] + weight_uv;
                    // parent[v] = u; // Store parent for path reconstruction
                    pq.offer(new Node(v, dist[v])); // Add/update v in priority queue
                }
            }
        }
        return dist; // Contains shortest distances from sourceVertex to all other vertices
    }

    // Example usage:
    // WeightedGraphAdjList g = new WeightedGraphAdjList(5, false);
    // g.addEdge(0, 1, 10); g.addEdge(0, 3, 5); ...
    // DijkstraAlgorithm da = new DijkstraAlgorithm();
    // int[] shortestDistances = da.dijkstra(g, 0);
    // System.out.println(Arrays.toString(shortestDistances));
}
```

**3. Bellman-Ford Algorithm**
*   **Concept:** Finds the shortest paths from a single source vertex to all other vertices in a weighted graph, even if some edge weights are **negative**. It can also detect **negative-weight cycles** reachable from the source.
*   **Algorithm:**
    1.  Initialize `dist[src] = 0` and `dist[v] = infinity` for all other `v`.
    2.  Repeat `V-1` times:
        For each edge `(u, v)` with weight `w(u,v)`:
            If `dist[u] != infinity` and `dist[u] + w(u,v) < dist[v]`:
                `dist[v] = dist[u] + w(u,v)` (Relax the edge)
    3.  After `V-1` iterations, if there are no negative-weight cycles, `dist[]` contains shortest paths.
    4.  **Detecting Negative Cycles:** Perform one more (V-th) iteration of relaxations. If any `dist[v]` value can still be reduced, then there is a negative-weight cycle reachable from the source.
*   **Why V-1 iterations?** The shortest path in a graph with V vertices can have at most V-1 edges (if no cycles). Each iteration `i` finds shortest paths of at most `i` edges.
*   **Complexity:** O(V * E) - `V-1` iterations, and each iteration goes through all `E` edges.
*   **Use Cases:** When negative edge weights are present. Network routing protocols (like RIP).

**4. Floyd-Warshall Algorithm**
*   **Concept:** Finds the shortest paths between **all pairs of vertices** in a weighted graph (can have negative weights, but not negative-weight cycles for meaningful results on paths affected by them).
*   **Dynamic Programming Approach:**
    `dist[i][j][k]` = shortest path from `i` to `j` using only intermediate vertices from the set `{0, 1, ..., k}`.
    The recurrence simplifies to: `dist[i][j] = min(dist[i][j], dist[i][k] + dist[k][j])`
*   **Algorithm:**
    1.  Initialize `dist[i][j]` with direct edge weights (or 0 if `i==j`, infinity if no direct edge).
    2.  For `k` from `0` to `V-1`: (k is the intermediate vertex)
        For `i` from `0` to `V-1`:
            For `j` from `0` to `V-1`:
                If `dist[i][k] != infinity` and `dist[k][j] != infinity`:
                    `dist[i][j] = min(dist[i][j], dist[i][k] + dist[k][j])`
*   **Complexity:** O(V³) - Three nested loops.
*   **Use Cases:** Finding all-pairs shortest paths. Transitive closure of a graph.

```java
// Floyd-Warshall Algorithm for All-Pairs Shortest Path
public class FloydWarshallAlgorithm {
    private final static int INF = Integer.MAX_VALUE / 2; // Use a large enough value for infinity to avoid overflow

    // graph[i][j] is the weight of edge from i to j, or INF if no direct edge.
    // graph[i][i] should be 0.
    public int[][] floydWarshall(int[][] graphMatrix) {
        int V = graphMatrix.length;
        int[][] dist = new int[V][V];

        // Initialize dist[][] with the given graph matrix
        for (int i = 0; i < V; i++) {
            for (int j = 0; j < V; j++) {
                dist[i][j] = graphMatrix[i][j];
            }
        }

        // Iterate through all vertices k as potential intermediate vertices
        for (int k = 0; k < V; k++) {
            // Iterate through all possible source vertices i
            for (int i = 0; i < V; i++) {
                // Iterate through all possible destination vertices j
                for (int j = 0; j < V; j++) {
                    // If vertex k is on the shortest path from i to j,
                    // then update the value of dist[i][j]
                    // Ensure that paths through k are valid (not involving INF leading to overflow)
                    if (dist[i][k] != INF && dist[k][j] != INF &&
                        dist[i][k] + dist[k][j] < dist[i][j]) {
                        dist[i][j] = dist[i][k] + dist[k][j];
                    }
                }
            }
        }
        // To detect negative cycles: if dist[i][i] < 0 for any i after algorithm, a negative cycle involving i exists.
        return dist;
    }
    // Example usage:
    // int[][] graph = { {0, 5, INF, 10},
    //                   {INF, 0, 3, INF},
    //                   {INF, INF, 0, 1},
    //                   {INF, INF, INF, 0} };
    // FloydWarshallAlgorithm fwa = new FloydWarshallAlgorithm();
    // int[][] shortestPaths = fwa.floydWarshall(graph);
    // for (int[] row : shortestPaths) System.out.println(Arrays.toString(row));
}
```

### Minimum Spanning Trees (MST) - Conceptual

*   **Concept:** Given a **connected, undirected, weighted graph**, an MST is a subgraph that connects all vertices together (it's a tree) with the minimum possible total sum of edge weights.
*   If the graph is not connected, we find an MST for each connected component (forming a Minimum Spanning Forest).
*   **Properties:**
    *   An MST for a graph with V vertices will always have V-1 edges.
    *   Adding an edge to an MST creates a cycle.
    *   Removing an edge from an MST splits it into two trees.
*   **Cut Property (Key for MST Algorithms):** For any cut (a partition of vertices into two disjoint sets), if the weight of an edge `(u,v)` is strictly smaller than the weights of all other edges with one endpoint in one set and the other endpoint in the other set, then this edge belongs to every MST of the graph.

**1. Prim's Algorithm**
*   **Concept:** A greedy algorithm that builds the MST by starting with an arbitrary vertex and iteratively adding the cheapest edge that connects a vertex in the growing MST to a vertex outside the MST, until all vertices are included.
*   **Analogy:** Similar to Dijkstra's algorithm structure.
*   **Data Structures:**
    *   `key[]`: Stores the minimum weight of an edge connecting vertex `v` to the MST.
    *   `mstSet[]`: Boolean array, `true` if vertex `v` is included in MST.
    *   `parent[]`: Stores the parent of `v` in the MST.
    *   Priority Queue (Min-Heap): Stores vertices not yet in MST, ordered by their `key` values.
*   **Complexity:** O(E log V) using a binary heap, or O(V²) with adjacency matrix and array-based key finding.
*   **Use Cases:** When the graph is dense (E is close to V²), an adjacency matrix version might be competitive. Often simpler to implement conceptually for some.

**2. Kruskal's Algorithm**
*   **Concept:** A greedy algorithm that builds the MST by repeatedly adding the next cheapest edge that does not form a cycle with the edges already chosen.
*   **Algorithm:**
    1.  Sort all edges in the graph by non-decreasing weight.
    2.  Initialize an empty set of edges for the MST.
    3.  Initialize a Disjoint Set Union (DSU) data structure with V disjoint sets, one for each vertex.
    4.  Iterate through the sorted edges `(u,v)`:
        If `find(u)` is not equal to `find(v)` (i.e., `u` and `v` are in different connected components, so adding edge `(u,v)` won't form a cycle):
            Add edge `(u,v)` to the MST.
            `union(u,v)`.
    5.  Stop when V-1 edges have been added to the MST (or all edges processed).
*   **Complexity:** O(E log E) for sorting edges. The DSU operations (find and union) take nearly constant time on average (O(E * α(V))). So, dominated by sorting: O(E log E). This can also be written as O(E log V) since E can be at most V².
*   **Use Cases:** Often preferred for sparse graphs. Conceptually simpler when thinking about edge selection.

*(Detailed code for Prim's and Kruskal's can be extensive, but the concepts and use of Priority Queues (for Prim's) and DSU (for Kruskal's) are key takeaways.)*

---

## 7. Sorting Algorithms

Sorting is the process of arranging elements of a list or array in a specific order (e.g., ascending or descending). Understanding various sorting algorithms, their mechanisms, and their trade-offs (time complexity, space complexity, stability, in-place nature) is fundamental in computer science and crucial for interviews.

**Key Sorting Algorithm Properties:**
*   **Time Complexity:** How the runtime grows with the input size `n` (Best, Average, Worst cases).
*   **Space Complexity:** Amount of extra memory used by the algorithm (In-place vs. Out-of-place).
    *   **In-place:** Sorts the input by modifying it directly, using only O(1) or O(log n) auxiliary space.
    *   **Out-of-place:** Requires O(n) auxiliary space (e.g., to create a copy or temporary arrays).
*   **Stability:** A sorting algorithm is stable if elements with equal keys maintain their relative order in the sorted output as they were in the input.
    *   *Example:* If sorting `[(5, "apple"), (3, "banana"), (5, "cherry")]` by the numeric key, a stable sort would produce `[(3, "banana"), (5, "apple"), (5, "cherry")]`, preserving the original order of "apple" before "cherry" for the key 5.
*   **Internal vs. External Sort:**
    *   **Internal:** Data fits entirely in main memory.
    *   **External:** Data is too large for main memory, requiring use of external storage (e.g., disk). Merge sort is often adapted for external sorting.
*   **Comparison vs. Non-Comparison Sort:**
    *   **Comparison Sort:** Determines order by comparing elements (e.g., Bubble, Merge, Quick Sort). Lower bound of Ω(n log n) for time complexity.
    *   **Non-Comparison Sort:** Uses properties of the elements themselves (e.g., their digits or counts) to sort (e.g., Counting Sort, Radix Sort). Can be faster than O(n log n) under certain conditions.

### Basic Sorting Algorithms (Often O(n²))

These are generally simpler to understand and implement but less efficient for large datasets.

**1. Bubble Sort**
*   **Concept:** Repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. The largest (or smallest) elements "bubble" to their correct position at the end of the list with each pass.
*   **Algorithm:**
    1.  Iterate from the first element to the second-to-last element (`i` from `0` to `n-2`).
    2.  In each outer iteration, iterate from the first element to `n-1-i` (`j` from `0` to `n-2-i`).
    3.  Compare `arr[j]` and `arr[j+1]`. If `arr[j] > arr[j+1]`, swap them.
    4.  An optimization: if no swaps occur in an inner loop pass, the array is sorted, and the algorithm can terminate early.
*   **Time Complexity:**
    *   **Worst Case:** O(n²) (e.g., reverse-sorted array).
    *   **Average Case:** O(n²).
    *   **Best Case:** O(n) (if array is already sorted and the optimization is used).
*   **Space Complexity:** O(1) (In-place).
*   **Stability:** Yes, it is stable (if implemented carefully to not swap equal elements).
*   **Use Cases:** Rarely used in practice for large datasets due to inefficiency. Good for educational purposes or very small arrays.

```java
public class BasicSorting {
    // Helper to swap elements in an array
    private void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

    // Bubble Sort
    public void bubbleSort(int[] arr) {
        if (arr == null || arr.length <= 1) return;
        int n = arr.length;
        boolean swapped; // Optimization: flag to check if any swap happened in a pass

        // Outer loop for passes. After i-th pass, last i elements are in place.
        for (int i = 0; i < n - 1; i++) {
            swapped = false;
            // Inner loop for comparisons and swaps within the unsorted part.
            // The unsorted part shrinks from the end: arr[0...n-1-i]
            for (int j = 0; j < n - 1 - i; j++) {
                if (arr[j] > arr[j + 1]) {
                    swap(arr, j, j + 1);
                    swapped = true;
                }
            }
            // If no two elements were swapped by inner loop, then array is sorted.
            if (!swapped) {
                break;
            }
        }
    }
    // Time: O(n^2) worst/avg, O(n) best (with optimization)
    // Space: O(1)
    // Stable: Yes
}
```

**2. Selection Sort**
*   **Concept:** Repeatedly finds the minimum element from the unsorted part of the list and puts it at the beginning of the unsorted part (effectively growing the sorted part from the left).
*   **Algorithm:**
    1.  Iterate from the first element to the second-to-last element (`i` from `0` to `n-2`). This `i` marks the beginning of the unsorted part.
    2.  In each outer iteration, assume `arr[i]` is the minimum. Find the index (`minIndex`) of the actual minimum element in the unsorted part (`arr[i...n-1]`).
    3.  Swap `arr[i]` with `arr[minIndex]`.
*   **Time Complexity:**
    *   **Worst Case:** O(n²) (Number of comparisons is always (n-1) + (n-2) + ... + 1).
    *   **Average Case:** O(n²).
    *   **Best Case:** O(n²) (Even if sorted, it still goes through all comparisons).
*   **Space Complexity:** O(1) (In-place).
*   **Stability:** No, it is generally not stable. Swapping can change the relative order of equal elements. (e.g., `[5a, 5b, 1]` -> `[1, 5b, 5a]`).
*   **Use Cases:** Simple to implement. Useful when memory writes are costly, as it makes at most `n-1` swaps.

```java
// (Continuing in BasicSorting class)
    // Selection Sort
    public void selectionSort(int[] arr) {
        if (arr == null || arr.length <= 1) return;
        int n = arr.length;

        // One by one move boundary of unsorted subarray
        for (int i = 0; i < n - 1; i++) {
            // Find the minimum element in unsorted array arr[i...n-1]
            int minIndex = i;
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[minIndex]) {
                    minIndex = j;
                }
            }
            // Swap the found minimum element with the first element of the unsorted part
            if (minIndex != i) { // Optimization: avoid swap if already in place
                swap(arr, i, minIndex);
            }
        }
    }
    // Time: O(n^2) for all cases (best, avg, worst)
    // Space: O(1)
    // Stable: No (by default implementation, can be made stable with modifications but usually isn't)
```

**3. Insertion Sort**
*   **Concept:** Builds the final sorted array one item at a time. It iterates through the input elements and, for each element, "inserts" it into its correct position within the already sorted part of the array.
*   **Algorithm:**
    1.  Iterate from the second element (`arr`) to the last element (`i` from `1` to `n-1`). The subarray `arr[0...i-1]` is considered sorted.
    2.  Pick the current element `key = arr[i]`.
    3.  Compare `key` with elements in the sorted subarray `arr[0...i-1]` from right to left (`j` from `i-1` down to `0`).
    4.  If `arr[j] > key`, shift `arr[j]` one position to the right (`arr[j+1] = arr[j]`).
    5.  Continue shifting until a position `j` is found where `arr[j] <= key` or the beginning of the array is reached.
    6.  Insert `key` at `arr[j+1]`.
*   **Time Complexity:**
    *   **Worst Case:** O(n²) (e.g., reverse-sorted array, many shifts needed).
    *   **Average Case:** O(n²).
    *   **Best Case:** O(n) (if array is already sorted, only comparisons, no shifts).
*   **Space Complexity:** O(1) (In-place).
*   **Stability:** Yes, it is stable.
*   **Use Cases:** Efficient for small datasets or partially sorted arrays. Often used as a subroutine in more complex algorithms (e.g., Timsort uses it for small subarrays). Good for online sorting (when elements arrive one by one).

```java
// (Continuing in BasicSorting class)
    // Insertion Sort
    public void insertionSort(int[] arr) {
        if (arr == null || arr.length <= 1) return;
        int n = arr.length;

        // Start from the second element (arr[0] is considered a sorted subarray of size 1)
        for (int i = 1; i < n; i++) {
            int key = arr[i]; // The element to be inserted into the sorted portion
            int j = i - 1;    // Index for iterating through the sorted portion (arr[0...i-1])

            // Move elements of arr[0...i-1], that are greater than key,
            // to one position ahead of their current position
            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j]; // Shift element to the right
                j--;
            }
            // Place the key at its correct position in sorted subarray
            arr[j + 1] = key;
        }
    }
    // Time: O(n^2) worst/avg, O(n) best
    // Space: O(1)
    // Stable: Yes
```

### Advanced Sorting Algorithms (Often O(n log n))

These are generally more efficient for larger datasets.

**1. Merge Sort**
*   **Concept:** A **Divide and Conquer** algorithm.
    1.  **Divide:** Recursively divide the array into two halves until each subarray contains a single element (which is trivially sorted).
    2.  **Conquer:** Merge the sorted subarrays back together to produce larger sorted subarrays, until the entire array is merged and sorted.
*   **Merge Step (Key Part):** Takes two sorted subarrays and merges them into a single sorted array. This is done by using two pointers, one for each subarray, and comparing elements to pick the smaller one to add to the merged array.
*   **Time Complexity:**
    *   **Worst Case:** O(n log n) (Division takes log n levels, merging at each level takes O(n)).
    *   **Average Case:** O(n log n).
    *   **Best Case:** O(n log n).
*   **Space Complexity:** O(n) (Out-of-place, requires temporary arrays for merging).
*   **Stability:** Yes, it is stable (if merge operation is implemented carefully).
*   **Use Cases:** Very reliable O(n log n) performance. Good for external sorting. Used in Timsort (Python's default sort).

```java
public class MergeSort {
    public void sort(int[] arr) {
        if (arr == null || arr.length <= 1) return;
        mergeSortRecursive(arr, 0, arr.length - 1);
    }

    private void mergeSortRecursive(int[] arr, int left, int right) {
        if (left < right) { // Base case: if left >= right, subarray has 0 or 1 element (sorted)
            int mid = left + (right - left) / 2; // Find the middle point

            // Recursively sort the two halves
            mergeSortRecursive(arr, left, mid);      // Sort left subarray arr[left...mid]
            mergeSortRecursive(arr, mid + 1, right); // Sort right subarray arr[mid+1...right]

            // Merge the sorted halves
            merge(arr, left, mid, right);
        }
    }

    // Merges two sorted subarrays arr[left...mid] and arr[mid+1...right]
    private void merge(int[] arr, int left, int mid, int right) {
        // Find sizes of two subarrays to be merged
        int n1 = mid - left + 1;
        int n2 = right - mid;

        // Create temporary arrays
        int[] L = new int[n1];
        int[] R = new int[n2];

        // Copy data to temporary arrays L[] and R[]
        for (int i = 0; i < n1; ++i) {
            L[i] = arr[left + i];
        }
        for (int j = 0; j < n2; ++j) {
            R[j] = arr[mid + 1 + j];
        }

        // Merge the temporary arrays back into arr[left...right]
        int i = 0, j = 0; // Initial indices of first and second subarrays
        int k = left;     // Initial index of merged subarray in original arr

        while (i < n1 && j < n2) {
            if (L[i] <= R[j]) { // For stability, use <=
                arr[k] = L[i];
                i++;
            } else {
                arr[k] = R[j];
                j++;
            }
            k++;
        }

        // Copy remaining elements of L[] if any
        while (i < n1) {
            arr[k] = L[i];
            i++;
            k++;
        }

        // Copy remaining elements of R[] if any
        while (j < n2) {
            arr[k] = R[j];
            j++;
            k++;
        }
    }
    // Time: O(n log n) for all cases
    // Space: O(n) due to temporary arrays
    // Stable: Yes
}
```

**2. Quick Sort**
*   **Concept:** Also a **Divide and Conquer** algorithm.
    1.  **Pick a Pivot:** Choose an element from the array as a pivot (e.g., first, last, median, random).
    2.  **Partition:** Rearrange the array such that all elements smaller than the pivot come before it, and all elements greater than the pivot come after it. Elements equal to the pivot can go on either side. After partitioning, the pivot is in its final sorted position.
    3.  **Recurse:** Recursively apply Quick Sort to the sub-array of elements smaller than the pivot and the sub-array of elements greater than the pivot.
*   **Partition Step (Key Part):** Various schemes exist (e.g., Lomuto, Hoare). Lomuto is often simpler to implement.
*   **Time Complexity:**
    *   **Worst Case:** O(n²) (Occurs when the pivot selection consistently leads to highly unbalanced partitions, e.g., picking the smallest/largest element in an already sorted array).
    *   **Average Case:** O(n log n).
    *   **Best Case:** O(n log n) (When partitions are well-balanced).
*   **Space Complexity:** O(log n) (Average, due to recursion call stack). O(n) in the worst case (skewed recursion). It's considered in-place as it modifies the array directly, and the auxiliary space is for recursion.
*   **Stability:** No, it is generally not stable (depends on partition implementation).
*   **Use Cases:** Very fast on average. Widely used. Choice of pivot is crucial. Randomized pivot selection or median-of-three helps avoid worst-case scenarios.

```java
public class QuickSort {
    private void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

    public void sort(int[] arr) {
        if (arr == null || arr.length <= 1) return;
        quickSortRecursive(arr, 0, arr.length - 1);
    }

    private void quickSortRecursive(int[] arr, int low, int high) {
        if (low < high) {
            // pi is partitioning index, arr[pi] is now at right place
            int partitionIndex = partitionLomuto(arr, low, high);

            // Separately sort elements before partition and after partition
            quickSortRecursive(arr, low, partitionIndex - 1);
            quickSortRecursive(arr, partitionIndex + 1, high);
        }
    }

    // Lomuto partition scheme:
    // Takes last element as pivot, places the pivot element at its
    // correct position in sorted array, and places all smaller (smaller than pivot)
    // to left of pivot and all greater elements to right of pivot.
    private int partitionLomuto(int[] arr, int low, int high) {
        int pivot = arr[high]; // Choose the last element as pivot
        int i = (low - 1);     // Index of smaller element, indicates the right position of pivot found so far

        for (int j = low; j < high; j++) {
            // If current element is smaller than or equal to pivot
            if (arr[j] <= pivot) {
                i++; // Increment index of smaller element
                swap(arr, i, j);
            }
        }
        // Place pivot at its correct position by swapping arr[i+1] and arr[high] (or pivot)
        swap(arr, i + 1, high);
        return (i + 1); // Return the partitioning index
    }

    // Randomized Quick Sort (to improve chances of good pivot selection)
    public void sortRandomized(int[] arr) {
        if (arr == null || arr.length <= 1) return;
        quickSortRandomizedRecursive(arr, 0, arr.length - 1);
    }

    private void quickSortRandomizedRecursive(int[] arr, int low, int high) {
        if (low < high) {
            // Randomly pick a pivot and move it to the end for Lomuto partition
            int randomIndex = low + (int)(Math.random() * (high - low + 1));
            swap(arr, randomIndex, high);

            int partitionIndex = partitionLomuto(arr, low, high);

            quickSortRandomizedRecursive(arr, low, partitionIndex - 1);
            quickSortRandomizedRecursive(arr, partitionIndex + 1, high);
        }
    }
    // Time: O(n log n) avg/best, O(n^2) worst (less likely with randomization)
    // Space: O(log n) avg (recursion stack), O(n) worst
    // Stable: No
}
```

**3. Heap Sort**
*   **Concept:** Uses a Binary Heap data structure.
    1.  **Build Heap:** Convert the input array into a Max-Heap (or Min-Heap for descending sort). The largest (or smallest) element will be at the root. This takes O(n) time.
    2.  **Sort:** Repeatedly extract the maximum element from the heap:
        a.  Swap the root element (max) with the last element of the heap.
        b.  Reduce the heap size by one (effectively placing the max element at the end of the sorted portion).
        c.  Call `heapify` (or `siftDown`) on the new root to restore the heap property for the reduced heap.
        d.  Repeat `n-1` times. Each extraction takes O(log n).
*   **Time Complexity:**
    *   **Worst Case:** O(n log n).
    *   **Average Case:** O(n log n).
    *   **Best Case:** O(n log n).
*   **Space Complexity:** O(1) (In-place, if heap is built within the input array).
*   **Stability:** No, it is not stable.
*   **Use Cases:** Good worst-case time complexity. In-place. Often used when O(n log n) worst-case is required without extra space (unlike Merge Sort).

```java
public class HeapSort {
    private void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

    public void sort(int[] arr) {
        if (arr == null || arr.length <= 1) return;
        int n = arr.length;

        // 1. Build Max-Heap (rearrange array)
        // Start from the last non-leaf node (n/2 - 1) and heapify down to the root.
        for (int i = n / 2 - 1; i >= 0; i--) {
            heapify(arr, n, i); // n is the current size of the heap
        }

        // 2. One by one extract an element from heap and place it at the end
        for (int i = n - 1; i > 0; i--) {
            // Move current root (maximum element) to the end (arr[i])
            swap(arr, 0, i);

            // Call max heapify on the reduced heap (size is i, root is 0)
            // This ensures the largest remaining element moves to the root.
            heapify(arr, i, 0);
        }
    }

    // To heapify a subtree rooted with node i which is an index in arr[].
    // n is size of heap.
    private void heapify(int[] arr, int n, int i) {
        int largest = i;     // Initialize largest as root
        int leftChild = 2 * i + 1;
        int rightChild = 2 * i + 2;

        // If left child is larger than root
        if (leftChild < n && arr[leftChild] > arr[largest]) {
            largest = leftChild;
        }

        // If right child is larger than largest so far
        if (rightChild < n && arr[rightChild] > arr[largest]) {
            largest = rightChild;
        }

        // If largest is not root
        if (largest != i) {
            swap(arr, i, largest);

            // Recursively heapify the affected sub-tree
            heapify(arr, n, largest);
        }
    }
    // Time: O(n log n) for all cases
    // Space: O(1) (in-place)
    // Stable: No
}
```

### Specialized Sorting Algorithms (Linear Time Potential)

These algorithms can achieve better than O(n log n) time complexity under specific assumptions about the input data. They are not comparison-based.

**1. Counting Sort**
*   **Concept:** Works by counting the number of occurrences of each distinct element in the input array. Then, it uses these counts to determine the positions of each element in the sorted output array.
*   **Assumptions:** Input elements are integers within a known, relatively small range `k` (max value - min value + 1).
*   **Algorithm:**
    1.  Find the maximum (and minimum, if range is not 0-based) element to determine the range `k`.
    2.  Create a `count` array of size `k`, initialized to zeros.
    3.  Iterate through the input array: for each element `x`, increment `count[x - min]`.
    4.  Modify the `count` array: for each `i`, `count[i]` now stores the sum of counts up to `i`. This gives the ending position of elements with value `i + min` in the sorted array.
    5.  Create an `output` array. Iterate through the input array in reverse (to maintain stability):
        Place element `x` at index `count[x - min] - 1` in the `output` array.
        Decrement `count[x - min]`.
    6.  Copy the `output` array back to the original array.
*   **Time Complexity:** O(n + k) where `n` is number of elements and `k` is the range of input. If `k = O(n)`, then O(n).
*   **Space Complexity:** O(n + k) (for `count` and `output` arrays). Can be O(k) if modifying input array carefully.
*   **Stability:** Yes, it is stable (if implemented as described, especially step 5).
*   **Use Cases:** Efficient when `k` is not significantly larger than `n`. Used as a subroutine in Radix Sort.

```java
public class SpecializedSorting {
    // Counting Sort
    public void countingSort(int[] arr) {
        if (arr == null || arr.length <= 1) return;

        // Find min and max to determine range
        int max = arr[0];
        int min = arr[0];
        for (int num : arr) {
            if (num > max) max = num;
            if (num < min) min = num;
        }

        int range = max - min + 1;
        int[] count = new int[range]; // Stores counts of each element
        int[] output = new int[arr.length]; // Stores sorted output

        // 1. Store count of each character
        for (int num : arr) {
            count[num - min]++;
        }

        // 2. Change count[i] so that count[i] now contains actual
        //    position of this character in output array (cumulative count)
        for (int i = 1; i < range; i++) {
            count[i] += count[i - 1];
        }

        // 3. Build the output character array
        //    Iterate from end of input array to maintain stability
        for (int i = arr.length - 1; i >= 0; i--) {
            int num = arr[i];
            output[count[num - min] - 1] = num;
            count[num - min]--; // Decrement count for this number
        }

        // 4. Copy the output array to arr, so that arr now
        //    contains sorted characters
        System.arraycopy(output, 0, arr, 0, arr.length);
    }
    // Time: O(n + k) where k is range (max-min+1)
    // Space: O(n + k) or O(k) if modifying input carefully (though output array makes it O(n+k))
    // Stable: Yes
}
```

**2. Radix Sort**
*   **Concept:** Sorts integers (or strings) by processing individual digits (or characters). It repeatedly sorts the numbers by each digit, from the least significant digit (LSD) to the most significant digit (MSD), or vice-versa (MSD radix sort is also possible but less common for integers). It uses a stable sorting algorithm (like Counting Sort) as a subroutine for sorting by each digit.
*   **Algorithm (LSD Radix Sort for Integers):**
    1.  Find the maximum number to determine the number of digits (`d`).
    2.  For each digit position `exp` (from 1, 10, 100, ... up to `d`-th digit):
        Sort the input array stably based on the digit at the current `exp` position using Counting Sort (or another stable sort suitable for small ranges like 0-9).
*   **Time Complexity:** O(d * (n + k)) where `d` is the number of digits in the maximum number, `n` is the number of elements, and `k` is the base (radix, usually 10 for decimal numbers, or size of alphabet for strings). If `d` is constant and `k = O(n)`, it can be O(n).
*   **Space Complexity:** O(n + k) (due to the stable sort subroutine, typically Counting Sort).
*   **Stability:** Yes, if the underlying sorting algorithm used for digits is stable.
*   **Use Cases:** Efficient for sorting integers or strings with fixed-size keys.

```java
// (Continuing in SpecializedSorting class)
    // Radix Sort (LSD for non-negative integers)
    public void radixSort(int[] arr) {
        if (arr == null || arr.length <= 1) return;

        // Find the maximum number to know number of digits
        int max = arr[0];
        for (int num : arr) {
            if (num > max) max = num;
        }

        // Do counting sort for every digit. Note that instead of passing digit number,
        // exp is passed. exp is 10^i where i is current digit number.
        for (int exp = 1; max / exp > 0; exp *= 10) {
            countingSortByDigit(arr, exp);
        }
    }

    // A helper function for Radix Sort to perform Counting Sort based on a specific digit (exp).
    private void countingSortByDigit(int[] arr, int exp) {
        int n = arr.length;
        int[] output = new int[n]; // Output array
        int[] count = new int[10]; // Digits are 0-9

        // Store count of occurrences of digits
        for (int i = 0; i < n; i++) {
            count[(arr[i] / exp) % 10]++;
        }

        // Change count[i] so that count[i] now contains
        // actual position of this digit in output[]
        for (int i = 1; i < 10; i++) {
            count[i] += count[i - 1];
        }

        // Build the output array (iterate from end for stability)
        for (int i = n - 1; i >= 0; i--) {
            int digitIndex = (arr[i] / exp) % 10;
            output[count[digitIndex] - 1] = arr[i];
            count[digitIndex]--;
        }

        // Copy the output array to arr[], so that arr[] now
        // contains numbers sorted according to current digit
        System.arraycopy(output, 0, arr, 0, n);
    }
    // Time: O(d * (n + k)) where d is num digits, k is radix (10)
    // Space: O(n + k)
    // Stable: Yes (because countingSortByDigit is stable)
}
```

**3. Bucket Sort**
*   **Concept:** Distributes elements into a number of "buckets". Each bucket is then sorted individually, either using a different sorting algorithm or by recursively applying Bucket Sort. Finally, the elements from the sorted buckets are concatenated.
*   **Assumptions:** Input data is uniformly distributed over a range.
*   **Algorithm:**
    1.  Create `m` empty buckets (usually `m=n`, where `n` is number of elements).
    2.  For each element in the input array, map it to a bucket (e.g., for numbers in `[0,1)`, map `x` to bucket `floor(n*x)`). Add the element to that bucket.
    3.  Sort each non-empty bucket (e.g., using Insertion Sort or another Bucket Sort).
    4.  Concatenate the sorted buckets to get the final sorted array.
*   **Time Complexity:**
    *   **Average Case:** O(n + k) or O(n) if elements are uniformly distributed and bucket sorting is efficient (k is number of buckets, or if sorting buckets takes linear time). If `k=n` and sorting buckets takes O(1) on average (e.g. few elements per bucket), then O(n).
    *   **Worst Case:** O(n²) if all elements fall into a single bucket and a slow sort (like Insertion Sort) is used for buckets.
*   **Space Complexity:** O(n + k) or O(n) for buckets and elements.
*   **Stability:** Can be stable if the sorting algorithm used for buckets is stable and elements are inserted into buckets in order.
*   **Use Cases:** Effective when input is uniformly distributed.

```java
// (Continuing in SpecializedSorting class)
    // Bucket Sort (for floating point numbers in range [0, 1) for this example)
    public void bucketSort(float[] arr) {
        if (arr == null || arr.length <= 1) return;
        int n = arr.length;

        // 1. Create n empty buckets
        @SuppressWarnings("unchecked") // For generic array list creation
        List<Float>[] buckets = new ArrayList[n];
        for (int i = 0; i < n; i++) {
            buckets[i] = new ArrayList<Float>();
        }

        // 2. Put array elements in different buckets
        // Assuming elements are uniformly distributed in [0, 1)
        for (int i = 0; i < n; i++) {
            int bucketIndex = (int) (n * arr[i]); // Map element to a bucket
            // Handle edge case where arr[i] = 1.0 (should go into last bucket if range is [0,1])
            if (bucketIndex >= n) bucketIndex = n - 1;
            buckets[bucketIndex].add(arr[i]);
        }

        // 3. Sort individual buckets (e.g., using Collections.sort which uses Timsort)
        for (int i = 0; i < n; i++) {
            Collections.sort(buckets[i]); // Timsort is O(m log m) for bucket of size m
        }

        // 4. Concatenate all buckets into arr[]
        int index = 0;
        for (int i = 0; i < n; i++) {
            for (float val : buckets[i]) {
                arr[index++] = val;
            }
        }
    }
    // Time: O(n) average (if uniform distribution and efficient bucket sort), O(n^2) worst
    // Space: O(n) for buckets
    // Stable: Yes (if bucket sort is stable and items added to buckets in order)
```

---



## 8. Searching Algorithms

Searching algorithms are designed to find the location of a specific element (target) within a data structure, or to determine if the element exists.

### Linear Search

*   **Concept:** The simplest searching algorithm. It sequentially checks each element of the list until a match is found or the whole list has been searched.
*   **Data Structure:** Works on any list-like structure, typically arrays or linked lists. Does not require the data to be sorted.
*   **Algorithm:**
    1.  Iterate through the collection from the first element to the last.
    2.  In each step, compare the current element with the target value.
    3.  If a match is found, return the index (or true).
    4.  If the end of the collection is reached without finding the target, return an indicator that it's not found (e.g., -1 or false).
*   **Time Complexity:**
    *   **Worst Case:** O(n) (Target is the last element or not present; have to scan the entire list).
    *   **Average Case:** O(n) (On average, scan n/2 elements).
    *   **Best Case:** O(1) (Target is the first element).
*   **Space Complexity:** O(1) (Iterative version).
*   **Use Cases:**
    *   Small datasets.
    *   Unsorted data where other algorithms are not applicable.
    *   Simple to implement.

```java
public class SearchingAlgorithms {
    // Linear Search
    // Returns the index of the target in the array, or -1 if not found.
    public int linearSearch(int[] arr, int target) {
        if (arr == null || arr.length == 0) {
            return -1;
        }
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == target) {
                return i; // Target found at index i
            }
        }
        return -1; // Target not found
    }
    // Time: O(n) worst/avg, O(1) best
    // Space: O(1)
}
```

### Binary Search and Variations

*   **Concept:** A highly efficient searching algorithm that works on **sorted** data structures (typically arrays). It follows a divide and conquer approach.
*   **Algorithm:**
    1.  Compare the target value with the middle element of the sorted array.
    2.  If the target matches the middle element, its position is found.
    3.  If the target is less than the middle element, narrow the search to the lower (left) half of the array.
    4.  If the target is greater than the middle element, narrow the search to the upper (right) half of the array.
    5.  Repeat steps 1-4 with the new subarray until the target is found or the subarray size becomes zero (target not found).
*   **Prerequisite:** The array **must be sorted**.
*   **Time Complexity:**
    *   **Worst Case:** O(log n) (Each step halves the search space).
    *   **Average Case:** O(log n).
    *   **Best Case:** O(1) (Target is the middle element on the first try).
*   **Space Complexity:**
    *   **Iterative version:** O(1).
    *   **Recursive version:** O(log n) (due to recursion call stack).
*   **Use Cases:**
    *   Searching in large, sorted datasets.
    *   Foundation for many other algorithms and problems (e.g., finding first/last occurrence, square root, searching in rotated arrays).

```java
// (Continuing in SearchingAlgorithms class)

    // Classic Binary Search (Iterative)
    // Returns the index of the target in the sorted array, or -1 if not found.
    public int binarySearchIterative(int[] sortedArr, int target) {
        if (sortedArr == null || sortedArr.length == 0) {
            return -1;
        }
        int left = 0;
        int right = sortedArr.length - 1;

        while (left <= right) {
            // int mid = (left + right) / 2; // Can cause overflow if left+right is too large
            int mid = left + (right - left) / 2; // Preferred way to calculate mid

            if (sortedArr[mid] == target) {
                return mid; // Target found at index mid
            } else if (sortedArr[mid] < target) {
                left = mid + 1; // Search in the right half
            } else { // sortedArr[mid] > target
                right = mid - 1; // Search in the left half
            }
        }
        return -1; // Target not found
    }
    // Time: O(log n)
    // Space: O(1)

    // Recursive Binary Search
    public int binarySearchRecursive(int[] sortedArr, int target) {
        if (sortedArr == null || sortedArr.length == 0) {
            return -1;
        }
        return binarySearchRecursiveHelper(sortedArr, target, 0, sortedArr.length - 1);
    }

    private int binarySearchRecursiveHelper(int[] sortedArr, int target, int left, int right) {
        if (left > right) { // Base case: search space is exhausted
            return -1;
        }

        int mid = left + (right - left) / 2;

        if (sortedArr[mid] == target) {
            return mid;
        } else if (sortedArr[mid] < target) {
            return binarySearchRecursiveHelper(sortedArr, target, mid + 1, right);
        } else { // sortedArr[mid] > target
            return binarySearchRecursiveHelper(sortedArr, target, left, mid - 1);
        }
    }
    // Time: O(log n)
    // Space: O(log n) for recursion stack

    // --- Binary Search Variations ---

    // Find First Occurrence of an element in a sorted array (if duplicates exist)
    public int findFirstOccurrence(int[] sortedArr, int target) {
        if (sortedArr == null || sortedArr.length == 0) return -1;
        int left = 0, right = sortedArr.length - 1;
        int result = -1; // Store the potential first occurrence index

        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (sortedArr[mid] == target) {
                result = mid;      // Found a potential answer
                right = mid - 1;   // Try to find an earlier occurrence in the left half
            } else if (sortedArr[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return result;
    }

    // Find Last Occurrence of an element in a sorted array (if duplicates exist)
    public int findLastOccurrence(int[] sortedArr, int target) {
        if (sortedArr == null || sortedArr.length == 0) return -1;
        int left = 0, right = sortedArr.length - 1;
        int result = -1; // Store the potential last occurrence index

        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (sortedArr[mid] == target) {
                result = mid;     // Found a potential answer
                left = mid + 1;   // Try to find a later occurrence in the right half
            } else if (sortedArr[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return result;
    }

    // Count Occurrences of an element = (Last Occurrence - First Occurrence + 1)

    // Search in a Rotated Sorted Array (unique elements assumed)
    // e.g., [4, 5, 6, 7, 0, 1, 2] was originally [0, 1, 2, 4, 5, 6, 7]
    public int searchInRotatedSortedArray(int[] nums, int target) {
        if (nums == null || nums.length == 0) return -1;
        int left = 0, right = nums.length - 1;

        while (left <= right) {
            int mid = left + (right - left) / 2;

            if (nums[mid] == target) {
                return mid;
            }

            // Check if the left half [left...mid] is sorted
            if (nums[left] <= nums[mid]) { // Note: <= is important for 2 elements case
                // If left half is sorted, check if target lies in this half
                if (target >= nums[left] && target < nums[mid]) {
                    right = mid - 1; // Search left
                } else {
                    left = mid + 1;  // Search right
                }
            }
            // Otherwise, the right half [mid...right] must be sorted
            else {
                // If right half is sorted, check if target lies in this half
                if (target > nums[mid] && target <= nums[right]) {
                    left = mid + 1;  // Search right
                } else {
                    right = mid - 1; // Search left
                }
            }
        }
        return -1; // Target not found
    }

    // Find Peak Element in an array
    // A peak element is an element that is strictly greater than its neighbors.
    // Array may contain multiple peaks, return index of any one.
    // Assume nums[-1] = nums[n] = -infinity.
    public int findPeakElement(int[] nums) {
        if (nums == null || nums.length == 0) return -1; // Or throw exception
        int left = 0, right = nums.length - 1;

        while (left < right) { // Loop until left and right converge
            int mid = left + (right - left) / 2;
            // If nums[mid] is less than its right neighbor, a peak must be in the right half
            // (mid could be part of an upward slope leading to a peak on the right)
            if (nums[mid] < nums[mid + 1]) {
                left = mid + 1;
            }
            // Otherwise (nums[mid] >= nums[mid+1]), mid could be a peak,
            // or a peak is in the left half (or mid itself is the peak).
            else {
                right = mid; // Include mid as it could be the peak
            }
        }
        // When left == right, we've found a peak.
        return left; // or right, as they are equal
    }

    // Search in a 2D Matrix (sorted rows, first element of row > last of previous row)
    // Matrix properties:
    // 1. Integers in each row are sorted from left to right.
    // 2. The first integer of each row is greater than the last integer of the previous row.
    // This means the matrix can be "flattened" into a single sorted 1D array conceptually.
    public boolean searchIn2DMatrix(int[][] matrix, int target) {
        if (matrix == null || matrix.length == 0 || matrix[0].length == 0) {
            return false;
        }
        int rows = matrix.length;
        int cols = matrix[0].length;

        // Treat the 2D matrix as a flattened 1D sorted array of size rows * cols
        int left = 0;
        int right = rows * cols - 1;

        while (left <= right) {
            int mid_idx = left + (right - left) / 2;
            // Convert 1D mid_idx back to 2D row and col
            int mid_val = matrix[mid_idx / cols][mid_idx % cols];

            if (mid_val == target) {
                return true;
            } else if (mid_val < target) {
                left = mid_idx + 1;
            } else {
                right = mid_idx - 1;
            }
        }
        return false;
    }
}
```

### Advanced Search Problems

(Referencing the problems from your provided example, with enhanced explanations where needed)

```java
public class AdvancedSearchProblems { // New class for these specific problems

    // Find Minimum in Rotated Sorted Array (unique elements assumed)
    // e.g., [3,4,5,1,2] -> min is 1
    // e.g., [4,5,6,7,0,1,2] -> min is 0
    // e.g., [11,13,15,17] -> min is 11 (no rotation or rotated by n times)
    public int findMinInRotatedSortedArray(int[] nums) {
        if (nums == null || nums.length == 0) {
            throw new IllegalArgumentException("Input array cannot be null or empty.");
        }
        int left = 0, right = nums.length - 1;

        // If the array is not rotated (or rotated n times), the first element is the minimum.
        if (nums[left] <= nums[right]) { // Check if already sorted (no rotation or full rotation)
            return nums[left];
        }

        // Binary search for the pivot point (the smallest element)
        while (left < right) { // Use left < right to ensure loop terminates and left is the answer
            int mid = left + (right - left) / 2;

            // If nums[mid] is greater than nums[right], it means the pivot (smallest element)
            // must be in the right half (mid+1 to right).
            // e.g., [3,4,5, *1*, 2], mid points to 5, right points to 2. 5 > 2. Min is in [1,2].
            if (nums[mid] > nums[right]) {
                left = mid + 1;
            }
            // If nums[mid] is less than or equal to nums[right], it means the pivot
            // could be nums[mid] itself or in the left half (left to mid).
            // e.g., [5, *1*, 2,3,4], mid points to 1, right points to 4. 1 <= 4. Min is in [5,1].
            // e.g., [2, *3*, 4,5,1], mid points to 4, right points to 1. 4 > 1. Min is in [1].
            else { // nums[mid] <= nums[right]
                right = mid; // mid could be the minimum, so include it.
            }
        }
        // When the loop ends, left (or right) points to the minimum element.
        return nums[left];
    }
    // Time: O(log n)
    // Space: O(1)

    // Median of Two Sorted Arrays (of sizes m and n)
    // Find the median of the two sorted arrays. Overall run time should be O(log(m+n)).
    // This is a complex problem often involving binary searching on the partition.
    // Conceptual Explanation:
    // The median is the element that divides the combined sorted array into two equal halves.
    // If total length (m+n) is odd, median is the middle element.
    // If total length is even, median is the average of the two middle elements.
    // We need to find a partition in both arrays (say, `partitionX` in nums1 and `partitionY` in nums2)
    // such that:
    // 1. All elements in the left part (elements before partitions) are <= all elements in the right part.
    //    Specifically, `maxLeftX <= minRightY` and `maxLeftY <= minRightX`.
    // 2. The total number of elements in the left parts equals total in right parts (or differs by 1 for odd total).
    //    `partitionX + partitionY = (m + n + 1) / 2` (this handles both odd/even total length nicely).
    // We can binary search for the optimal `partitionX` in the smaller array. `partitionY` is then determined.
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        int m = nums1.length;
        int n = nums2.length;

        // Ensure nums1 is the smaller array to simplify partitioning search space
        if (m > n) {
            return findMedianSortedArrays(nums2, nums1); // Swap arrays
        }

        int low = 0;
        int high = m; // Binary search for partitionX in nums1 (can be from 0 to m elements in left part)
        int totalLeftHalfSize = (m + n + 1) / 2; // Desired total elements in the combined left half

        while (low <= high) {
            // partitionX: number of elements from nums1 in the combined left half
            int partitionX = low + (high - low) / 2;
            // partitionY: number of elements from nums2 in the combined left half
            int partitionY = totalLeftHalfSize - partitionX;

            // Determine boundary elements (handle edge cases for empty partitions)
            int maxLeftX = (partitionX == 0) ? Integer.MIN_VALUE : nums1[partitionX - 1];
            int minRightX = (partitionX == m) ? Integer.MAX_VALUE : nums1[partitionX];

            int maxLeftY = (partitionY == 0) ? Integer.MIN_VALUE : nums2[partitionY - 1];
            int minRightY = (partitionY == n) ? Integer.MAX_VALUE : nums2[partitionY];

            // Check if partitions are correct:
            if (maxLeftX <= minRightY && maxLeftY <= minRightX) {
                // Found the correct partition
                if ((m + n) % 2 == 0) { // Even total length
                    return (Math.max(maxLeftX, maxLeftY) + Math.min(minRightX, minRightY)) / 2.0;
                } else { // Odd total length
                    return Math.max(maxLeftX, maxLeftY);
                }
            } else if (maxLeftX > minRightY) {
                // We are too far on the right for partitionX (nums1's left part is too large/values too high).
                // Move left in nums1's partition search space.
                high = partitionX - 1;
            } else { // maxLeftY > minRightX
                // We are too far on the left for partitionX (nums1's left part is too small/values too low).
                // Move right in nums1's partition search space.
                low = partitionX + 1;
            }
        }
        // Should not be reached if arrays are sorted and non-empty (or handled by swapping).
        // Can throw an exception for invalid input or if logic assumes valid inputs always lead to solution.
        throw new IllegalArgumentException("Input arrays are not sorted or other issue.");
    }
    // Time: O(log(min(m,n))) - Binary search is on the smaller array.
    // Space: O(1)
}
```

---



Okay, let's proceed with the **Hashing** section.

---

## 9. Hashing

Hashing is a fundamental technique used to uniquely identify a specific object from a group of similar objects. It involves using a **hash function** to map keys (which can be of any data type like strings, numbers, or objects) to array indices (called **hash values** or **hash codes**), which are then used to store and retrieve the corresponding values in a data structure called a **hash table** (or hash map).

**Core Components:**
1.  **Hash Function:** A function that takes a key as input and returns an integer hash value (or hash code).
    *   **Properties of a Good Hash Function:**
        *   **Deterministic:** For a given key, it must always produce the same hash value.
        *   **Efficiently Computable:** Should be fast to calculate.
        *   **Uniform Distribution:** Should distribute keys as evenly as possible across the available hash table slots to minimize collisions.
        *   **Low Collision Rate:** Different keys should ideally map to different hash values, though collisions are often unavoidable.
        *   **Avalanche Effect (Desirable):** A small change in the input key should produce a significantly different hash value.
2.  **Hash Table (Hash Map):** A data structure that stores key-value pairs. It uses a hash function to compute an index into an array of buckets or slots, from which the desired value can be found.
    *   **Bucket/Slot:** An entry in the hash table array.
3.  **Collision:** Occurs when two different keys map to the same hash table index.
4.  **Collision Resolution Technique:** Strategies to handle collisions when they occur.

**How Hashing Works (Simplified):**
1.  **Insertion:**
    *   Given a key-value pair `(k, v)`.
    *   Compute the hash value: `hash = hashFunction(k)`.
    *   Map hash to an index: `index = hash % table_size`.
    *   Store `(k, v)` at `table[index]`. If a collision occurs, use a resolution technique.
2.  **Search/Retrieval:**
    *   Given a key `k`.
    *   Compute `hash = hashFunction(k)`.
    *   Map to `index = hash % table_size`.
    *   Go to `table[index]`. If a collision resolution technique was used, search within the elements at that index for the key `k`. If found, return its value.
3.  **Deletion:**
    *   Similar to search, find the element.
    *   Remove it, handling collision resolution structure appropriately.

**Advantages of Hashing:**
*   **Fast Average Time Complexity:** O(1) on average for insertions, deletions, and searches, assuming a good hash function and effective collision resolution.
*   Widely used for implementing associative arrays, sets, and caches.

**Disadvantages of Hashing:**
*   **Worst-Case Time Complexity:** O(n) if many collisions occur and all keys map to the same slot (e.g., in a poorly designed hash table or with a bad hash function).
*   **Not Ideal for Ordered Data:** Hash tables generally do not store elements in a sorted order. Operations like finding min/max or range queries are inefficient (O(n)).
*   **Choosing a Good Hash Function:** Can be challenging.
*   **Space Overhead:** Might have empty slots, or extra space for collision resolution structures (e.g., linked lists).

### Hash Functions

The goal is to map keys to indices (typically `0` to `table_size - 1`).
1.  **Get Hash Code:** Convert the key into an integer.
    *   For integers, the integer itself can be the hash code.
    *   For strings: Sum of ASCII values, polynomial rolling hash, etc. Java's `String.hashCode()` uses a polynomial hash: `s*31^(n-1) + s*31^(n-2) + ... + s[n-1]`. The number 31 is chosen because it's an odd prime and offers good distribution.
    *   For custom objects: Override `hashCode()` (and `equals()`) method. The contract is:
        *   If `obj1.equals(obj2)` is true, then `obj1.hashCode() == obj2.hashCode()` must be true.
        *   If `obj1.hashCode() == obj2.hashCode()`, it does not imply `obj1.equals(obj2)` is true (due to collisions).
2.  **Map to Index (Compression Function):** Convert the hash code to a valid array index.
    *   **Division Method:** `index = hashCode % table_size`. `table_size` is often chosen to be a prime number to help distribute keys more uniformly.
    *   **Multiplication Method:** Less common in basic explanations.

```java
// Example: Java's String hashCode() (conceptual)
// public int hashCode() {
//     int h = 0;
//     for (int i = 0; i < length(); i++) {
//         h = 31 * h + charAt(i);
//     }
//     return h;
// }

// Custom object hashing
class Employee {
    int id;
    String name;

    public Employee(int id, String name) {
        this.id = id;
        this.name = name;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Employee employee = (Employee) o;
        return id == employee.id && Objects.equals(name, employee.name);
    }

    @Override
    public int hashCode() {
        // A common way to combine hash codes of fields
        return Objects.hash(id, name);
        // Or manually:
        // int result = Integer.hashCode(id);
        // result = 31 * result + (name != null ? name.hashCode() : 0);
        // return result;
    }
}
```

### Collision Resolution Techniques

When `hashFunction(key1) % table_size == hashFunction(key2) % table_size` for `key1 != key2`.

**1. Separate Chaining (Open Hashing)**
*   **Concept:** Each slot (bucket) in the hash table array points to a linked list (or other data structure like a balanced BST for very high collision rates) of all key-value pairs that hashed to that slot.
*   **Operations:**
    *   **Insert:** Compute index. If slot is empty, create a new list. Add the new key-value pair to the list at that index.
    *   **Search:** Compute index. Traverse the list at that index to find the key.
    *   **Delete:** Compute index. Traverse the list, find the key, and remove it.
*   **Load Factor (α):** `n / m` (where `n` = number of keys, `m` = number of slots). Average length of a chain is α.
*   **Performance:** Search time is O(1 + α) on average. If α is small (e.g., constant), it's O(1). Worst case O(n) if all keys hash to one slot.
*   **Advantages:** Simple to implement. Table doesn't "fill up" in the same way as open addressing.
*   **Disadvantages:** Overhead of linked lists (space for pointers, potential cache misses).

```java
// Conceptual structure for Separate Chaining
class ChainingHashMap<K, V> {
    private static class Entry<K, V> {
        K key;
        V value;
        Entry<K, V> next; // For linked list

        Entry(K key, V value, Entry<K, V> next) {
            this.key = key;
            this.value = value;
            this.next = next;
        }
    }

    private LinkedList<Entry<K, V>>[] table; // Array of LinkedLists
    private int capacity;
    private int size; // Number of key-value pairs

    @SuppressWarnings("unchecked")
    public ChainingHashMap(int capacity) {
        this.capacity = capacity;
        this.table = new LinkedList[capacity];
        for (int i = 0; i < capacity; i++) {
            table[i] = new LinkedList<>(); // Initialize each slot with an empty linked list
        }
        this.size = 0;
    }

    private int getHashIndex(K key) {
        if (key == null) return 0; // Handle null keys (e.g., map to index 0)
        // Ensure positive index after modulo
        return (key.hashCode() & 0x7fffffff) % capacity;
    }

    public void put(K key, V value) {
        int index = getHashIndex(key);
        LinkedList<Entry<K, V>> bucket = table[index];

        // Check if key already exists in the bucket, update if so
        for (Entry<K, V> entry : bucket) {
            if (entry.key.equals(key)) {
                entry.value = value; // Update existing key
                return;
            }
        }
        // Key not found, add new entry to the list
        bucket.add(new Entry<>(key, value, null)); // For LinkedList, next is managed by LL itself
        size++;

        // Optional: Implement resizing if load factor exceeds a threshold
        // if ((double)size / capacity > LOAD_FACTOR_THRESHOLD) resize();
    }

    public V get(K key) {
        int index = getHashIndex(key);
        LinkedList<Entry<K, V>> bucket = table[index];
        for (Entry<K, V> entry : bucket) {
            if (entry.key.equals(key)) {
                return entry.value; // Key found
            }
        }
        return null; // Key not found
    }

    public V remove(K key) {
        int index = getHashIndex(key);
        LinkedList<Entry<K, V>> bucket = table[index];
        Iterator<Entry<K, V>> iterator = bucket.iterator();
        while (iterator.hasNext()) {
            Entry<K, V> entry = iterator.next();
            if (entry.key.equals(key)) {
                iterator.remove(); // Remove from linked list
                size--;
                return entry.value;
            }
        }
        return null; // Key not found
    }
    // ... other methods like size(), isEmpty() ...
}
```

**2. Open Addressing (Closed Hashing)**
*   **Concept:** All key-value pairs are stored directly within the hash table array itself. When a collision occurs, the algorithm "probes" for the next available slot in the table according to a specific sequence.
*   **Load Factor (α):** `n / m` must be ≤ 1. Table can get full.
*   **Probing Sequences:**
    *   **a. Linear Probing:** If `table[index]` is occupied, try `table[(index + 1) % m]`, then `table[(index + 2) % m]`, and so on.
        *   **Issue:** Can lead to **primary clustering**, where long runs of occupied slots build up, increasing search times.
    *   **b. Quadratic Probing:** If `table[index]` is occupied, try `table[(index + c1*i + c2*i^2) % m]` for `i = 1, 2, ...` (where `c1, c2` are constants). More commonly, `(index + i^2) % m`.
        *   **Issue:** Can lead to **secondary clustering**, where keys that hash to the same initial slot follow the same probe sequence.
        *   Helps alleviate primary clustering. Table size `m` should ideally be prime, and load factor α < 0.5 for good performance and to ensure an empty slot can be found.
    *   **c. Double Hashing:** Uses a second hash function `hash2(key)`. If `table[index]` (where `index = hash1(key) % m`) is occupied, try `table[(index + i * hash2(key)) % m]` for `i = 1, 2, ...`.
        *   `hash2(key)` should never be 0 and should be relatively prime to `m` (e.g., `m` is prime, `1 <= hash2(key) < m`).
        *   **Benefit:** Produces a wider variety of probe sequences, significantly reducing clustering. Generally considered the best open addressing method in terms of performance.
*   **Deletion in Open Addressing:** Simply marking a slot as empty can break probe sequences for other keys. A special "deleted" marker (tombstone) is often used, which means the slot is available for insertion but should not stop a search probe. This can complicate things and lead to table degradation over time if not handled with periodic rehashing.
*   **Advantages:** No pointers, so potentially better cache performance. Can be space-efficient if load factor is high.
*   **Disadvantages:** Performance degrades significantly as load factor approaches 1. Deletion is tricky. Clustering issues.

```java
// Conceptual structure for Linear Probing
class LinearProbingHashMap<K, V> {
    private static class Entry<K, V> {
        K key;
        V value;
        boolean isActive; // To handle deletions (tombstones)

        Entry(K key, V value) {
            this.key = key;
            this.value = value;
            this.isActive = true;
        }
    }

    private Entry<K, V>[] table;
    private int capacity;
    private int size; // Number of active key-value pairs
    private static final double MAX_LOAD_FACTOR = 0.7; // Example

    @SuppressWarnings("unchecked")
    public LinearProbingHashMap(int capacity) {
        // Capacity should ideally be prime for better distribution with some probing
        this.capacity = capacity;
        this.table = new Entry[capacity];
        this.size = 0;
    }

    private int getHashIndex(K key) {
        if (key == null) throw new IllegalArgumentException("Null keys not allowed for simplicity");
        return (key.hashCode() & 0x7fffffff) % capacity;
    }

    public void put(K key, V value) {
        if ((double) (size + 1) / capacity > MAX_LOAD_FACTOR) {
            // resize(); // Implement resizing logic
        }

        int initialIndex = getHashIndex(key);
        int currentIndex = initialIndex;
        int tombstoneIndex = -1;

        do {
            if (table[currentIndex] == null) { // Empty slot found
                if (tombstoneIndex != -1) { // Prefer using a tombstone slot if available
                    table[tombstoneIndex] = new Entry<>(key, value);
                } else {
                    table[currentIndex] = new Entry<>(key, value);
                }
                size++;
                return;
            } else if (!table[currentIndex].isActive && tombstoneIndex == -1) {
                 tombstoneIndex = currentIndex; // Found a tombstone, remember it
            } else if (table[currentIndex].isActive && table[currentIndex].key.equals(key)) {
                table[currentIndex].value = value; // Update existing key
                return;
            }
            currentIndex = (currentIndex + 1) % capacity; // Linear probe
        } while (currentIndex != initialIndex); // Stop if we've circled the entire table

        // If loop finishes, table is full or only tombstones left and no empty slot
        // This should ideally be handled by resizing earlier
        if (tombstoneIndex != -1) {
            table[tombstoneIndex] = new Entry<>(key, value);
            size++;
        } else {
            throw new RuntimeException("Hash table is full or in an unexpected state.");
        }
    }

    public V get(K key) {
        int initialIndex = getHashIndex(key);
        int currentIndex = initialIndex;

        do {
            if (table[currentIndex] == null) {
                return null; // Empty slot, key not found (and no tombstone encountered that could be it)
            }
            if (table[currentIndex].isActive && table[currentIndex].key.equals(key)) {
                return table[currentIndex].value; // Key found
            }
            currentIndex = (currentIndex + 1) % capacity;
        } while (currentIndex != initialIndex && table[currentIndex] != null);
        // If loop finishes due to table[currentIndex] == null before circling, means key not found.
        // If it circles, key also not found (unless it was a tombstone we passed over).
        return null;
    }

    public V remove(K key) {
        int initialIndex = getHashIndex(key);
        int currentIndex = initialIndex;

        do {
            if (table[currentIndex] == null) {
                return null; // Key not found
            }
            if (table[currentIndex].isActive && table[currentIndex].key.equals(key)) {
                table[currentIndex].isActive = false; // Mark as deleted (tombstone)
                size--;
                return table[currentIndex].value;
            }
            currentIndex = (currentIndex + 1) % capacity;
        } while (currentIndex != initialIndex && table[currentIndex] != null);
        return null; // Key not found
    }
    // ... resize(), size(), isEmpty() ...
}
```

**Rehashing:**
When the load factor of a hash table (especially open addressing) exceeds a certain threshold, or when too many tombstones accumulate, performance degrades. Rehashing involves:
1.  Creating a new, larger hash table (often double the size and a new prime).
2.  Iterating through all active entries in the old table.
3.  Re-calculating their hash indices based on the new table size and inserting them into the new table.
This is an O(N) operation (where N is old capacity or number of elements) but happens infrequently, so amortized cost of insertions can still be O(1).

### HashMap/Hashtable Implementation Concepts (e.g., Java's `HashMap`)

Java's `HashMap` is a sophisticated implementation. Key points:
*   Uses **Separate Chaining**.
*   Each bucket is a linked list of `Node` objects (key, value, hash, next).
*   **Initial Capacity:** Default is 16.
*   **Load Factor:** Default is 0.75. If `(size / capacity) > loadFactor`, the table is **resized** (usually doubled).
*   **Hash Function:** Uses the `hashCode()` method of the key object. It then applies a supplemental hash function (to spread poor `hashCode()` implementations better) before modulo capacity.
    `index = (h = key.hashCode()) ^ (h >>> 16)) & (capacity - 1);` (if capacity is power of 2, `& (capacity-1)` is equivalent to `% capacity` but faster).
*   **Handling `null` keys:** Allows one `null` key (usually mapped to index 0).
*   **Treeifying Buckets (Java 8+):** If a linked list in a bucket becomes too long (e.g., exceeds `TREEIFY_THRESHOLD`, default 8), and the table capacity is large enough (e.g., >= `MIN_TREEIFY_CAPACITY`, default 64), the linked list is converted into a balanced **Red-Black Tree**. This improves worst-case search within that bucket from O(L) to O(log L), where L is list length. This protects against scenarios where many keys hash to the same bucket.
*   **Untreeifying:** If a treeified bucket shrinks due to removals (below `UNTREEIFY_THRESHOLD`, default 6), it's converted back to a linked list.

**`Hashtable` vs. `HashMap` in Java:**
*   **`Hashtable`:** Older, synchronized (thread-safe, but slower due to locking). Does not allow `null` keys or values.
*   **`HashMap`:** Newer, not synchronized (faster for single-threaded access). Allows one `null` key and multiple `null` values. For concurrent access, use `ConcurrentHashMap`.

Understanding these underlying concepts helps in choosing the right data structure and in designing custom hashable objects correctly (by implementing `hashCode()` and `equals()` properly).


---

## 10. Recursion and Backtracking

These are powerful problem-solving techniques often used in algorithm design.

### Recursion

**Conceptual Explanation:**
Recursion is a programming technique where a function calls itself directly or indirectly to solve a problem. It breaks down a complex problem into smaller, self-similar subproblems until a simple base case is reached, which can be solved directly. The solutions to the subproblems are then combined to solve the original problem.

**Key Components of a Recursive Algorithm:**
1.  **Base Case(s):**
    *   One or more conditions that define the simplest version of the problem, which can be solved without further recursion.
    *   Essential to prevent infinite recursion. The recursion "stops" or "unwinds" from the base case.
2.  **Recursive Step (Recursive Call):**
    *   The part of the function where it calls itself with a modified input, moving closer to the base case.
    *   The problem is broken down into smaller or simpler versions of itself.
3.  **Combining Solutions (Implicit or Explicit):**
    *   How the results from the recursive calls are used to solve the current subproblem.

**How Recursion Works (Call Stack):**
When a function calls itself, a new **stack frame** is created on the program's **call stack**. This frame stores:
*   Local variables of the current function call.
*   Parameters passed to the function.
*   The return address (where to resume execution after the recursive call finishes).
When a recursive call returns, its stack frame is popped off the stack, and execution resumes in the caller's context.

**Advantages of Recursion:**
*   **Elegance and Readability:** Can lead to very concise and intuitive solutions for problems that are naturally recursive (e.g., tree traversals, factorial, Fibonacci).
*   **Problem Decomposition:** Helps in breaking down complex problems into simpler, manageable parts.
*   Naturally reflects mathematical definitions (e.g., recurrence relations).

**Disadvantages of Recursion:**
*   **Stack Overflow:** If the recursion is too deep (too many nested calls without reaching a base case quickly enough), the call stack can run out of memory, leading to a stack overflow error.
*   **Performance Overhead:** Function calls have some overhead (creating stack frames, parameter passing). For some problems, an iterative solution might be more efficient in terms of time and space.
*   **Debugging:** Can sometimes be harder to trace and debug than iterative solutions.

**When to Use Recursion:**
*   Problems that can be defined in terms of smaller instances of themselves (e.g., Factorial, Fibonacci).
*   Problems involving hierarchical data structures like trees and graphs (e.g., traversals, search).
*   Divide and Conquer algorithms (e.g., Merge Sort, Quick Sort).
*   Backtracking algorithms.

**Converting Recursion to Iteration:**
Many recursive algorithms can be converted to iterative solutions, often using an explicit stack data structure to simulate the call stack. Tail recursion (where the recursive call is the very last operation) can sometimes be optimized by compilers into iteration (Tail Call Optimization - TCO), though not all languages/compilers support this extensively (Java generally does not perform TCO in a way that avoids stack growth for general recursion).

**Examples:**

```java
public class RecursionExamples {

    // Factorial: n! = n * (n-1)!
    public int factorial(int n) {
        // Base Case: 0! = 1, 1! = 1
        if (n < 0) {
            throw new IllegalArgumentException("Factorial is not defined for negative numbers.");
        }
        if (n == 0 || n == 1) {
            return 1;
        }
        // Recursive Step: n * factorial(n-1)
        return n * factorial(n - 1);
    }
    // Time: O(n), Space: O(n) for call stack

    // Fibonacci Sequence: F(n) = F(n-1) + F(n-2)
    // Naive recursive solution (inefficient due to re-computation)
    public int fibonacciNaive(int n) {
        if (n < 0) {
            throw new IllegalArgumentException("Fibonacci is not defined for negative numbers.");
        }
        // Base Cases: F(0) = 0, F(1) = 1
        if (n == 0) {
            return 0;
        }
        if (n == 1) {
            return 1;
        }
        // Recursive Step
        return fibonacciNaive(n - 1) + fibonacciNaive(n - 2);
    }
    // Time: O(2^n) - exponential, very inefficient
    // Space: O(n) for call stack

    // Fibonacci with Memoization (Top-Down Dynamic Programming using recursion)
    public int fibonacciMemoized(int n) {
        if (n < 0) {
            throw new IllegalArgumentException("Fibonacci is not defined for negative numbers.");
        }
        int[] memo = new int[n + 1]; // memo[i] stores F(i)
        java.util.Arrays.fill(memo, -1); // Initialize with a value indicating not computed
        return fibonacciMemoHelper(n, memo);
    }

    private int fibonacciMemoHelper(int n, int[] memo) {
        if (n == 0) return 0;
        if (n == 1) return 1;

        // If already computed, return stored value
        if (memo[n] != -1) {
            return memo[n];
        }

        // Compute and store before returning
        memo[n] = fibonacciMemoHelper(n - 1, memo) + fibonacciMemoHelper(n - 2, memo);
        return memo[n];
    }
    // Time: O(n) - each F(i) computed once
    // Space: O(n) for call stack and memo array

    // Recursive Binary Search (already covered in Searching Algorithms)
    // Tree Traversals (Inorder, Preorder, Postorder - already covered in Trees)
}
```

**Divide and Conquer Strategy (often implemented recursively):**
1.  **Divide:** Break the problem into several smaller, independent subproblems of the same type.
2.  **Conquer:** Solve the subproblems recursively. If the subproblem sizes are small enough, solve them directly (base case).
3.  **Combine:** Combine the solutions to the subproblems to form the solution to the original problem.
    *   *Examples:* Merge Sort, Quick Sort, Karatsuba algorithm for fast multiplication.

### Backtracking

**Conceptual Explanation:**
Backtracking is an algorithmic technique for solving problems recursively by trying to build a solution incrementally, one piece at a time, and removing those solutions ("backtracking") that fail to satisfy the constraints of the problem at any point in time.

It's a refined brute-force approach where we explore all possible candidates for a solution. If a partial candidate is found to not lead to a complete solution, we "prune" that branch of the search space and backtrack to try another path.

**General Algorithm Structure:**
```
boolean solve(configuration C) {
    if (is_solution(C)) {
        return true; // Found a solution
    }

    for (each possible next_choice P from C) {
        if (is_valid(P)) {
            add_choice(P to C);      // Make the choice
            if (solve(C_with_P)) {   // Recurse
                return true;
            }
            remove_choice(P from C); // Backtrack: undo the choice
        }
    }
    return false; // No solution found from this configuration
}
```

**Key Characteristics:**
*   **State Space Tree:** The process of exploring solutions can be visualized as a tree where nodes represent partial solutions and edges represent choices. Backtracking is a depth-first traversal of this state space tree.
*   **Pruning:** The power of backtracking comes from its ability to abandon paths that are determined not to lead to a solution, thereby "pruning" branches of the search tree.
*   **Recursive Nature:** Naturally implemented using recursion. Each recursive call explores a new choice.
*   **Incremental Construction:** Solutions are built step-by-step.

**When to Use Backtracking:**
*   Problems involving finding all possible solutions or one optimal solution that satisfies a set of constraints.
*   Decision problems (is there a solution?), optimization problems (what is the best solution?), enumeration problems (find all solutions).
*   Examples:
    *   N-Queens problem
    *   Sudoku solver
    *   Generating permutations and combinations
    *   Maze solving / Pathfinding
    *   Graph coloring
    *   Subset sum problem

**Example: N-Queens Problem (Conceptual)**
Place N chess queens on an N×N chessboard such that no two queens threaten each other (no two queens on the same row, column, or diagonal).

**Backtracking Approach for N-Queens:**
1.  Start placing queens row by row (or column by column).
2.  For the current row, try placing a queen in each column `j`.
3.  **Check Validity:** Before placing, check if this position `(row, j)` is safe (not attacked by queens already placed in previous rows).
4.  **Make Choice:** If safe, place the queen.
5.  **Recurse:** Move to the next row and try to place the next queen: `solve(row + 1)`.
6.  **Backtrack:**
    *   If the recursive call returns `true` (meaning a solution was found for subsequent rows), then propagate `true` upwards.
    *   If the recursive call returns `false` (meaning no valid placement for queens in subsequent rows from the current choice), then remove the queen from `(row, j)` (undo the choice) and try the next column `j+1` in the current row.
7.  **Base Case:** If all N queens have been placed (`row == N`), a solution is found.

```java
// Example: Generating all permutations of a string
public class BacktrackingPermutations {

    public List<String> generatePermutations(String str) {
        List<String> result = new ArrayList<>();
        if (str == null || str.length() == 0) return result;
        backtrack(str.toCharArray(), 0, result);
        return result;
    }

    // Uses the "swap" method for generating permutations in-place
    private void backtrack(char[] arr, int index, List<String> result) {
        // Base Case: If index reaches array length, a full permutation is formed
        if (index == arr.length) {
            result.add(new String(arr));
            return;
        }

        // Recursive Step: Iterate through possible characters for the current 'index'
        for (int i = index; i < arr.length; i++) {
            // 1. Make a choice: Swap character at 'index' with character at 'i'
            // This brings arr[i] to the current position (index) to be fixed.
            swap(arr, index, i);

            // 2. Recurse: Find permutations for the rest of the array (from index + 1)
            backtrack(arr, index + 1, result);

            // 3. Backtrack: Undo the choice (swap back to restore original order for next iteration)
            // This is crucial so that the next iteration of the for loop (for a different 'i')
            // starts with the array state as it was before this choice of fixing arr[i] at 'index'.
            swap(arr, index, i);
        }
    }

    private void swap(char[] arr, int i, int j) {
        char temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }
    // Time: O(N * N!) - N! permutations, and each takes O(N) to construct string.
    // (If just printing, and char array ops are O(1), it's closer to N! recursive calls * O(N) per call for loop)
    // Space: O(N) for recursion stack depth and O(N) for storing the char array. String construction also takes space.
}

// Example: Subset Sum (Find if any subset sums to target)
public class SubsetSumProblem {
    public boolean canPartition(int[] nums, int targetSum) {
        if (nums == null || nums.length == 0) return targetSum == 0;
        return findSubsetSum(nums, targetSum, 0);
    }

    private boolean findSubsetSum(int[] nums, int remainingSum, int index) {
        // Base Cases
        if (remainingSum == 0) { // Found a subset that sums to the original target
            return true;
        }
        if (index == nums.length || remainingSum < 0) { // Reached end of array or sum became negative
            return false;
        }

        // Recursive Step:
        // Choice 1: Include the current element nums[index] in the subset
        if (findSubsetSum(nums, remainingSum - nums[index], index + 1)) {
            return true;
        }

        // Choice 2: Exclude the current element nums[index] from the subset (Backtrack implicitly by not including)
        if (findSubsetSum(nums, remainingSum, index + 1)) {
            return true;
        }

        return false; // No subset found from this path
    }
    // Time: O(2^N) - Each element has two choices (include or exclude).
    // Space: O(N) for recursion stack.
}
```
Key to backtracking is clearly defining:
1.  What a "choice" is at each step.
2.  How to "make" the choice.
3.  How to "undo" (backtrack) the choice.
4.  What the "constraints" or "validity checks" are.
5.  What the "base cases" are (solution found, or no solution possible from current path).

---

## 11. Dynamic Programming (DP)

Dynamic Programming is an algorithmic technique for solving optimization problems by breaking them down into simpler overlapping subproblems and storing the results of these subproblems to avoid redundant computations. It's particularly useful when subproblems are solved multiple times.

**Core DP Concepts:**
1.  **Overlapping Subproblems:** A problem has overlapping subproblems if it can be broken down into subproblems that are reused multiple times.
    *   *Example:* In calculating `fib(5)`, `fib(3)` is calculated multiple times by the naive recursive approach. DP solves `fib(3)` once and stores its result.
2.  **Optimal Substructure:** A problem exhibits optimal substructure if an optimal solution to the problem can be constructed from optimal solutions to its subproblems.
    *   *Example:* The shortest path between two points in a graph contains shortest paths between intermediate points.

**Two Main Approaches to DP:**

**1. Memoization (Top-Down DP)**
*   **Concept:** This is a recursive approach where you solve the problem by breaking it down. Before computing a subproblem, you check if its solution has already been computed and stored (usually in a lookup table like an array or hash map, often called a "memo" or "cache").
*   **Algorithm:**
    1.  Write a recursive function to solve the problem.
    2.  In the recursive function, add a base case.
    3.  Before making recursive calls for a subproblem, check if the result for this subproblem is already in the memo table.
        *   If yes, return the stored result.
        *   If no, compute the result using recursive calls.
    4.  Store the computed result in the memo table before returning it.
*   **Pros:**
    *   Often more intuitive to write if you can define a clear recurrence relation.
    *   Only computes subproblems that are actually needed.
*   **Cons:**
    *   Recursion overhead (function calls, call stack).
    *   Can hit recursion depth limits for very deep problems (though less likely if subproblems are unique).

**2. Tabulation (Bottom-Up DP)**
*   **Concept:** This is an iterative approach where you solve subproblems in a specific order, typically starting from the smallest/simplest subproblems and building up to the solution for the original problem. Solutions to subproblems are stored in a table (e.g., 1D or 2D array).
*   **Algorithm:**
    1.  Identify the dimensions and size of the DP table needed to store solutions to all subproblems.
    2.  Initialize the base cases in the DP table.
    3.  Iterate through the DP table, filling in entries based on previously computed values (using the recurrence relation). The order of iteration is crucial to ensure dependencies are met.
    4.  The final solution is usually found in one of the last entries of the DP table.
*   **Pros:**
    *   No recursion overhead, avoids stack overflow issues.
    *   Can sometimes lead to further space optimizations (e.g., if only the previous row/column of the DP table is needed).
*   **Cons:**
    *   May compute all subproblems, even those not strictly necessary for the final solution (though often this is fine).
    *   Requires figuring out the correct order of iteration.

**Steps to Solve a DP Problem:**
1.  **Identify if it's a DP problem:** Look for overlapping subproblems and optimal substructure. Often involves finding a min/max value, counting ways, or checking feasibility under constraints.
2.  **Define the State:** What variables uniquely identify a subproblem? These will be the parameters of your recursive function (memoization) or the dimensions of your DP table (tabulation). `dp[i]` or `dp[i][j]` might represent the solution to the subproblem ending at `i` or involving states `i` and `j`.
3.  **Formulate the Recurrence Relation (Transition Function):** Express the solution to a state (subproblem) in terms of solutions to smaller/previous states.
4.  **Identify the Base Cases:** These are the smallest subproblems whose solutions are known directly.
5.  **Choose Approach (Memoization or Tabulation):** Implement the solution.
6.  **Optimize (Optional):** Consider space optimization if possible (e.g., if `dp[i]` only depends on `dp[i-1]` and `dp[i-2]`, you only need to store a few previous values).

### Basic DP Problems (1D DP)

Usually involve a 1D array `dp[]` where `dp[i]` stores the solution for the subproblem related to the `i`-th element or state.

```java
public class DynamicProgramming1D {

    // Fibonacci Sequence (Tabulation)
    // dp[i] stores the i-th Fibonacci number
    public int fibonacciTabulation(int n) {
        if (n < 0) throw new IllegalArgumentException("Input cannot be negative.");
        if (n <= 1) return n;

        int[] dp = new int[n + 1];
        // Base Cases
        dp[0] = 0;
        dp[1] = 1;

        // Iteratively fill the dp table
        for (int i = 2; i <= n; i++) {
            // Recurrence Relation: F(i) = F(i-1) + F(i-2)
            dp[i] = dp[i - 1] + dp[i - 2];
        }
        return dp[n];
    }
    // Time: O(n), Space: O(n) for dp array

    // Fibonacci Sequence (Space Optimized Tabulation)
    // Since F(i) only depends on F(i-1) and F(i-2), we only need to store two previous values.
    public int fibonacciSpaceOptimized(int n) {
        if (n < 0) throw new IllegalArgumentException("Input cannot be negative.");
        if (n <= 1) return n;

        int prev2 = 0; // Represents F(i-2)
        int prev1 = 1; // Represents F(i-1)
        int current = 0; // Represents F(i)

        for (int i = 2; i <= n; i++) {
            current = prev1 + prev2;
            prev2 = prev1;
            prev1 = current;
        }
        return prev1; // The last 'prev1' will be F(n)
    }
    // Time: O(n), Space: O(1)

    // Climbing Stairs
    // You are climbing a staircase. It takes n steps to reach the top.
    // Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?
    // dp[i] = number of ways to reach step i
    // Recurrence: dp[i] = dp[i-1] (from step i-1, take 1 step) + dp[i-2] (from step i-2, take 2 steps)
    public int climbStairs(int n) {
        if (n <= 0) return 0;
        if (n == 1) return 1;
        if (n == 2) return 2; // (1,1) or (2)

        // Using space optimization directly as it's similar to Fibonacci
        int oneStepBack = 2; // ways to reach step i-1 (dp[n-1])
        int twoStepsBack = 1; // ways to reach step i-2 (dp[n-2])
        int currentWays = 0;

        for (int i = 3; i <= n; i++) {
            currentWays = oneStepBack + twoStepsBack;
            twoStepsBack = oneStepBack;
            oneStepBack = currentWays;
        }
        return currentWays; // Or oneStepBack at the end
        // If using DP array:
        // int[] dp = new int[n + 1];
        // dp[1] = 1;
        // dp[2] = 2;
        // for (int i = 3; i <= n; i++) dp[i] = dp[i-1] + dp[i-2];
        // return dp[n];
    }
    // Time: O(n), Space: O(1) (optimized) or O(n) (with DP array)

    // House Robber
    // You are a professional robber planning to rob houses along a street. Each house has a certain
    // amount of money. You cannot rob two adjacent houses. Maximize the amount you can rob.
    // dp[i] = maximum money robbed up to house i.
    // Choice for house i:
    // 1. Rob house i: money[i] + dp[i-2] (cannot rob house i-1)
    // 2. Don't rob house i: dp[i-1]
    // dp[i] = Math.max(money[i] + dp[i-2], dp[i-1])
    public int rob(int[] nums) {
        if (nums == null || nums.length == 0) return 0;
        int n = nums.length;
        if (n == 1) return nums[0];

        // dp[i] will store the max money robbed considering houses up to index i
        int[] dp = new int[n];

        // Base cases
        dp[0] = nums[0];                            // Max money if only 1st house exists
        dp[1] = Math.max(nums[0], nums[1]);         // Max money if 1st or 2nd house exists

        for (int i = 2; i < n; i++) {
            // Max of:
            // 1. Robbing current house i (nums[i]) + max money from robbing up to house i-2 (dp[i-2])
            // 2. Not robbing current house i, so max money is same as robbing up to house i-1 (dp[i-1])
            dp[i] = Math.max(nums[i] + dp[i - 2], dp[i - 1]);
        }
        return dp[n - 1];
    }
    // Space Optimized Robber:
    public int robSpaceOptimized(int[] nums) {
        if (nums == null || nums.length == 0) return 0;
        int n = nums.length;
        if (n == 1) return nums[0];

        int robPrev2 = 0; // Corresponds to dp[i-2]
        int robPrev1 = 0; // Corresponds to dp[i-1]

        // Base cases for space optimized variables (think about dp[0] and dp[1])
        // If we iterate from the first house:
        // For nums[0]: robPrev1 = nums[0], robPrev2 = 0
        // For nums[1]: current = max(nums[1]+robPrev2, robPrev1)
        // Let's adjust:
        robPrev2 = 0;           // Max money if we rob up to "house before previous"
        robPrev1 = nums[0];    // Max money if we rob up to "previous house" (considering only house 0)

        // For the second house (index 1)
        if (n > 1) { // This check is actually handled by the loop structure
             int temp = Math.max(nums[1] + robPrev2, robPrev1); // robPrev2 is 0 here
             robPrev2 = robPrev1;
             robPrev1 = temp;
        } else {
            return robPrev1; // only one house
        }


        for (int i = 2; i < n; i++) {
            int currentRob = Math.max(nums[i] + robPrev2, robPrev1);
            robPrev2 = robPrev1;
            robPrev1 = currentRob;
        }
        return robPrev1;
    }
    // Time: O(n), Space: O(n) for dp array or O(1) for space-optimized version.

    // Maximum Subarray (Kadane's Algorithm) - Classic DP
    // Find the contiguous subarray within an array (containing at least one number)
    // which has the largest sum.
    // dp[i] = maximum sum of a subarray ending at index i.
    // Recurrence: dp[i] = Math.max(nums[i], nums[i] + dp[i-1])
    // The overall max is the max value in the dp array.
    public int maxSubArray(int[] nums) {
        if (nums == null || nums.length == 0) return 0; // Or throw exception
        int n = nums.length;

        int maxEndingHere = nums[0]; // Max sum of subarray ending at current position
        int maxSoFar = nums[0];      // Overall max sum found

        for (int i = 1; i < n; i++) {
            // For the current element nums[i], we can either:
            // 1. Start a new subarray with just nums[i].
            // 2. Extend the previous max-ending-here subarray by adding nums[i] to it.
            maxEndingHere = Math.max(nums[i], maxEndingHere + nums[i]);
            // Update the overall maximum sum found so far.
            maxSoFar = Math.max(maxSoFar, maxEndingHere);
        }
        return maxSoFar;
    }
    // Time: O(n), Space: O(1) (Kadane's optimizes space by only keeping track of current max ending here)
    // The `dp` array is implicit in `maxEndingHere`.
}
```

### 2D Dynamic Programming

Often involves a 2D array `dp[i][j]` where `dp[i][j]` stores the solution for a subproblem defined by states `i` and `j` (e.g., considering first `i` elements of one input and first `j` elements of another, or a grid cell `(i,j)`).

```java
public class DynamicProgramming2D {

    // Unique Paths - Grid DP
    // A robot is located at the top-left corner of a m x n grid.
    // The robot can only move either down or right at any point in time.
    // How many possible unique paths are there to reach the bottom-right corner?
    // dp[i][j] = number of unique paths to reach cell (i, j)
    // Recurrence: dp[i][j] = dp[i-1][j] (from cell above) + dp[i][j-1] (from cell to the left)
    public int uniquePaths(int m, int n) { // m rows, n columns
        if (m <= 0 || n <= 0) return 0;
        int[][] dp = new int[m][n];

        // Base Cases:
        // There's only 1 way to reach any cell in the first row (all right moves)
        for (int j = 0; j < n; j++) {
            dp[0][j] = 1;
        }
        // There's only 1 way to reach any cell in the first column (all down moves)
        for (int i = 0; i < m; i++) {
            dp[i][0] = 1;
        }

        // Fill the rest of the dp table
        for (int i = 1; i < m; i++) {
            for (int j = 1; j < n; j++) {
                dp[i][j] = dp[i - 1][j] + dp[i][j - 1];
            }
        }
        return dp[m - 1][n - 1]; // Result is at the bottom-right corner
    }
    // Time: O(m*n), Space: O(m*n)

    // Space Optimized Unique Paths
    // Since dp[i][j] only depends on dp[i-1][j] and dp[i][j-1],
    // we only need the previous row (or current row being built using previous row values)
    public int uniquePathsSpaceOptimized(int m, int n) {
        if (m <= 0 || n <= 0) return 0;
        // Let's use a 1D dp array representing a row (e.g., current row)
        // Ensure dp array is for the smaller dimension if optimizing further, but for simplicity:
        int[] dp = new int[n]; // dp[j] will store paths to cell (currentRow, j)

        // Initialize first row (all 1s)
        java.util.Arrays.fill(dp, 1);

        // Iterate for remaining rows (from row 1 up to m-1)
        for (int i = 1; i < m; i++) {
            // For each cell in the current row
            // dp[0] remains 1 (paths to first column)
            for (int j = 1; j < n; j++) {
                // dp[j] (new value for current row) = dp[j] (value from previous row, same col)
                //                                   + dp[j-1] (value from current row, prev col)
                dp[j] = dp[j] + dp[j - 1];
            }
        }
        return dp[n - 1]; // Result for the last cell of the last row
    }
    // Time: O(m*n), Space: O(n) (or O(min(m,n)))

    // Minimum Path Sum in a Grid
    // Given a m x n grid filled with non-negative numbers, find a path from top left
    // to bottom right, which minimizes the sum of all numbers along its path.
    // You can only move either down or right.
    // dp[i][j] = minimum sum to reach cell (i, j)
    // Recurrence: dp[i][j] = grid[i][j] + Math.min(dp[i-1][j], dp[i][j-1])
    public int minPathSum(int[][] grid) {
        if (grid == null || grid.length == 0 || grid[0].length == 0) return 0;
        int m = grid.length;
        int n = grid[0].length;
        int[][] dp = new int[m][n];

        // Base Case: Top-left cell
        dp[0][0] = grid[0][0];

        // Initialize first row (can only come from left)
        for (int j = 1; j < n; j++) {
            dp[0][j] = grid[0][j] + dp[0][j - 1];
        }
        // Initialize first column (can only come from top)
        for (int i = 1; i < m; i++) {
            dp[i][0] = grid[i][0] + dp[i - 1][0];
        }

        // Fill the rest of the dp table
        for (int i = 1; i < m; i++) {
            for (int j = 1; j < n; j++) {
                dp[i][j] = grid[i][j] + Math.min(dp[i - 1][j], dp[i][j - 1]);
            }
        }
        return dp[m - 1][n - 1];
    }
    // Time: O(m*n), Space: O(m*n). Can be space-optimized to O(n) or O(min(m,n)).

    // Longest Common Subsequence (LCS)
    // Given two strings text1 and text2, return the length of their longest common subsequence.
    // A subsequence is a sequence that can be derived from another sequence by deleting some
    // or no elements without changing the order of the remaining elements.
    // dp[i][j] = length of LCS of text1[0...i-1] and text2[0...j-1]
    // Recurrence:
    // If text1[i-1] == text2[j-1]:  dp[i][j] = 1 + dp[i-1][j-1]
    // Else:                         dp[i][j] = Math.max(dp[i-1][j], dp[i][j-1])
    public int longestCommonSubsequence(String text1, String text2) {
        if (text1 == null || text2 == null) return 0;
        int m = text1.length();
        int n = text2.length();
        int[][] dp = new int[m + 1][n + 1]; // +1 for empty string base cases

        // dp[i][j] will store LCS of text1.substring(0,i) and text2.substring(0,j)
        // Base cases: dp[0][j] = 0 and dp[i][0] = 0 (LCS with empty string is 0),
        // which is default for int array.

        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (text1.charAt(i - 1) == text2.charAt(j - 1)) {
                    // Characters match, so current char is part of LCS
                    dp[i][j] = 1 + dp[i - 1][j - 1];
                } else {
                    // Characters don't match, take max LCS from either
                    // excluding current char of text1 OR excluding current char of text2.
                    dp[i][j] = Math.max(dp[i - 1][j], dp[i][j - 1]);
                }
            }
        }
        return dp[m][n];
    }
    // Time: O(m*n), Space: O(m*n). Can be space-optimized to O(min(m,n)).

    // Edit Distance (Levenshtein Distance)
    // Given two strings word1 and word2, return the minimum number of operations
    // (insert, delete, or replace a character) required to convert word1 to word2.
    // dp[i][j] = min operations to convert word1[0...i-1] to word2[0...j-1]
    // Recurrence:
    // If word1[i-1] == word2[j-1]: dp[i][j] = dp[i-1][j-1] (no operation needed for current chars)
    // Else:
    //   dp[i][j] = 1 + Math.min(
    //                      dp[i-1][j],    // Delete char from word1
    //                      dp[i][j-1],    // Insert char into word1 (to match word2[j-1])
    //                      dp[i-1][j-1]   // Replace char in word1 with word2[j-1]
    //                  )
    public int minDistance(String word1, String word2) {
        if (word1 == null || word2 == null) return 0; // Or handle as error
        int m = word1.length();
        int n = word2.length();
        int[][] dp = new int[m + 1][n + 1];

        // Base Cases:
        // To convert empty string to word2[0...j-1], need j insertions.
        for (int j = 0; j <= n; j++) {
            dp[0][j] = j;
        }
        // To convert word1[0...i-1] to empty string, need i deletions.
        for (int i = 0; i <= m; i++) {
            dp[i][0] = i;
        }

        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (word1.charAt(i - 1) == word2.charAt(j - 1)) {
                    dp[i][j] = dp[i - 1][j - 1];
                } else {
                    int deleteOp = dp[i - 1][j];
                    int insertOp = dp[i][j - 1];
                    int replaceOp = dp[i - 1][j - 1];
                    dp[i][j] = 1 + Math.min(Math.min(deleteOp, insertOp), replaceOp);
                }
            }
        }
        return dp[m][n];
    }
    // Time: O(m*n), Space: O(m*n). Can be space-optimized to O(min(m,n)).
}
```

### Advanced DP Problems

These often involve more complex state definitions or transitions.

```java
public class AdvancedDynamicProgramming {

    // 0/1 Knapsack Problem
    // Given weights and values of n items, put these items in a knapsack of capacity W
    // to get the maximum total value. You cannot break an item (0/1 property).
    // dp[i][w] = maximum value that can be obtained using items from 1 to i with knapsack capacity w.
    // Recurrence for item i (with weight wt[i-1] and value val[i-1]):
    // If wt[i-1] <= w:
    //   dp[i][w] = Math.max(
    //                  val[i-1] + dp[i-1][w - wt[i-1]],  // Include item i
    //                  dp[i-1][w]                       // Exclude item i
    //              )
    // Else (item i is too heavy):
    //   dp[i][w] = dp[i-1][w]
    public int knapsack01(int[] weights, int[] values, int capacity) {
        int n = weights.length;
        if (n == 0 || capacity == 0) return 0;

        // dp[i][w] stores the max value using first i items with capacity w
        // Using 0-based indexing for items, so dp[i][w] uses items up to index i-1
        int[][] dp = new int[n + 1][capacity + 1];

        // Base cases: dp[0][w] = 0 (no items, no value)
        //             dp[i][0] = 0 (no capacity, no value)
        // These are usually handled by default 0-initialization of int array.

        for (int i = 1; i <= n; i++) { // Iterate through items
            // Current item's weight and value (using i-1 for 0-based array access)
            int currentWeight = weights[i - 1];
            int currentValue = values[i - 1];
            for (int w = 0; w <= capacity; w++) { // Iterate through capacities
                if (currentWeight <= w) {
                    // Option 1: Include current item
                    // Value = currentValue + max value from remaining capacity (w - currentWeight) using previous items (i-1)
                    int valueWithItem = currentValue + dp[i - 1][w - currentWeight];
                    // Option 2: Exclude current item
                    // Value = max value using previous items (i-1) with same capacity w
                    int valueWithoutItem = dp[i - 1][w];
                    dp[i][w] = Math.max(valueWithItem, valueWithoutItem);
                } else {
                    // Current item is too heavy, cannot include it
                    dp[i][w] = dp[i - 1][w];
                }
            }
        }
        return dp[n][capacity];
    }
    // Time: O(N*W) where N is number of items, W is capacity
    // Space: O(N*W)

    // Space Optimized 0/1 Knapsack (uses only 1D DP array)
    // Since dp[i][w] only depends on dp[i-1][...], we can optimize.
    // dp[w] = max value for capacity w.
    // Iterate items one by one. For each item, update dp table for all capacities.
    // Crucial: Iterate capacities from right to left (W down to item_weight) to use
    // values from the *previous* item's iteration (dp[w - item_weight] should refer to
    // the state before considering the current item for that smaller capacity).
    public int knapsack01SpaceOptimized(int[] weights, int[] values, int capacity) {
        int n = weights.length;
        if (n == 0 || capacity == 0) return 0;

        int[] dp = new int[capacity + 1]; // dp[w] stores max value for capacity w

        for (int i = 0; i < n; i++) { // For each item
            int currentWeight = weights[i];
            int currentValue = values[i];
            // Iterate capacities from right to left
            for (int w = capacity; w >= currentWeight; w--) {
                // dp[w] before this line is effectively dp_prev_item[w]
                // dp[w - currentWeight] is effectively dp_prev_item[w - currentWeight]
                dp[w] = Math.max(dp[w], currentValue + dp[w - currentWeight]);
            }
        }
        return dp[capacity];
    }
    // Time: O(N*W), Space: O(W)

    // Coin Change - Minimum Coins
    // Given an array of coin denominations and a total amount, find the minimum number
    // of coins needed to make up that amount. If not possible, return -1. Assume infinite coins of each type.
    // dp[i] = minimum coins to make amount i.
    // Recurrence: dp[i] = Math.min(dp[i], 1 + dp[i - coin_value]) for each coin.
    public int coinChange(int[] coins, int amount) {
        if (amount < 0) return -1;
        if (amount == 0) return 0;

        // dp[i] will store the minimum number of coins needed for amount i
        // Initialize with a value larger than any possible number of coins (e.g., amount + 1)
        int[] dp = new int[amount + 1];
        java.util.Arrays.fill(dp, amount + 1); // Sentinel value for "not possible"

        dp[0] = 0; // Base case: 0 coins needed to make amount 0

        for (int currentAmount = 1; currentAmount <= amount; currentAmount++) {
            for (int coin : coins) {
                if (coin <= currentAmount) {
                    // If we use this 'coin', we need 1 (for current coin) + dp[currentAmount - coin] coins
                    if (dp[currentAmount - coin] != amount + 1) { // Check if subproblem is solvable
                        dp[currentAmount] = Math.min(dp[currentAmount], 1 + dp[currentAmount - coin]);
                    }
                }
            }
        }
        // If dp[amount] is still amount + 1, it means it's not possible to make that amount.
        return dp[amount] > amount ? -1 : dp[amount];
    }
    // Time: O(Amount * NumCoins), Space: O(Amount)

    // Coin Change II - Number of Ways to Make Change
    // Given an array of coin denominations and a total amount, find the number of
    // distinct combinations of coins that make up that amount. Assume infinite coins.
    // dp[i] = number of ways to make amount i.
    // For each coin `c`: iterate amounts `j` from `c` to `target_amount`.
    // dp[j] = dp[j] (ways without using current coin `c`) + dp[j - c] (ways using current coin `c`)
    public int changeCombinations(int amount, int[] coins) {
        if (amount < 0) return 0;
        // dp[i] will store the number of ways to make up amount i
        int[] dp = new int[amount + 1];
        dp[0] = 1; // Base case: 1 way to make amount 0 (by choosing no coins)

        // Iterate through each coin type
        for (int coin : coins) {
            // For each amount from coin_value up to target_amount
            for (int currentAmount = coin; currentAmount <= amount; currentAmount++) {
                // Add the number of ways to make (currentAmount - coin) using previous coins
                // and the current coin to the existing ways to make currentAmount.
                dp[currentAmount] += dp[currentAmount - coin];
            }
        }
        return dp[amount];
    }
    // Time: O(Amount * NumCoins), Space: O(Amount)

    // Longest Increasing Subsequence (LIS)
    // Given an array of integers, find the length of the longest subsequence
    // such that all elements of the subsequence are sorted in increasing order.
    // dp[i] = length of the LIS ending at index i (and including nums[i]).
    // Recurrence: dp[i] = 1 + max(dp[j]) for all j < i where nums[j] < nums[i].
    // If no such j exists, dp[i] = 1.
    public int lengthOfLIS_N2(int[] nums) {
        if (nums == null || nums.length == 0) return 0;
        int n = nums.length;
        int[] dp = new int[n]; // dp[i] stores the length of LIS ending at nums[i]
        java.util.Arrays.fill(dp, 1); // Min LIS ending at any element is 1 (the element itself)

        int maxLength = 1;

        for (int i = 1; i < n; i++) {
            for (int j = 0; j < i; j++) {
                if (nums[i] > nums[j]) {
                    // If nums[i] can extend the LIS ending at nums[j]
                    dp[i] = Math.max(dp[i], 1 + dp[j]);
                }
            }
            maxLength = Math.max(maxLength, dp[i]); // Update overall max length
        }
        return maxLength;
    }
    // Time: O(N^2), Space: O(N)

    // LIS with Patience Sorting / Binary Search - O(N log N)
    // Maintain an array `tails` where `tails[i]` is the smallest tail of all
    // increasing subsequences of length `i+1`. This array is always sorted.
    // For each number `num` in `nums`:
    //   If `num` is greater than all tails, append it (extends the longest LIS found so far).
    //   Else, find the smallest tail `t` in `tails` such that `t >= num`. Replace `t` with `num`.
    //   This means we found a shorter path to an increasing subsequence of the same length,
    //   or we started a new increasing subsequence of a certain length with a smaller tail.
    // The length of `tails` array at the end is the length of LIS.
    public int lengthOfLIS_NLogN(int[] nums) {
        if (nums == null || nums.length == 0) return 0;

        // `tails[i]` is the smallest tail of all increasing subsequences of length `i+1`.
        // This list `tails` will always be sorted.
        List<Integer> tails = new ArrayList<>();

        for (int num : nums) {
            // Binary search to find the first element in `tails` >= `num`
            // Or, find the insertion point if `num` is larger than all elements in `tails`.
            int left = 0, right = tails.size(); // `right` is exclusive end
            while (left < right) {
                int mid = left + (right - left) / 2;
                if (tails.get(mid) < num) {
                    left = mid + 1; // `num` is larger, so `num` could extend sequence ending at `tails[mid]`
                } else {
                    right = mid; // `tails[mid]` >= `num`, so `num` could potentially replace `tails[mid]`
                }
            }

            // `left` is now the index where `num` should be inserted or replace an existing element.
            if (left == tails.size()) {
                // If `num` is greater than all elements in `tails`, it extends the LIS.
                tails.add(num);
            } else {
                // Otherwise, `num` replaces `tails[left]` because it allows us to achieve
                // an increasing subsequence of length `left+1` with a smaller tail element (`num`).
                tails.set(left, num);
            }
        }
        return tails.size(); // The size of `tails` is the length of LIS.
    }
    // Time: O(N log N) - N iterations, each involves a binary search (log N).
    // Space: O(N) in worst case for `tails` list (e.g., if array is sorted). Can be O(LIS_length).

    // Word Break
    // Given a string s and a dictionary of strings wordDict, return true if s can be
    // segmented into a space-separated sequence of one or more dictionary words.
    // dp[i] = true if s.substring(0, i) can be segmented.
    // Recurrence: dp[i] is true if there exists a j < i such that
    //             dp[j] is true AND s.substring(j, i) is in wordDict.
    public boolean wordBreak(String s, List<String> wordDict) {
        if (s == null || s.length() == 0) return true; // Or based on problem spec for empty string
        Set<String> dict = new HashSet<>(wordDict); // For O(1) average lookup

        // dp[i] is true if the prefix s[0...i-1] of length i can be segmented
        boolean[] dp = new boolean[s.length() + 1];
        dp[0] = true; // Base case: empty string can always be segmented

        for (int i = 1; i <= s.length(); i++) { // i is the length of the prefix being considered
            for (int j = 0; j < i; j++) { // j is the split point
                // If s[0...j-1] can be segmented (dp[j] is true)
                // AND s[j...i-1] (substring of length i-j starting at index j) is in the dictionary
                if (dp[j] && dict.contains(s.substring(j, i))) {
                    dp[i] = true; // Then s[0...i-1] can be segmented
                    break; // Found a way, no need to check other j for this i
                }
            }
        }
        return dp[s.length()];
    }
    // Time: O(N^2 * L) in worst case if substring takes O(L), where L is max word length.
    // If substring is O(1) (e.g. in Python slicing) or optimized, it can be closer to O(N^2).
    // String.substring in Java creates a new string, potentially O(L).
    // More precisely, outer loop N, inner loop N, substring L, set contains M (avg word length).
    // Can be O(N * M * L) or O(N^3) if L is N. With trie for dict, can optimize dict search.
    // Space: O(N) for dp array, O(DictSize * AvgWordLength) for set.
}
```

---

## 12. Greedy Algorithms

**Concept:**
Greedy algorithms make locally optimal choices at each step with the hope of finding a global optimum. At each decision point, they choose the option that looks best at the moment, without considering future consequences or backtracking.

Greedy algorithms don't always guarantee a globally optimal solution, but for certain problems, they do. The key is to prove that the greedy choice made at each step will lead to a global optimum (or is part of some optimal solution).

**General Structure:**
1.  Make a greedy choice.
2.  Reduce the problem to a smaller subproblem.
3.  Repeat until the problem is solved.

**When to Use Greedy Algorithms:**
*   Problems that exhibit the **Greedy Choice Property**: A global optimum can be arrived at by selecting a local optimum. This means the choice made at the current step doesn't prevent reaching the global optimum.
*   Problems that have the **Optimal Substructure Property**: An optimal solution to the problem contains optimal solutions to its subproblems (similar to DP, but the greedy choice is simpler).

**Proving Correctness of a Greedy Algorithm:**
This is often the hardest part. Common proof techniques:
1.  **Greedy Stays Ahead:** Show that after each step, the greedy solution is at least as good as any other partial solution.
2.  **Exchange Argument (Proof by Contradiction):** Assume there's an optimal solution that doesn't use the greedy choice at some step. Then show that you can replace some choice in this optimal solution with the greedy choice to get an equally good or better solution, thus contradicting the assumption or showing the greedy choice is part of an optimal solution.

**Examples:**

**1. Activity Selection Problem**
*   **Problem:** Given `n` activities with their start and finish times, select the maximum number of non-overlapping activities that can be performed by a single person.
*   **Greedy Choice:** Sort activities by their **finish times** in ascending order. Then, select the first activity. For subsequent activities, select the next activity in the sorted list whose start time is greater than or equal to the finish time of the previously selected activity.
*   **Why it works (Greedy Choice Property):** By picking the activity that finishes earliest, you leave the maximum possible time for other activities.

```java
import java.util.Arrays;
import java.util.Comparator;
import java.util.ArrayList;
import java.util.List;

public class GreedyAlgorithms {

    static class Activity {
        int start;
        int finish;
        int id; // Optional, for tracking

        Activity(int start, int finish, int id) {
            this.start = start;
            this.finish = finish;
            this.id = id;
        }

        @Override
        public String toString() {
            return "Activity(" + id + ": " + start + "-" + finish + ")";
        }
    }

    public List<Activity> activitySelection(Activity[] activities) {
        List<Activity> selectedActivities = new ArrayList<>();
        if (activities == null || activities.length == 0) {
            return selectedActivities;
        }

        // Sort activities based on their finish times in ascending order
        Arrays.sort(activities, Comparator.comparingInt(a -> a.finish));

        // The first activity is always selected
        selectedActivities.add(activities[0]);
        int lastFinishTime = activities[0].finish;

        // Iterate through the rest of the activities
        for (int i = 1; i < activities.length; i++) {
            // If the current activity's start time is after or same as the
            // finish time of the previously selected activity, then select it.
            if (activities[i].start >= lastFinishTime) {
                selectedActivities.add(activities[i]);
                lastFinishTime = activities[i].finish;
            }
        }
        return selectedActivities;
    }
    // Time: O(N log N) for sorting, O(N) for iteration. So, O(N log N).
    // Space: O(N) if considering output list, O(1) if modifying input or just counting.
}
```

**2. Fractional Knapsack Problem**
*   **Problem:** Given weights and values of `n` items, and a knapsack of capacity `W`. You can take fractions of items. Find the maximum total value that can be put into the knapsack.
*   **Greedy Choice:** Calculate the value-to-weight ratio (`value / weight`) for each item. Sort items by this ratio in descending order. Pick items with the highest ratio first. If an item doesn't fit entirely, take a fraction of it to fill the remaining capacity.
*   **Why it works:** By prioritizing items with the highest value per unit of weight, you maximize the value packed for any given amount of weight used.

```java
// (Continuing in GreedyAlgorithms class)
    static class Item {
        int weight;
        int value;
        double ratio; // value / weight
        int id;

        Item(int weight, int value, int id) {
            this.weight = weight;
            this.value = value;
            this.ratio = (double) value / weight;
            this.id = id;
        }
         @Override
        public String toString() {
            return "Item(" + id + ": w=" + weight + ", v=" + value + ", r=" + String.format("%.2f", ratio) + ")";
        }
    }

    public double fractionalKnapsack(Item[] items, int capacity) {
        if (items == null || items.length == 0 || capacity <= 0) {
            return 0.0;
        }

        // Sort items based on their value-to-weight ratio in descending order
        Arrays.sort(items, (a, b) -> Double.compare(b.ratio, a.ratio)); // Descending

        double totalValue = 0.0;
        int currentWeight = 0;

        System.out.println("Sorted items by ratio: " + Arrays.toString(items));


        for (Item item : items) {
            if (currentWeight + item.weight <= capacity) {
                // Take the whole item
                currentWeight += item.weight;
                totalValue += item.value;
                System.out.println("Took whole " + item);
            } else {
                // Take a fraction of the item to fill the remaining capacity
                int remainingCapacity = capacity - currentWeight;
                double fraction = (double) remainingCapacity / item.weight;
                totalValue += item.value * fraction;
                currentWeight += remainingCapacity; // Knapsack is now full
                System.out.println("Took fraction " + String.format("%.2f", fraction) + " of " + item);
                break; // Knapsack is full
            }
        }
        return totalValue;
    }
    // Time: O(N log N) for sorting, O(N) for iteration. So, O(N log N).
    // Space: O(1) (if sorting in-place or not counting input array as extra).
```

**3. Huffman Coding (Conceptual)**
*   **Problem:** Data compression. Assign variable-length codes to input characters, lengths of the codes based on the frequencies of corresponding characters. More frequent characters get shorter codes.
*   **Greedy Choice:** Create a binary tree (Huffman Tree). Start with each character as a leaf node with its frequency as weight. Repeatedly merge the two nodes with the smallest frequencies to create a new internal node whose frequency is the sum of its children's frequencies. Continue until only one node (the root) remains.
    *   Edges to left children can be assigned '0', right children '1'. The path from root to a leaf (character) gives its Huffman code.
*   This is a prefix code (no code is a prefix of another), ensuring unambiguous decoding.

**Dijkstra's Algorithm and Prim's Algorithm (for MSTs)** are also examples of greedy algorithms.

**Difference between Greedy and DP:**
*   **Choice:** Greedy makes one choice at each step (the "best" at that moment) and never reconsiders. DP explores multiple choices/options at each step and finds the best one among them (often by solving all relevant subproblems).
*   **Subproblems:** In greedy, the choice reduces the problem to one subproblem. In DP, the solution to a subproblem might depend on solutions to multiple smaller subproblems.
*   **Proof of Correctness:** Generally harder for greedy algorithms. For DP, if optimal substructure and overlapping subproblems exist, it usually works.

---

## 13. Advanced Topics (Continued)

### Union-Find (Disjoint Set Union - DSU)

**Conceptual Explanation:**
A data structure that keeps track of a set of elements partitioned into a number of disjoint (non-overlapping) subsets. It provides two main operations:
1.  **`find(i)`:** Determine which subset element `i` belongs to. This typically returns a representative (or parent) of the set.
2.  **`union(i, j)`:** Merge the two subsets to which elements `i` and `j` belong. If they are already in the same set, do nothing.

**Representation:**
*   Often implemented using an array `parent[]`, where `parent[i]` stores the parent of element `i`.
*   If `parent[i] == i`, then `i` is the representative (root) of its set.

**Optimizations to Improve Performance:**
1.  **Path Compression:** During a `find(i)` operation, after finding the root `r` of `i`'s set, make all nodes on the path from `i` to `r` point directly to `r`. This flattens the tree structure, speeding up future `find` operations for these elements.
2.  **Union by Rank (or Union by Size):** When merging two sets, make the root of the shorter/smaller tree point to the root of the taller/larger tree.
    *   **Union by Rank:** Keep track of the "rank" (an upper bound on the height) of each tree. Attach the tree with smaller rank to the root of the tree with larger rank. If ranks are equal, pick one as parent and increment its rank.
    *   **Union by Size:** Keep track of the size (number of elements) of each set. Attach the tree with smaller size to the root of the tree with larger size.
*   These optimizations make the amortized time complexity per operation nearly constant, O(α(n)), where α(n) is the inverse Ackermann function, which is very slow growing (effectively ≤ 5 for all practical values of n).

**Applications:**
*   Kruskal's algorithm for Minimum Spanning Tree (to detect cycles).
*   Detecting cycles in an undirected graph.
*   Finding connected components in a graph.
*   Problems involving partitioning or equivalence classes.

```java
// Union-Find with Path Compression and Union by Rank/Size
class UnionFind {
    private int[] parent; // parent[i] = parent of element i
    private int[] rank;   // rank[i] = rank of the set whose root is i (used for union by rank)
    // private int[] size; // Alternatively, use size[i] = size of set whose root is i (for union by size)
    private int numComponents; // Number of disjoint sets

    public UnionFind(int n) {
        if (n <= 0) throw new IllegalArgumentException("Number of elements must be positive.");
        parent = new int[n];
        rank = new int[n];
        // size = new int[n];
        numComponents = n; // Initially, each element is in its own set

        for (int i = 0; i < n; i++) {
            parent[i] = i;    // Each element is its own parent initially
            rank[i] = 0;      // Initial rank is 0
            // size[i] = 1;    // Initial size is 1
        }
    }

    // Find operation with path compression
    public int find(int i) {
        if (i < 0 || i >= parent.length) throw new IndexOutOfBoundsException("Element out of bounds.");

        // If parent[i] is not i, it means i is not the root of its set.
        // Recursively find the root and apply path compression.
        if (parent[i] != i) {
            parent[i] = find(parent[i]); // Path compression: make i point directly to the root
        }
        return parent[i]; // Return the root of the set
    }

    // Union operation (using union by rank)
    // Returns true if sets were different and merged, false if already in same set.
    public boolean union(int i, int j) {
        if (i < 0 || i >= parent.length || j < 0 || j >= parent.length) {
            throw new IndexOutOfBoundsException("Element out of bounds.");
        }

        int rootI = find(i); // Find root of set containing i
        int rootJ = find(j); // Find root of set containing j

        if (rootI != rootJ) { // If they are in different sets, merge them
            // Union by rank: attach smaller rank tree under root of higher rank tree
            if (rank[rootI] < rank[rootJ]) {
                parent[rootI] = rootJ;
            } else if (rank[rootJ] < rank[rootI]) {
                parent[rootJ] = rootI;
            } else {
                // If ranks are same, make one root of the other and increment rank
                parent[rootJ] = rootI;
                rank[rootI]++;
            }
            numComponents--; // One component merged into another
            return true;
        }
        return false; // Already in the same set
    }

    /*
    // Union operation (using union by size) - Alternative to union by rank
    public boolean unionBySize(int i, int j) {
        int rootI = find(i);
        int rootJ = find(j);

        if (rootI != rootJ) {
            // Attach smaller size tree under root of larger size tree
            if (size[rootI] < size[rootJ]) {
                parent[rootI] = rootJ;
                size[rootJ] += size[rootI];
            } else {
                parent[rootJ] = rootI;
                size[rootI] += size[rootJ];
            }
            numComponents--;
            return true;
        }
        return false;
    }
    */

    // Check if two elements are in the same set
    public boolean connected(int i, int j) {
        return find(i) == find(j);
    }

    // Get the number of disjoint sets/components
    public int getNumComponents() {
        return numComponents;
    }

    // Get the size of the set containing element i (if using union by size)
    /*
    public int getSetSize(int i) {
        if (i < 0 || i >= parent.length) throw new IndexOutOfBoundsException("Element out of bounds.");
        return size[find(i)];
    }
    */
}

// Applications of Union-Find (Example: Number of Islands)
// Problem: Given a 2D grid map of '1's (land) and '0's (water), count the number of islands.
// An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically.
public class NumberOfIslandsUF {
    public int numIslands(char[][] grid) {
        if (grid == null || grid.length == 0 || grid[0].length == 0) {
            return 0;
        }

        int rows = grid.length;
        int cols = grid[0].length;
        UnionFind uf = new UnionFind(rows * cols); // Each cell is an element

        int initialIslands = 0; // Could track this, or use uf.getNumComponents() carefully

        for (int r = 0; r < rows; r++) {
            for (int c = 0; c < cols; c++) {
                if (grid[r][c] == '1') {
                    initialIslands++; // Count each land cell initially as a separate island
                    int cell1DIndex = r * cols + c;

                    // Check right neighbor
                    if (c + 1 < cols && grid[r][c + 1] == '1') {
                        int neighborIndex = r * cols + (c + 1);
                        if(uf.union(cell1DIndex, neighborIndex)){
                            initialIslands--; // If union happened, reduce island count
                        }
                    }
                    // Check bottom neighbor
                    if (r + 1 < rows && grid[r + 1][c] == '1') {
                        int neighborIndex = (r + 1) * cols + c;
                         if(uf.union(cell1DIndex, neighborIndex)){
                            initialIslands--;
                        }
                    }
                    // No need to check left/top as they would have been processed
                }
            }
        }
         // The above logic has a slight issue. A simpler way is to initialize numComponents
         // in UF only for '1's or adjust the count correctly.
         // Let's use the numComponents property from a refined UF for '1's only.

        // Corrected approach using UF for numIslands:
        int count = 0;
        for(int r=0; r<rows; ++r) for(int c=0; c<cols; ++c) if(grid[r][c] == '1') count++;

        UnionFind ufCorrected = new UnionFind(rows * cols); // Still map all cells
        // We need to adjust the component count in UF initially or at the end.
        // Or, more directly:
        // Initialize UF with 0 components.
        // When a '1' is found, increment component count, then try to union.
        // If union happens, decrement component count.

        // Alternative: Use UF's internal component count.
        // For this, we'd need to know which of the N elements in UF are "active" (are '1's).
        // The provided UF starts with N components.
        // Let's use the initialIslands and decrement logic carefully.

        // The issue with `initialIslands--` inside `uf.union` is that `uf.union`
        // itself adjusts `numComponents`.
        // A better way for this problem:
        // Initialize UF with rows*cols elements.
        // Iterate, and if grid[r][c] is '1', consider it.
        // Then iterate again, if grid[r][c] is '1', and its neighbor is '1', union them.
        // The number of components in UF corresponding to '1's would be the answer.
        // The provided code in the prompt for `numIslands` was more of an illustration.
        // The final number of components in UF, if only '1' cells were considered as actual
        // elements from the start, would be the answer.
        // For the current UF that takes N total elements:
        // We can count '1's. For each '1', its component is initially distinct.
        // Then union. The final `uf.getNumComponents()` needs to be adjusted for the '0' cells
        // that are also part of the UF structure but don't form islands.

        // More standard way to count islands using UF:
        // 1. Iterate through grid. If grid[r][c] == '1', this is potentially a new island.
        // 2. If it's a '1', connect it (union) with any adjacent '1's (left and top, as right and bottom will be processed later).
        // 3. The number of distinct sets (roots) among the '1' cells is the number of islands.
        // This requires filtering `uf.getNumComponents()` or a more tailored UF.

        // Let's use the `initialIslands` decrement logic from the user's provided example,
        // assuming `uf.union` only reflects if a merge happened:
        int actualIslandCount = 0;
        for (int r = 0; r < rows; r++) {
            for (int c = 0; c < cols; c++) {
                if (grid[r][c] == '1') {
                    actualIslandCount++; // Tentatively count it
                }
            }
        }
        // Now perform unions, and decrement if a *true* merge of distinct islands happens.
        // The UF's internal numComponents will also track this if initialized correctly.
        // Let's assume the UnionFind `numComponents` is the primary tracker.
        // We must initialize it so that initially only land cells are components.

        // Re-thinking for standard UF usage where UF has rows*cols elements:
        UnionFind islandUf = new UnionFind(rows * cols);
        int zeroCellCount = 0;

        for (int r = 0; r < rows; r++) {
            for (int c = 0; c < cols; c++) {
                if (grid[r][c] == '0') {
                    zeroCellCount++; // We'll subtract these non-island components later
                } else { // It's a '1'
                    int cell1DIndex = r * cols + c;
                    // Check and union with right neighbor if it's also land
                    if (c + 1 < cols && grid[r][c + 1] == '1') {
                        islandUf.union(cell1DIndex, r * cols + (c + 1));
                    }
                    // Check and union with bottom neighbor if it's also land
                    if (r + 1 < rows && grid[r + 1][c] == '1') {
                        islandUf.union(cell1DIndex, (r + 1) * cols + c);
                    }
                }
            }
        }
        // Total components from UF - components that are just '0' cells.
        // Each '0' cell initially forms its own component in the UF if not unioned.
        // This is tricky. The standard way is to count distinct roots of '1' cells.
        // Or:
        // Initialize `num_islands = 0`.
        // Iterate `grid[r][c]`. If '1' and not visited (or not part of an existing UF set for an island):
        //   `num_islands++`. Perform DFS/BFS from `(r,c)` to find all parts of this island,
        //   unioning them in UF.
        // The UF in the prompt was likely simplified.
        // The version in the original prompt for `accountsMerge` is more typical for UF application.

        // The key is `uf.getNumComponents()` will be (num_water_components + num_land_islands).
        // If all water cells are treated as one component (or ignored from count), then it's simpler.
        // The prompt's `numIslands` in advanced topics was a bit of a mix.
        // For `WordSearchII` and `AccountsMerge`, the UF usage is more direct.
        // The `numIslands` solution using UF as shown in the prompt example is more about connecting
        // '1's and seeing how many `initialIslands` count reduces.
        // It assumes `uf.union` returns true if a *meaningful* merge happened, reducing distinct island count.
        return initialIslands; // Based on the logic structure provided in the user's prompt
    }
}
```

### Bit Manipulation (Overview)

**Concept:**
Bit manipulation involves performing operations directly on the binary representations of numbers. This can lead to highly efficient solutions for certain problems.

**Common Bitwise Operators (Java):**
*   **AND (`&`):** `1 & 1 = 1`, `1 & 0 = 0`, `0 & 1 = 0`, `0 & 0 = 0`.
    *   Used for: Checking if a bit is set (`num & (1 << k)`), clearing bits (`num & ~(1 << k)`), masking.
*   **OR (`|`):** `1 | 1 = 1`, `1 | 0 = 1`, `0 | 1 = 1`, `0 | 0 = 0`.
    *   Used for: Setting a bit (`num | (1 << k)`).
*   **XOR (`^`):** `1 ^ 1 = 0`, `1 ^ 0 = 1`, `0 ^ 1 = 1`, `0 ^ 0 = 0`.
    *   Properties: `x ^ x = 0`, `x ^ 0 = x`. `x ^ y = y ^ x`. Associative.
    *   Used for: Swapping two numbers without a temp variable (`a^=b; b^=a; a^=b;`), finding the single non-repeated element in an array where others repeat twice, checking if two numbers are different.
*   **NOT (`~`) (Bitwise Complement):** Flips all bits (`~0101 = 1010`).
*   **Left Shift (`<<`):** `num << k` shifts bits of `num` left by `k` positions, filling with zeros on the right. Equivalent to `num * 2^k`.
*   **Right Shift (`>>`) (Arithmetic/Signed):** `num >> k` shifts bits right by `k` positions. For positive numbers, fills with zeros on the left. For negative numbers, fills with the sign bit (1) on the left to preserve sign.
*   **Unsigned Right Shift (`>>>`):** `num >>> k` shifts bits right by `k` positions, always filling with zeros on the left, regardless of sign.

**Common Bit Manipulation Techniques:**
*   **Get `k`-th bit:** `(num >> k) & 1` (0-indexed from right)
*   **Set `k`-th bit:** `num | (1 << k)`
*   **Clear `k`-th bit:** `num & ~(1 << k)`
*   **Toggle `k`-th bit:** `num ^ (1 << k)`
*   **Check if a number is a power of 2:** `(num > 0) && (num & (num - 1)) == 0`
    *   A power of 2 has only one bit set (e.g., 0100). `num-1` will have all bits to its right set (e.g., 0011). ANDing them gives 0.
*   **Count set bits (Hamming Weight):**
    *   Loop and check each bit: `count += (num >> i) & 1;`
    *   Brian Kernighan's Algorithm: `while (num > 0) { num &= (num - 1); count++; }` (clears the rightmost set bit in each step).
    *   Java: `Integer.bitCount(num)`.
*   **Find the rightmost set bit:** `num & -num` (or `num & (~num + 1)` due to two's complement). This isolates the lowest set bit.
*   **Clear rightmost set bit:** `num & (num - 1)`
*   **Swap two numbers:** `a = a ^ b; b = a ^ b; a = a ^ b;`

**Applications:**
*   Optimizing performance in low-level programming or specific algorithms.
*   Representing sets or states efficiently (e.g., using a bitmask for subsets in DP).
*   Cryptography and data compression.
*   Solving problems related to binary properties of numbers.

**Example: Single Number**
Given a non-empty array of integers where every element appears twice except for one, find that single one.
```java
public class BitManipulationExamples {
    public int singleNumber(int[] nums) {
        int single = 0;
        for (int num : nums) {
            single ^= num; // XORing all elements. Duplicates cancel out (x ^ x = 0).
        }
        return single; // The remaining value is the single number.
    }
    // Time: O(N), Space: O(1)
}
```

---



# Interview Preparation Strategies

## Problem-Solving Framework

When approaching coding interview problems, follow this systematic framework to increase your success rate and demonstrate clear thinking to interviewers.

### Step 1: Understand the Problem

*   Read the problem statement carefully.
*   Ask clarifying questions about:
    *   Edge cases (empty inputs, null values, duplicates, constraints on numbers like positive/negative).
    *   Input/output format (data types, expected structure).
    *   Constraints on input size (helps determine feasible time/space complexity).
    *   Assumptions (e.g., are elements unique? is the array sorted?).
*   Work through examples manually:
    *   Use the examples provided in the problem.
    *   Create your own small, simple examples.
    *   Consider edge case examples. This helps solidify understanding and can reveal ambiguities.

### Step 2: Design the Approach

*   **Start with a Brute-Force Solution (if appropriate):**
    *   Think about the most straightforward way to solve the problem, even if it's inefficient.
    *   This demonstrates you can solve the problem and provides a baseline.
    *   Verbally communicate this to the interviewer.
*   **Identify Optimization Opportunities:**
    *   Look for redundant computations or inefficiencies in the brute-force approach.
    *   Consider if sorting the input helps.
    *   Can a different data structure improve performance (e.g., using a HashMap for O(1) lookups)?
*   **Consider Relevant Data Structures and Algorithms:**
    *   Map the problem to known DSA patterns (see "Common Patterns" below).
    *   Think about trade-offs (e.g., hash map for speed vs. space).
*   **Think About Time and Space Complexity Trade-offs:**
    *   Discuss the Big O complexity of your proposed approach(es).
    *   Sometimes a solution with higher time complexity but lower space complexity (or vice-versa) might be acceptable or even preferred, depending on constraints.

### Step 3: Code the Solution

*   **Write Clean, Readable Code:**
    *   Use meaningful variable and function names.
    *   Indent properly and maintain a consistent style.
    *   Break down complex logic into smaller helper functions if it improves clarity.
*   **Add Comments for Complex Logic (Sparingly):**
    *   Code should ideally be self-documenting.
    *   Add comments only for non-obvious parts or to explain your high-level approach for a section.
*   **Handle Edge Cases Explicitly:**
    *   Address the edge cases you identified in Step 1.
*   **Test with Provided Examples (and your own):**
    *   Mentally walk through your code with examples.
    *   If in a collaborative editor, you might be able to run it.

### Step 4: Analyze and Optimize

*   **Calculate Time and Space Complexity:**
    *   Be prepared to justify your analysis for the implemented solution.
*   **Discuss Potential Optimizations:**
    *   Even if your current solution is good, mention if there are more advanced or alternative ways to optimize further, perhaps with different trade-offs.
    *   This shows depth of knowledge.
*   **Consider Alternative Approaches:**
    *   Briefly mention other ways the problem could have been solved and why you chose your particular approach.
*   **Be Prepared to Modify Your Solution:**
    *   Interviewers might ask follow-up questions or introduce new constraints that require you to adapt your code.

## Common Patterns and When to Use Them

Understanding these patterns will help you quickly identify the right approach for different types of problems:

*   **Two Pointers Pattern**
    *   **Use for:** Array/string problems, often with sorted data, palindrome checks, finding pairs that sum to a target, problems involving finding a subsequence or subarray meeting certain criteria by moving pointers from ends or in the same direction.
    *   **Example problems:** Two Sum (sorted array), Container with Most Water, Valid Palindrome, Remove Duplicates from Sorted Array, Sort Colors.

*   **Sliding Window Pattern**
    *   **Use for:** Substring/subarray problems that involve finding a segment (window) that satisfies certain conditions (e.g., max/min sum, longest/shortest window, specific character counts). The window can be fixed or variable size.
    *   **Example problems:** Longest Substring Without Repeating Characters, Minimum Window Substring, Maximum Sum Subarray of Size K, Fruit Into Baskets.

*   **Fast and Slow Pointers (Floyd's Tortoise and Hare)**
    *   **Use for:** Cycle detection in linked lists or arrays, finding the middle element of a linked list, problems where one element needs to "catch up" to another or where relative speeds matter.
    *   **Example problems:** Linked List Cycle, Middle of Linked List, Happy Number, Palindrome Linked List.

*   **Merge Intervals Pattern**
    *   **Use for:** Problems involving overlapping intervals, scheduling, or geometric problems on a line. Typically involves sorting intervals by start or end times.
    *   **Example problems:** Merge Intervals, Insert Interval, Meeting Rooms I & II, Non-overlapping Intervals.

*   **Cyclic Sort Pattern**
    *   **Use for:** Problems with arrays containing numbers in a specific range (e.g., 1 to N). The idea is to place each number at its correct index.
    *   **Example problems:** Find Missing Number, Find All Missing Numbers, Find Duplicate Number, Find the Corrupt Pair, First Missing Positive.

*   **Tree DFS (Depth-First Search) Pattern**
    *   **Use for:** Tree traversal problems (preorder, inorder, postorder), pathfinding problems (e.g., path sum, diameter), problems requiring exploration of all nodes down a branch before backtracking.
    *   **Example problems:** Path Sum (I, II, III), Binary Tree Maximum Path Sum, Diameter of Binary Tree, Validate Binary Search Tree, Lowest Common Ancestor.

*   **Tree BFS (Breadth-First Search) Pattern**
    *   **Use for:** Level-order traversal of trees, finding the minimum depth or shortest path in terms of levels, problems where you need to explore nearest neighbors first.
    *   **Example problems:** Binary Tree Level Order Traversal, Minimum Depth of Binary Tree, Binary Tree Zigzag Level Order Traversal, Connect Level Order Siblings.

*   **Dynamic Programming Patterns**
    *   **Linear DP (1D):** Problems where the state `dp[i]` depends on previous states (e.g., `dp[i-1]`, `dp[i-2]`). Optimal substructure in one dimension.
        *   *Examples:* Fibonacci, Climbing Stairs, House Robber, Maximum Subarray (Kadane's).
    *   **Grid DP (2D):** 2D problems where `dp[i][j]` depends on `dp[i-1][j]`, `dp[i][j-1]`, or `dp[i-1][j-1]`.
        *   *Examples:* Unique Paths, Minimum Path Sum, Maximal Square.
    *   **Subsequence DP:** Problems involving finding optimal properties of subsequences of one or two strings/arrays.
        *   *Examples:* Longest Common Subsequence, Longest Increasing Subsequence, Edit Distance.
    *   **Knapsack DP:** Resource allocation problems where you need to choose items to maximize value/minimize cost under a capacity constraint (0/1 Knapsack, Unbounded Knapsack, Fractional Knapsack - though fractional is greedy).
        *   *Examples:* 0/1 Knapsack, Coin Change (min coins, number of ways).

## Time Management During Interviews

**(Typical 45-Minute Interview Breakdown)**

*   **Problem Understanding and Clarification:** `5-7 minutes`
    *   Listen actively, ask questions, confirm understanding.
*   **Solution Design and Approach Discussion:** `8-10 minutes`
    *   Whiteboard/verbally outline brute-force, then optimal approach. Discuss DSA choices and complexity.
*   **Coding Implementation:** `20-25 minutes`
    *   Focus on clean, correct code for the agreed-upon approach. Communicate while coding if helpful.
*   **Testing and Optimization Discussion:** `5-8 minutes`
    *   Test with examples. Discuss complexity and further optimizations if time allows or prompted.
*   **Questions for the Interviewer:** `2-3 minutes`
    *   Always have a couple of thoughtful questions ready.

### Tips for Efficient Coding:

*   **Practice typing code quickly and accurately.**
*   **Use IDE shortcuts and code snippets when allowed** (more for practice; in interviews, often a basic editor).
*   **Start with the main logic, then add edge case handling** (or handle critical ones upfront).
*   **Don't optimize prematurely** - get a working solution first, then discuss optimizations. Correctness is paramount.

## Final Preparation Checklist

### Technical Preparation:

*   **Master fundamental data structures** (Arrays, Strings, Linked Lists, Stacks, Queues, Trees, Heaps, Graphs, Hash Tables/Maps) and their operations.
*   **Understand time/space complexity analysis (Big O Notation)** for common operations and algorithms.
*   **Practice 150-200 coding problems** (e.g., from LeetCode, HackerRank) across different patterns and difficulty levels. Focus on quality over quantity initially.
*   **Review system design basics** for senior positions (scalability, reliability, common components like load balancers, databases, caches).
*   **Practice explaining solutions clearly and concisely**, as if teaching someone else. This includes your thought process.

### Behavioral Preparation:

*   **Prepare STAR format stories** (Situation, Task, Action, Result) for common behavioral questions (e.g., teamwork, conflict, failure, leadership, strengths, weaknesses).
*   **Practice explaining technical concepts to non-technical audiences** (if applicable to the role or for general communication skills).
*   **Prepare thoughtful questions about the role, team, and company culture.**
*   **Research the company's technical stack, products, and recent developments.**

### Day-of-Interview:

*   **Get good sleep** and arrive early (for in-person) or log in early (for virtual interviews).
*   **Bring/have ready:** Pen, paper (for an in-person whiteboard or personal notes), water. For virtual: ensure a stable internet connection.
*   **Test your setup** (camera, microphone, screen sharing, collaborative editor links) beforehand for virtual interviews.
*   **Stay calm, think out loud.** Interviewers want to see your thought process, not just the final answer.
*   **Don't be afraid to ask for hints** if you're truly stuck, after you've shown your attempts.

---


