# ADT Bag on Singly Linked List (SLL)

In this project, I implemented the interface of a Bag using a Singly Linked List and tested each feature to demonstrate its correctness and robustness.

## Node Structure

The `Node` structure is used to represent elements in the Bag. Each node contains:

- **element**: The value of the element stored in the node.
- **frequency**: The frequency of the element.
- **next**: A pointer to the next node in the list.
- 
## Bag Attributes

- **head**: A pointer to the first node in the linked list, representing the start of the Bag.
- **length**: An integer representing the number of elements in the Bag, including their frequencies.

## Operations

a few operations of the interface are briefly covered and explained, along with their complexity:

### Add
- **Description**: Adds an element to the Bag. If the element already exists, its frequency is increased. If the element does not exist, a new node is created and added to the front of the list.
- **Best Case Complexity**: Θ(1) (element found at the first position)
- **Worst Case Complexity**: Θ(n) (element not found; must traverse the whole linked list)
- **Total Complexity**: O(n)

### Remove
- **Description**: Removes an element from the Bag if it exists. If the element's frequency is greater than 1, it is decremented. If the frequency is 1, the node is removed from the list. 
- **Best Case Complexity**: Θ(1) (element is the head node)
- **Worst Case Complexity**: Θ(n) (element is not found; must traverse the whole linked list)
- **Total Complexity**: O(n)

### Search
- **Description**: Searches for an element in the Bag. Returns true if the element is found; otherwise, returns false.
- **Best Case Complexity**: Θ(1) (element found at the first position)
- **Worst Case Complexity**: Θ(n) (element not found; must traverse the whole linked list)
- **Total Complexity**: O(n)

### Number of Occurrences: `nrOccurrences(TElem elem) const`
- **Description**: Returns the number of occurrences of a specific element in the Bag. If the element is not found, returns 0.
- **Best Case Complexity**: Θ(1) (element found at the first position)
- **Worst Case Complexity**: Θ(n) (element not found; must traverse the whole linked list)
- **Total Complexity**: O(n)

## Iterator

To iterate over the Bag, a current element is initialized with the head and a current frequency is set to 1. The current element will have its frequency increased as many times as it appears and will go to the next element when that is no longer the case until the next element is actually `nullptr`.

## Tests

The tests are composed of short and extended scenarios designed to target the main aspects and edge cases. The results of the tests are visible as soon as the program finishes its execution.

![image](https://github.com/user-attachments/assets/4bd30b57-e94f-4abf-906b-7b5de5da1b73)
