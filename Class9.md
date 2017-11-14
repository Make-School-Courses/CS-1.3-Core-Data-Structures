## Class 9: Trees & Binary Search Trees

### Topics
- [Tree] data structure, [terminology]
- [Binary search tree], [operations]

### Resources
- Review Make School's [trees slides]
- Watch Make School's [trees video lecture]
- Read Interview Cake's [logarithms and binary search article][IC logarithms] and [binary tree properties article][IC binary tree]
- Watch HackerRank's [trees and binary search tree video][HR trees video] (up to 3:00)
- Watch Harvards's [family trees and binary search tree video][Harvard trees video] and [stack frames video]
- Play with VisuAlgo's [interactive binary search tree visualization][visualgo bst]

### Challenges
- Implement `BinaryTreeNode` class with the following properties and instance methods using [binary tree starter code]:
    - `data` - the node's data element
    - `left` - the node's left child, or `None` (if it does not exist)
    - `right` - the node's right child, or `None` (if it does not exist)
    - `is_leaf` - check if the node is a leaf (an external node that has no children)
    - `is_branch` - check if the node is a branch (an internal node that has at least one child)
    - `height` - return the node's height (the number of edges on the longest downward path from the node to a descendant leaf node)
- Implement `BinarySearchTree` class using `BinaryTreeNode` objects with the following properties and instance methods using [binary tree starter code]:
    - `root` - the tree's root node, or `None` (if the tree is empty)
    - `size` - property that tracks the number of nodes in constant time
    - `is_empty` - check if the tree is empty (has no nodes)
    - `height` - return the tree's height (the number of edges on the longest downward path from the tree's root node to a descendant leaf node)
    - `contains(item)` - return a boolean indicating whether `item` is present in the tree
    - `search(item)` - return an item in the tree matching the given `item`, or `None` if not found
    - `insert(item)` - insert the given `item` in order into the tree
    - `_find_node(item)` - return the node containing `item` in the tree, or `None` if not found (*hint: implement this first*)
    - `_find_parent_node(item)` - return the parent of the node containing `item` (or the parent of where `item` would be if inserted) in the tree, or `None` if the tree is empty or has only a root node
- Run `python binarytree.py` to test `BinarySearchTree` class instance methods on a small example
- Run `pytest binarytree_test.py` to run the [binary tree unit tests] and fix any failures
- Write additional unit tests for the `BinaryTreeNode` and `BinarySearchTree` classes
    - Add to existing test cases to ensure the `size` property is correct
    - Include test cases for the `height` instance method on both classes
- Annotate class instance methods with complexity analysis of running time

### Stretch Challenges
- Implement this additional `BinarySearchTree` class instance method:
    - `delete(item)` - remove `item` from the tree, if present, or else raise `ValueError` (*hint: break this down into cases based on how many children the node containing `item` has and implement helper methods for subtasks of the more complex cases*)
- Implement binary search tree with singly linked list nodes (having only one link to another node) instead of binary tree nodes (having two links to other nodes)


[tree]: https://en.wikipedia.org/wiki/Tree_(data_structure)
[terminology]: https://en.wikipedia.org/wiki/Tree_(data_structure)#Terminology_used_in_trees
[binary search tree]: https://en.wikipedia.org/wiki/Binary_search_tree
[operations]: https://en.wikipedia.org/wiki/Binary_search_tree#Operations

[trees slides]: slides/Trees.pdf
[trees video lecture]: https://www.youtube.com/watch?v=Yr3y78d2KYI
[HR trees video]: https://www.youtube.com/watch?v=oSWTXtMglKE
[HR bst interview problem]: https://www.youtube.com/watch?v=i_Q0v_Ct5lY
[Harvard trees video]: https://www.youtube.com/watch?v=mFptHjTT3l8
[stack frames video]: https://www.youtube.com/watch?v=beqqGIdabrE
[IC logarithms]: https://www.interviewcake.com/article/python/logarithms
[IC binary tree]: https://www.interviewcake.com/concept/python/binary-tree
[visualgo bst]: https://visualgo.net/bst

[binary tree starter code]: source/binarytree.py
[binary tree unit tests]: source/binarytree_test.py
