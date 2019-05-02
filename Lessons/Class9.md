# Class 9: Tree Traversals

## Learning Objectives

By this end of this lesson, students should be able to...

1. Differentiate between depth-first search (DFS) and breadth-first search (BFS)
1. Explain the various types of traversals for DFS and BFS
1. Implement traversal methods on a binary search tree

## Topics
- [Tree traversal]
    - [Depth-first search]: pre-order, post-order, in-order traversal
    - [Breadth-first search]: level-order traversal

## Resources
- Review Make School's [tree traversal slides]
- Watch Make School's [tree traversal video lecture]
- Read Interview Cake's articles on [depth-first search][IC DFS], [breadth-first search][IC BFS], and [binary tree properties][IC binary tree]
- Read Vaidehi Joshi's articles on [depth-first search][BaseCS DFS] and [breadth-first search][BaseCS BFS] with beautiful drawings and excellent analysis
- Watch HackerRank's [trees and binary search tree video][HR trees video] (traversals start at 3:00)
- Watch Harvards's [family trees and binary search tree video][Harvard trees video] and [stack frames video]
- Play with VisuAlgo's [interactive binary search tree visualization][visualgo bst]

## Challenges
- Implement tree traversal methods on the `BinarySearchTree` class using [binary tree starter code]:
    - `_traverse_in_order_recursive` - traverse the tree with recursive in-order traversal (DFS)
    - `_traverse_pre_order_recursive` - traverse the tree with recursive pre-order traversal (DFS)
    - `_traverse_post_order_recursive` - traverse the tree with recursive post-order traversal (DFS)
    - `_traverse_level_order_iterative` - traverse the tree with iterative level-order traversal (BFS)
- Annotate tree traversal methods with complexity analysis of running time and space (memory)
- Run `python binarytree.py` to test `BinarySearchTree` traversal methods on a small example
- Run `pytest binarytree_test.py` to run the [binary tree unit tests] and fix any failures

## Stretch Challenges
- Implement iterative tree traversal methods on the `BinarySearchTree` class (*without using recursion*):
    - `_traverse_in_order_iterative` - traverse the tree with iterative in-order traversal (DFS)
    - `_traverse_pre_order_iterative` - traverse the tree with iterative pre-order traversal (DFS)
    - `_traverse_post_order_iterative` - traverse the tree with iterative post-order traversal (DFS)
- Annotate tree traversal methods with complexity analysis of running time and space (memory)
- Implement `TreeMap` class ([map/dictionary][map] abstract data type implemented with [binary search tree] data structure) with the following properties and instance methods:
    - `__init__` - initialize a new empty tree map structure
    - `size` - property that tracks the number of tree map entries in constant time
    - `keys` - return a list of all keys in the tree map
    - `values` - return a list of all values in the tree map
    - `items` - return a list of all entries (key-value pairs) in the tree map
    - `contains(key)` - return a boolean indicating whether `key` is in the tree map
    - `get(key)` - return the value associated with `key` in the tree map, or raise `KeyError` if not found
    - `set(key, value)` - insert `key` (or update, if already present) with associated `value` in the tree map
    - `delete(key)` - delete `key` and associated value from the tree map, or raise `KeyError` if not found
- Write unit tests to ensure the `TreeMap` class is robust (*hint: these should be very similar to the hash table unit tests*)
    - Include test cases for each class instance method
- Annotate class instance methods with complexity analysis of running time and space (memory)
- Compare the behaviors of your `TreeMap` class to those of the `HashTable` class and the [Python `dict` type]

## TT - Tree Traversals (20 min)

![tree-traversals](./assets/tree-traversals.png)

See [slides](https://github.com/Make-School-Courses/CS-1.3-Core-Data-Structures/blob/master/Lessons/slides/TreeTraversals.pdf)

- What if you wanted to have a tree give all of its elements, instead of just one in particular?
- The goal of a traversal is to **visit** each node once and only once. Whatever action you do on a visit is arbitrary.
- You can **traverese either left or right** down sub-trees of a tree
- For convention, we always traverse from left to right
- There are two main ways to traverse: **Depth-first search (DFS) or Breadth-first search (BFS)**
    - DFS visits a child and then descendents - you drill down one side of the tree, gradually making your way from left to right
    - BFS vists across levels - vist all siblings before going deeper into the tree

### DFS

Within DFS we can visit nodes in three different ways: 

1. **In-order**
1. **Pre-order**
1. **Post-order**

#### In-order

Make sure everything in the left sub-tree is visited first before the parent, then visit the parent, then visit everything in the right sub-tree. Walk through the traversal on the slides for details

#### Worksheet Part 2

Do the first row of the worksheet for DFS in-order

#### Pre-Order
Same as in-order, but visit first before exploring the left sub-tree. Visit node, explore the left-sub tree as far as you can, visiting each node you get to, and then do the same for the right sub-tree. Walk through the traversal on the slides for details

#### Worksheet Part 2

Fill in second row of the worksheet

#### Post-order

Traverse left sub-tree as far as you can, then the right-subtree as far as you can, and then finally visit the node when you can't traverse further. Walk through the traversal on the slides for details

#### Worksheet Part 2

Fill in third row of the worksheet

### BFS

- Vist from the root down to the leaves, left to right, one horizontal layer/level at a time
- Use a queue that we `enqueue` and `dequeue` to explore nodes

### Worksheet Part 2

Fill in fourth row of the worksheet


[tree traversal]: https://en.wikipedia.org/wiki/Tree_traversal
[depth-first search]: https://en.wikipedia.org/wiki/Depth-first_search
[breadth-first search]: https://en.wikipedia.org/wiki/Breadth-first_search
[binary search tree]: https://en.wikipedia.org/wiki/Binary_search_tree
[map]: https://en.wikipedia.org/wiki/Associative_array
[Python `dict` type]: https://docs.python.org/3/library/stdtypes.html#dict

[tree traversal slides]: slides/TreeTraversals.pdf
[tree traversal video lecture]: https://www.youtube.com/watch?v=Qd8dKFaRu9I
[HR trees video]: https://www.youtube.com/watch?v=oSWTXtMglKE
[HR bst interview problem]: https://www.youtube.com/watch?v=i_Q0v_Ct5lY
[Harvard trees video]: https://www.youtube.com/watch?v=mFptHjTT3l8
[stack frames video]: https://www.youtube.com/watch?v=beqqGIdabrE

[IC BFS]: https://www.interviewcake.com/concept/python/bfs
[IC DFS]: https://www.interviewcake.com/concept/python/dfs
[IC binary tree]: https://www.interviewcake.com/concept/python/binary-tree
[BaseCS DFS]: https://medium.com/basecs/demystifying-depth-first-search-a7c14cccf056
[BaseCS BFS]: https://medium.com/basecs/breaking-down-breadth-first-search-cebe696709d9
[visualgo bst]: https://visualgo.net/bst

[binary tree starter code]: source/binarytree.py
[binary tree unit tests]: source/binarytree_test.py
