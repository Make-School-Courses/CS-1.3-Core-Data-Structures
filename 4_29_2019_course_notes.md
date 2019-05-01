#Start of class
- NOTE: no learning outcomes

- get a whiteboard plan your solution to this problem ([slide](https://docs.google.com/document/d/1Zubz61IgpVddClWwnyauiFwANXn_xOoLDuK5hMbZRjw/preview))
    - Problem: "A web application needs to redact some words.  Write a function that takes two arrays of words (strings), and returns a new array of words in the first array (the text) that are not in the second array (the redacted words)."
    - Step 0: Write Pseudocode (more on the slide)
    - students given 25 min to work on.  Engaged
    - clarifying question: If there is three of the same word in a sentence - do you remove all three? (think of the problem statement ie redaction)
- [2:00] Check in on how students are doing - moved them forward to the next step.
[2:22] - Called the class back - had them commit their unit test and solution.  Update tracker.

- BREAK

[2:35]
New topic - trees
- slides
- a tree is a set of nodes and edges. An edge is a reference to a tree.  Note the use of the word set.
- just like a linked list we have nodes and edges.  An edge (usual notation for a tree) is like a link in a LinkedList.  A tree is just a LinkedList with two pointers.
- We will focus on binary search trees for the next several courses.
- In future classes we will look at many other trees and graphs.

- Examples of trees (diagram)
- Vocabulary : Parent, Child.  Root (Parent of all nodes) .  
- Not Trees (diagram)- have cycles, are disconnected.
- Binary Tree: tree in which each node has at most two children
- Activity: whiteboard: draw this tree (diagram on visu-algo site).
    - vocabulary exercise : identify on your whiteboard drawing - slides show terms 1 by 1 with explaination.  NOTE: This was great.
        - root:unique topmost node of tree that can reach all other nodes
        - parent -> child:
        - descendant:node reachable from parent to child, grandchild, etc.  (SUGGESTION: maybe re-word)
        - ancestor: node reachable from child to parent, grandparent (SUGGESTION: maybe re-word)
        - leaf / external node: node without any children
        - branch / internal node: node with at least one child
    - reviewed on visu-algo.

- More vocab:
        -size: number of nodes in the tree
        - height (tree): number of edges on longest downward path from root to leaf.
        -height(node) number of edges on the longest downward path from node to leaf.
        -depth(node) number of edges between the node and the root.
        -level(node) 1+number of edges between the node and the root.
[NOTE: build a dynamic slide show - same graph, parts highlighted to emphasize the terms ]

-complete tree : every level (except maybe the last) is completely filled and nodes on the last level are as far left as possible.   
-perfect tree: every level is completely filled.

- balanced tree: all leaves are at a minimum possible depth.  This matters a lot for runtime - better runtime on balanced trees.
- question - why would you input data that is unbalanced?
- answer [Alan] - you don't control the way the user inputs data.  There are ways to auto balance but we'll cover that in the next course.

- Binary Search Tree: always sorted, for each node left children are smaller, right children are larger.  No duplicate keys (usually)
 - diagram of BST - the root splits the tree into sub trees that also follow all the rules.
- look at the tree on your whiteboard - is it a binary search tree?
    - question: does the structure of the tree depend on the order that they are entered? (yes).  Without auto balancing, the root node is always the first item inserted.
- what is a BST good for? (any guesses) - imagine a phone book
- fast search, insertion, deletion - especially if it is balance.
- sort as you go instead of all at once.
- fairly simple implementation for good performance (when balanced)

- only allocates memory as it's needed.  Doesn't have to reallocate memory

- a note on log n.  When discussing time and space complexity of algorithms, log n usually means log base 2 n ( but the 2 is sometimes left off)

- Binary logorithm formula (see slide) the power by which 2 must be raised by to obtain n.


- Why is log n good.  Imagine a BST with 2^32 nodes.  How big is that number? (4.29 billion) This is a REALLY big number but can be represented by a tree that is only 32 levels deep.  So a search will only visit a maximum of 32 nodes to find the node containing the data we're looking for (assuming perfectly balanced).

- Insertion (see slides)

- Deletion (see slides)

- Check out the visu-algo site to walk through these algorithms.  Do the challenges (see the repo)
