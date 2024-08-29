# Matrix ADT with Binary Search Tree (BST)

In this project, I implemented the Matrix ADT where elements are stored as triplets (`<line, column, value>`) in a Binary Search Tree (BST). Each operation was tested to ensure correctness and efficiency.

## Node Structure

The `MatrixNode` structure represents nodes in the BST. Each node contains:

- **row**: The row index of the matrix element.
- **column**: The column index of the matrix element.
- **value**: The value of the matrix element.
- **left**: Pointer to the left child node.
- **right**: Pointer to the right child node.
- **parent**: Pointer to the parent node.

## Matrix Attributes

- **nr_lines**: An integer representing the number of rows in the matrix.
- **nr_columns**: An integer representing the number of columns in the matrix.
- **nr_elems**: An integer representing the number of elements currently in the matrix.
- **root**: A pointer to the root node of the BST that represents the matrix.

## Operations

### Constructor
- **Description**: Initializes a matrix with a specified number of rows and columns. Sets up an empty BST.
- **Complexity**: Θ(1)

### Get Number of Lines and Columns
- **Description**: Returns the number of rows and columns in the matrix.
- **Complexity**: Θ(1) for both operations

### Access Element
- **Description**: Retrieves the value at position `(i, j)`. Throws an exception if the position is invalid.
- **Best Case Complexity**: Θ(1) (element is at the root)
- **Worst Case Complexity**: Θ(h) (element is at a leaf or not present, where h is the height of the BST)
- **Total Complexity**: O(h)

### Modify Element
- **Description**: Modifies or inserts a value at position `(i, j)`. Returns the previous value. Handles insertion and deletion of nodes.
- **Best Case Complexity**: Θ(1) (modification at the root)
- **Worst Case Complexity**: Θ(h) (insertion or deletion involves traversing the BST)
- **Total Complexity**: O(h)

### Remove Node
- **Description**: Removes a node from the BST. Manages nodes with no, one, or two children.
- **Worst Case Complexity**: Θ(h) (finding and re-linking nodes)
- **Total Complexity**: O(h)

### Set Main Diagonal
- **Description**: Sets all diagonal elements (where row equals column) to a specified value. Creates nodes if they do not exist.
- **Worst Case Complexity**: Θ(nr_lines * h) (each diagonal element may require traversal)
- **Total Complexity**: O(nr_lines * h)

## Iterator

An iterator traverses the matrix in-order, starting from the root and visiting nodes in ascending order of their row and column indices. It moves through the BST from one node to the next until it has visited all nodes.

## Tests

The tests include:
- Adding elements and verifying correct matrix updates.
- Removing elements and ensuring proper node re-linking.
- Accessing and modifying elements to check correctness.
- Setting the main diagonal and validating changes.

Test results are displayed upon program execution, demonstrating the matrix operations' accuracy and efficiency.

![image](https://github.com/user-attachments/assets/7c7dd1fe-7bd7-4ae8-af8f-0a88991b81ba)
