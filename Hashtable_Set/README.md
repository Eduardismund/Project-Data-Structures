# Set on Hashtable

In this project, I implemented the interface of a Set using a on Hashtable with open addressing and double hashing and tested each feature to demonstrate its correctness and robustness.

## Set Attributes

### `elements`

- **Type**: `TElem*` (Array of elements)
- **Description**: This array holds the actual data of the hash table. It stores elements directly and uses special values to denote empty and deleted slots.
- **Special Values**:
  - **`EMPTY_POSITION`**: Indicates that a slot in the array has never been used.
  - **`DELETED_POSITION`**: Indicates that a slot was previously occupied but has been removed.

### `capacity`

- **Type**: `int`
- **Description**: Represents the current size of the `elements` array, i.e., the number of slots available in the hash table. This capacity determines how many slots are available for storing elements and affects the distribution of elements.

### `sizeSet`

- **Type**: `int`
- **Description**: The number of elements currently stored in the hash table. This helps manage the load factor, which is the ratio of the number of elements to the capacity. The load factor is important for deciding when to resize the hash table.

## Hash Functions

### `hashFunction1(TElem elem)`

- **Purpose**: Computes the primary hash value.
- **Formula**: `elem % this->capacity`
- **Usage**: Provides the initial index for probing. It helps distribute elements uniformly across available slots.

### `hashFunction2(TElem elem)`

- **Purpose**: Computes the secondary hash value to handle collisions.
- **Formula**: `1 + (elem % (this->capacity - 1))`
- **Usage**: Provides the step size for probing in case of collisions. It ensures that the probing sequence does not repeat in the same pattern.

## Double Hashing Function

### `doubleHash(TElem elem)`

- **Purpose**: Determines the position for inserting or finding an element using double hashing.
- **Process**:
  - **Primary Hash**: Compute the initial index using `hashFunction1`.
  - **Probing**: If the computed position is occupied (i.e., not empty or deleted), increment the probe number and recompute the position using the secondary hash function (`hashFunction2`) to find the next slot to check.
  - **Termination**: The process continues until an empty or deleted slot is found or until all positions have been checked (full table scenario).
- **Return Value**: Returns the index where the element should be placed or found. If the table is full, it returns `-1`.

## Operations

A few fundamental operations of the interface are briefly covered and explained, along with their complexity:

## Add

- **Description**: Inserts an element into the hash table. If the element already exists, the operation will not add it again and will return `false`. If the element is new, it is added to its appropriate position.
- **Best Case Complexity**: Θ(1) (when the element is added in an empty slot or the table is initially empty).
- **Worst Case Complexity**: Θ(capacity) (when the element needs to be rehashed due to collisions or if the table needs resizing).
- **Total Complexity**: O(capacity) (considering resizing and rehashing operations).

## Remove

- **Description**: Removes an element from the hash table if it exists. If the element is found, it is marked as `DELETED_POSITION`, which allows the slot to be reused in the future.
- **Best Case Complexity**: Θ(1) (when the element is located in the first slot or quickly found).
- **Worst Case Complexity**: Θ(capacity) (when the element needs to be searched through several probes or if the element is not present).
- **Total Complexity**: O(capacity) (including search and deletion operations).

## Search

- **Description**: Searches for an element in the hash table. Returns `true` if the element is found, otherwise returns `false`.
- **Best Case Complexity**: Θ(1) (when the element is found at the initial hash position).
- **Worst Case Complexity**: Θ(capacity) (when the element must be searched through several probing sequences or is not present).
- **Total Complexity**: O(capacity) (considering the probing sequence).

## Resize

- **Description**: Expands the hash table when the load factor exceeds a certain threshold. The capacity is increased, usually to a prime number greater than twice the current capacity. All existing elements are rehashed and inserted into the new table.
- **Process**:
  - **Allocate New Array**: Create a new `elements` array with increased capacity.
  - **Rehash Elements**: Recompute the positions of existing elements and insert them into the new array.
  - **Update Capacity**: Set the new capacity and update the internal data structures.
- **Complexity**: Θ(capacity) (for copying and rehashing all existing elements).

## Iterator

The `SetIterator` class allows iteration over a hash table implemented with open addressing and double hashing. It provides methods to move to the first valid element, advance to the next, and move to the previous element. 


## Tests

They are composed of short and extended tests that are meant to target the main aspect and the corner cases. The result of the tests is visible as soon as the program stops its execution.
![image](https://github.com/user-attachments/assets/ae13d6b9-7a01-43c1-907f-7ddf61b1f32f)
