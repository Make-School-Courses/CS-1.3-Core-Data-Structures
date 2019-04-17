# Class 4: Arrays & Linked Lists

## Topics
- Compare [abstract data types] and [concrete data structures][data structures]
- Abstract data types: [list]
- Concrete data structures: [array], [dynamic array (resizable array, vector)][dynamic array], [linked list]

## Learning Outcomes (5 min)

By this end of this lesson, students should be able to...

1. Practice more advanced techniques with lists and arrays
1. Implement list manipulation methods such as insert and replace

## Minute-by-Minute

| **Elapsed** | **Time**  | **Activity**              |
| ----------- | --------- | ------------------------- |
| 0:00        | 0:15      | Discuss Palindrome Notes                |
| 0:05        | 1:20      | Code Review + Presentations       |
| 1:35        | 0:10      | Break      |
| 1:45        | 0:05      | Wrap up      |
| TOTAL       | 1:50      |                           |

## Progress Tracker (3 min)

- Fill out attendance, challenges completed, etc.

## Palindromes (15 min)
- Discuss Palindrome Notes with a partner.  Compare iterative and recursive solutions.

## Code Review + Presentations (80 min)
### Student Code Review Presentation (Palindrome) (20 min)
Iterative Solution Highlights:
- Find left and right bound then compare left to right
    - if not same done
    - if all same - return true
- Run through a small example on the board of a translator method to translate string to comparable string.
`"Taco? Cat!" ->"Taco Cat" -> "TacoCat" -> "tacocat"`
-  Example of loop: draw an arrow pointing to comparisons t to t, a to a, c to c, o (middle)
- look at < vs <= to show both work in this case
- unit tests of even and odd length words test boundary cases.

#### Complexity (5 min)
- What is the complexity of the iterative solution?
    - Only have to look at 1/2 the string, not every character. n/2 iterations `O(n^2)`
- Separate preamble (translator creation) from input (string) dependent code.  Thus not calling a method every time when not needed.
- Optimize by `.lower` on letter inside the conditional.
    - does this work with order of operations? (yes values are computed before compared)

### Student Code Review Presentation (Palindrome - Recursive) (15 min)
Recursive Solution Highlights:
- set left and right values
- translate to a comparable string by recursively moving if it is not in LETTERS (set of ascii values)

**Tips:**
- Build example on the whiteboard showing how right and left move until they get to a letter and then do a compare.
- Show the recursive stack unwinding on the whiteboard

### Break (10 min)

### Pair Code Review  (30 min)
- Review your findIndex method with a partner.

### Student Code Review Presentation (findIndex) (20 min)
- Create a diagram of how it works in code comments for future reference and on the whiteboard

EX: Check if "nas" is in "bananas"
- letters of "bananas" for the labels of the columns
- letters of "nas" labels of rows
- loop through letters in bananas to check if "nas" is in "bananas"
- if so will have one check per row under corresponding col of "bananas"

```
    INITIAL MATRIX
    [| |b|a|n|a|n|a|s|]
    [|n| | | | | | | |]
    [|a| | | | | | | |]
    [|s| | | | | | | |]

    MATRIX AFTER ALGORITHM
    [| |b|a|n|a|n|a|s|]
    [|n|X|X|O|X|O| | |]
    [|a| | | |O| |O| |]
    [|s| | | | |X| |O|]
```

#### Complexity

- Algorithm analysis - area of the rectangle (length of text * length of pattern) : O(nm)

## Wrap Up (5 min)

Go over the challenges for next class, and allow for clarifying questions.

**Next topic: Arrays and Linked Lists**
- Differences between Linked List and Array
    - can access arbitrary address of array in constant time - so can find middle element with binary search.  
    - In Linked List, you can't access the middle directly (have to traverse from beginning) so binary search would not work.
- Similarity between Array and Linked List?
    - they both are ordered
    - both implements methods: insert, append, prepend, read
- List Abstract Data Type - ADT
    - Arrays and Linked List are concrete Data Structures that can implement the ADT / Interface / Protocol

#### Preview of Challenges for next class (20 min):
Implement methods on linked list class so interface is the same as an array. [On repo - includes example, unit tests, starter code]

##TT (from previous session)
Stacks and Queues are abstract data types.  They can be implemented with an array or a linked list.  They share common methods like
- isEmpty
- isFull
- size

### Queue
- A queue is a like a line
    -enqueue : add to front of the List
    -dequeue: remove from end of the list
    -front: view the object at the front
    -FIFO : first in first out
- Real life examples:
    - Priority Queue: covered in CS 2.1

### Stack
- A stack is like a set of plates you add and remove from the top.
    - Push: add an object to the top
    - Pop: remove top items
    - Peek: view object on the top
    - LIFO:
- Real life examples:
    - Function Stack: Function calls go on the stack, popped when the function returns.
    - Stack trace: The call stack being displayed to your terminal.

## Resources
- Review Make School's [array and linked list slides]
- Watch Make School's [array and linked list video lecture]
- Read Vaidehi Joshi's [articles on linked lists, part 1: how they work][BaseCS linked list 1] and [part 2: complexity analysis and comparison to arrays][BaseCS linked list 2] with excellent, beautiful drawings
- Watch HackerRank's [linked list video]
- Watch Harvard's [array video], [singly linked list video], and [doubly linked list video]
- Play with VisuAlgo's [interactive linked list visualization][visualgo list]

## Challenges
- Add new features to `LinkedList` class using [linked list starter code]:
    - Add `size` property that tracks list length in constant running time
    - Implement `get_at_index(index)` - returns the item at `index` in the list
    - Implement `insert_at_index(index, item)` - inserts `item` at `index` (all items after `index` are moved down)
    - Implement `replace(old_item, new_item)` - replaces `old_item` in the list with `new_item` using the same node
    - Run `python linkedlist.py` to test `LinkedList` class instance methods on a small example
    - Run `pytest linkedlist_test.py` to run the [linked list unit tests] and fix any failures
- Annotate methods with complexity analysis of running time and space (memory)

### Stretch Challenges
- Implement `DoublyLinkedList` class with `BinaryNode` objects, which have both `next` and `previous` properties
- Write unit tests for to ensure the `DoublyLinkedList` class is robust
    - Include test cases for each class instance method and property
- Annotate methods with complexity analysis of running time and space (memory)


[abstract data types]: https://en.wikipedia.org/wiki/Abstract_data_type
[data structures]: https://en.wikipedia.org/wiki/Data_structure
[list]: https://en.wikipedia.org/wiki/List_(abstract_data_type)
[array]: https://en.wikipedia.org/wiki/Array_data_structure
[dynamic array]: https://en.wikipedia.org/wiki/Dynamic_array
[linked list]: https://en.wikipedia.org/wiki/Linked_list

[array and linked list slides]: slides/ArraysLinkedLists.pdf
[array and linked list video lecture]: https://www.youtube.com/watch?v=3WWuf4H61Nk
[linked list video]: https://www.youtube.com/watch?v=njTh_OwMljA
[array video]: https://www.youtube.com/watch?v=7EdaoE46BTI
[singly linked list video]: https://www.youtube.com/watch?v=ZoG2hOIoTnA
[doubly linked list video]: https://www.youtube.com/watch?v=HmAEzp1taIE

[BaseCS linked list 1]: https://medium.com/basecs/whats-a-linked-list-anyway-part-1-d8b7e6508b9d
[BaseCS linked list 2]: https://medium.com/basecs/whats-a-linked-list-anyway-part-2-131d96f71996
[visualgo list]: https://visualgo.net/list

[linked list starter code]: source/linkedlist.py
[linked list unit tests]: source/linkedlist_test.py
