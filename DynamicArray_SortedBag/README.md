# ADT Sorted Bag on Dynamic Array with Relation

In this project, I implemented the interface of a Sorted Bag using a Dynamic Array and tested each feature to demonstrate its correctness and robustness.

## Sorted Bag Attributes

- **e**: A pointer to the `TElem` structure, which ensures flexibility in the data type used in the bag.
- **length**: An integer representing the number of active elements in the ADT.
- **capacity**: An integer representing the capacity of the bag, which doubles when it is reached.
- **r**: A relation that determines the order in which elements are added to the Sorted Bag.

## Operations

A few fundamental operations of the interface are briefly covered and explained, along with their complexity:

### Add
- **Description**: Adds an element to the Sorted Bag according to the given relation. A search is performed while the relation holds true, or if the counter hasn't exceeded the number of active elements, to identify where in the array to add the new element and to move others if necessary. If the bag's capacity is reached, it resizes to accommodate more elements.
- **Complexity**: Θ(n) (regardless of the number of elements, the entire array is iterated over, either for checking existence or for moving elements).

### Resize
- **Description**: Doubles the capacity of the dynamic array when it is full, ensuring there is room for additional elements.
- **Complexity**: Θ(n)

### Remove
- **Description**: Removes an element from the Sorted Bag if it exists. If the element is not found, the operation returns false.
- **Complexity**: Θ(n) (regardless of whether the element exists, the entire array must be searched, and if found, elements need to be moved).

### Search
- **Description**: Searches for an element in the Sorted Bag using a variation of Binary Search. The lower time complexity is preferred here, especially knowing that the elements are sorted. Returns true if the element is found; otherwise, returns false.
- **Best Case Complexity**: Θ(1) (element is in the middle)
- **Worst Case Complexity**: Θ(log(n)) (element is not present)
- **Total Complexity**: O(log(n))

## Iterator

To iterate over the Sorted Bag, a current element is initialized with 0 and is incremented to point to the next element, and so on.

## Tests

The tests are composed of short and extended scenarios designed to target the main aspects and edge cases. The results of the tests are visible as soon as the program finishes its execution.
![image](https://github.com/user-attachments/assets/92b7b8bd-4717-434d-a799-8b50e9017514)
