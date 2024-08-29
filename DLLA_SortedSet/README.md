# Sorted Set on DLLA

In this project, I implemented the interface of a Sorted Set using a Doubly Linked List Array (DLLA) and tested each feature to demonstrate its correctness and robustness.

## Node Structure

The `DLLANode` structure is used to represent elements in the Sorted Set. Each node contains:

- **prev**: The index of the previous node in the array.
- **element**: The value of the element stored in the node.
- **next**: The index of the next node in the array.

## Sorted Set Attributes

- **nodes**: An array of `DLLANode` objects representing the nodes in the sorted set.
- **head**: An integer representing the index of the first node in the sorted set.
- **tail**: An integer representing the index of the last node in the sorted set.
- **firstEmpty**: An integer representing the index of the first available (empty) node.
- **cap**: An integer representing the current capacity of the `nodes` array.
- **length**: An integer representing the number of elements in the sorted set.
- **relation**: A function pointer used to define the order of elements in the sorted set.

## Operations

A few operations of the interface are briefly covered and explained, along with their complexity:

### Add
- **Description**: Adds an element to the Sorted Set. If the element already exists, the operation returns false. Otherwise, the element is inserted in its correct sorted position. If the `nodes` array is full, its capacity is doubled.
- **Best Case Complexity**: Θ(1) (element added in constant time if the list is empty or element is added at the beginning).
- **Worst Case Complexity**: Θ(n) (element needs to be inserted in a position towards the end or if the array needs resizing).
- **Total Complexity**: O(n)

### Remove
- **Description**: Removes an element from the Sorted Set if it exists. If the element is found, it is removed and the space is reclaimed.
- **Best Case Complexity**: Θ(1) (element is at the head and can be removed immediately).
- **Worst Case Complexity**: Θ(n) (element needs to be searched and removed, which may involve traversing the list).
- **Total Complexity**: O(n)

### Search
- **Description**: Searches for an element in the Sorted Set. Returns true if the element is found; otherwise, returns false.
- **Best Case Complexity**: Θ(1) (element is found at the head).
- **Worst Case Complexity**: Θ(n) (element is not found; must traverse the entire list).
- **Total Complexity**: O(n)

## Iterator

To iterate over the `SortedSet`, the iterator starts at the head of the list. It moves through the list from one element to the next. The iterator simply advances to the next element until it reaches the end of the list (when the next element is `nullptr` or `-1`).


## Tests

The tests cover various scenarios, including:
- Adding elements to the Sorted Set and verifying the correct order.
- Removing elements and ensuring the correct re-linking of nodes.
- Searching for elements to confirm that the search functionality works as expected.
- Checking the size and emptiness of the set under different conditions.

The results of the tests are visible as soon as the program finishes its execution.

![pp](https://github.com/user-attachments/assets/c3bff4af-cecf-4d8f-8712-73d1ba3a644b)

