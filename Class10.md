## Class 10: Tree Traversals

### Topics
- [Tree traversal]
    - [Depth-first search]: pre-order, post-order, in-order traversal
    - [Breadth-first search]: level-order traversal

### Resources
- Review Make School's [tree traversal slides]
- Watch Make School's [tree traversal video lecture]
- Read Interview Cake's articles on [depth-first search][IC DFS], [breadth-first search][IC BFS], and [binary tree properties][IC binary tree]
- Watch HackerRank's [trees and binary search tree video][HR trees video] (traversals start at 3:00)
- Watch Harvards's [family trees and binary search tree video][Harvard trees video] and [stack frames video]
- Play with VisuAlgo's [interactive binary search tree visualization][visualgo bst]

### Challenges
- Implement tree traversal methods on the `BinarySearchTree` class using [binary tree starter code]:
    - `_traverse_in_order_recursive` - traverse the tree with recursive in-order traversal (DFS)
    - `_traverse_pre_order_recursive` - traverse the tree with recursive pre-order traversal (DFS)
    - `_traverse_post_order_recursive` - traverse the tree with recursive post-order traversal (DFS)
    - `_traverse_level_order_iterative` - traverse the tree with iterative level-order traversal (BFS)
- Annotate tree traversal methods with complexity analysis of running time and space (memory)
- Run `python binarytree.py` to test `BinarySearchTree` traversal methods on a small example
- Run `pytest binarytree_test.py` to run the [binary tree unit tests] and fix any failures

### Stretch Challenges
- Implement iterative tree traversal methods on the `BinarySearchTree` class (*without using recursion*):
    - `_traverse_in_order_iterative` - traverse the tree with iterative in-order traversal (DFS)
    - `_traverse_pre_order_iterative` - traverse the tree with iterative pre-order traversal (DFS)
    - `_traverse_post_order_iterative` - traverse the tree with iterative post-order traversal (DFS)
- Annotate tree traversal methods with complexity analysis of running time and space (memory)


[tree traversal]: https://en.wikipedia.org/wiki/Tree_traversal
[depth-first search]: https://en.wikipedia.org/wiki/Depth-first_search
[breadth-first search]: https://en.wikipedia.org/wiki/Breadth-first_search

[tree traversal slides]: slides/TreeTraversals.pdf
[tree traversal video lecture]: https://www.youtube.com/watch?v=Qd8dKFaRu9I
[HR trees video]: https://www.youtube.com/watch?v=oSWTXtMglKE
[HR bst interview problem]: https://www.youtube.com/watch?v=i_Q0v_Ct5lY
[Harvard trees video]: https://www.youtube.com/watch?v=mFptHjTT3l8
[stack frames video]: https://www.youtube.com/watch?v=beqqGIdabrE
[IC BFS]: https://www.interviewcake.com/concept/python/bfs
[IC DFS]: https://www.interviewcake.com/concept/python/dfs
[IC binary tree]: https://www.interviewcake.com/concept/python/binary-tree
[visualgo bst]: https://visualgo.net/bst

[binary tree starter code]: source/binarytree.py
[binary tree unit tests]: source/binarytree_test.py
