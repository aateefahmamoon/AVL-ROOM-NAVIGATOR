# AVL-ROOM-NAVIGATOR
AVL Room Navigator is an intelligent room management system that efficiently organizes and navigates building layouts using a balanced AVL tree structure.


# AVL Room Navigator

## Introduction to AVL Room Navigator
**AVL Room Navigator** is an intelligent room management system designed to help you navigate through a building efficiently. By leveraging the power of an **AVL tree**, we ensure that the building layout remains balanced, much like how rooms are placed in a way that avoids overcrowding or confusion. This balance prevents the system from becoming sluggish or "tumbling over" with inefficiency.

The **Insert** operation allows you to easily add a new room number to the system, automatically placing it in the right position while maintaining the tree's balance. This ensures fast and organized access to room data as the building expands.

The **Search** operation lets you trace the path to a specific room, following a sequence of left and right steps based on the AVL tree structure. If a room is not found, the system kindly informs you that your room number isn’t part of the building, helping you avoid any confusion or misdirection.

With the **AVL Room Navigator**, both operations work seamlessly together to ensure that the building’s room directory remains well-structured, balanced, and quick to navigate.

---

## Table of Contents
1. [Introduction to AVL Room Navigator](#introduction-to-avl-room-navigator)
2. [Introduction to Binary Search Tree](#introduction-to-binary-search-tree)
3. [Need of Self Balancing Trees](#need-of-self-balancing-trees)
4. [AVL Trees Introduction](#avl-trees-introduction)
5. [AVL Trees vs Red Black Trees](#avl-trees-vs-red-black-trees)

---

## Introduction to Binary Search Tree

A **Binary Search Tree** is a data structure used in computer science for organizing and storing data in a sorted manner. A binary search tree follows all properties of a binary tree, where for every node, its left subtree contains values less than the node, and the right subtree contains values greater than the node. This hierarchical structure allows for efficient searching, insertion, and deletion operations on the data stored in the tree.

### Time Complexity of Binary Search Tree
- **Search:**
  - In a balanced BST, the time complexity for searching an element is O(log(n)), where n is the number of nodes in the tree. This efficiency is achieved by halving the search space at each level as we compare the target value with the current node's value and proceed left or right.
  - In an unbalanced BST, the worst-case time complexity for searching can be O(n) if the tree is completely skewed.
  
- **Insertion:**
  - In a balanced BST, the time complexity for inserting an element is O(log(n)) since we find the appropriate position to insert the new node while maintaining the BST property.
  - In an unbalanced BST, the worst-case time complexity for insertion can be O(n) if the tree is highly unbalanced.

- **Deletion:**
  - Similar to insertion, the time complexity for deletion in a balanced BST is O(log(n)) on average.
  - In an unbalanced BST, the worst-case time complexity for deletion can be O(n) if the tree is highly unbalanced.

---

## Need of Self Balancing Trees

Self-balancing trees are needed to maintain a relatively consistent height in a binary search tree, ensuring efficient operations like searching, insertion, and deletion by preventing the tree from becoming skewed, resulting in worst-case linear time complexity. They guarantee near-logarithmic time for these operations, even when data is inserted in a non-random order, making them ideal for applications where fast access to large datasets is crucial.

### Key Points about Self-Balancing Trees:
- **Prevent Skewed Trees:** A regular binary search tree can become unbalanced if data is inserted in a specific pattern, leading to a long, skewed branch that slows down operations.
- **Maintain Logarithmic Height:** By rebalancing during insertions and deletions, self-balancing trees ensure that the height of the tree remains proportional to log(n), ensuring efficient operations.
- **Applications:** Widely used in data structures like dictionaries, sets, and priority queues where fast lookups and updates are necessary.

### Example of a Self-Balancing Tree:
- **AVL Tree:** One of the most common self-balancing trees, where each node stores a balance factor (the difference in height between its left and right subtrees). Rotations are performed to maintain balance.
- **Red-Black Tree:** A red-black tree is a binary search tree with properties that ensure balance through coloring nodes either red or black.

---

## AVL Trees Introduction

The **AVL Tree** was invented by **GM Adelson-Velsky** and **EM Landis** in 1962. It is a height-balanced binary search tree where each node is associated with a balance factor, calculated by subtracting the height of the right subtree from the left subtree.

### Balance Factor Calculation
Balance Factor (k) = height(left(k)) - height(right(k))

A tree is considered balanced if the balance factor of every node is between -1 and 1. If the balance factor is outside this range, the tree needs to be rebalanced using rotations.

### Sub-Cases of Imbalance in AVL Trees
- **Left-Left (LL) Case:** The unbalanced node is left-heavy, and the left child node is also left-heavy. A single right rotation restores balance.
- **Right-Right (RR) Case:** The unbalanced node is right-heavy, and the right child node is also right-heavy. A single left rotation restores balance.
- **Left-Right (LR) Case:** The unbalanced node is left-heavy, but its left child node is right-heavy. A left rotation is done on the left child, followed by a right rotation on the unbalanced node.
- **Right-Left (RL) Case:** The unbalanced node is right-heavy, but its right child node is left-heavy. A right rotation is done on the right child, followed by a left rotation on the unbalanced node.

### Rotations
- **Right Rotation:** When a node is added to the left subtree of the left subtree, we do a right rotation.
- **Left Rotation:** When a node is added to the right subtree of the right subtree, we do a left rotation.

---

## AVL Trees vs Red-Black Trees

### **Red-Black Tree:**
- **Self-Balancing:** Achieved by painting each node with either red or black.
- **Properties:** Requires 1 bit of color information per node.
- **Time Complexity:** O(log n).

### **AVL Tree:**
- **Self-Balancing:** Height difference of the left and right subtrees should be less than 2.
- **Properties:** Requires more frequent rotations than red-black trees.
- **Time Complexity:** O(log n).

### Basis of Comparison

|**Basis of Comparison**| **Red-Black Trees**                    | **AVL Trees**                        |
|----------------------_|----------------------------------------|--------------------------------------|
| **Lookups**           | Fewer lookups, less strict balance     | Faster lookups due to strict balance |
| **Insertion/Removal** | Faster due to fewer rotations          | More complex due to strict balancing |
| **Storage**           | Requires 1 bit of information per node | Requires storage for balance factors |
| **Searching**         | Less efficient                         | More efficient                       |
| **Uses**              | Used in language libraries like `map`, | Used in databases for faster         |
|                       |  `multimap`, `multiset`                |  retrieval                           |

---

