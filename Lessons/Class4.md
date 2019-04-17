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

## Progress Tracker (10 min)

- Fill out attendance, challenges completed, etc.
- Tracker leaderboard - students who have completed most challenges
- Technical Articles : write a draft by next Wed 4/24.
    - Requirements:
        - 5 min read on medium.
        - Topic - anything we've covered in this class - or you can go into something deeper.
        - draft - topic and outine
        - needs diagrams (can be borrowed) - *no tolerance of plagiarism*
- Added code review tracking to progress tracker - everyone should do at least one live code review before end of course.

## Code Review + Presentations (80 min)
### Student Code Review Presentation (Linked List - Insert) (20 min)
Linked List Insertion Highlights:
- Draw a diagram Linked List containing: "I", "Love", "Cats" (in that order).  Walk through the diagram as the student presents their code

- What does the method 'insert_at_index(index, value) - value goes at index, items shift down
- Explore the range function by running code `range(1) = [0]`, `range(3)=[0,1,2]`
- Write a test case to find bugs. Don't rewrite code without showing the bug.
- Review: when to use a for loop or while loop: while has condition, for loop uses an index (counter controlled)  

**Whiteboard Tips**
- Switch colors of markers between setup and implementation.

### Student Code Review Presentation (Linked List - Insert) (20 min)
Linked List Replace Highlights:
- Run your personal code on your whiteboard diagram as student explains
- discussion : difference between break and return.
    - using return means the ValueError doesn't run if found.
- What part of this code 'node=node.next' what is evaluated first?  
    - need to evaluate the right hand side first before assignment.
- Code doesn't use 'return self' because replace doesn't expect a return value.

## Break (10 min)

#### Preview of Challenges for next class (20 min):
See slides and notes on next lesson (Stacks and Queues).

Concrete Data Structures
- in CS 1 you learned about Arrays - what are the two types? List is an ordered sequence of items you can store items in, add, remove, replace,
- Abstract Data Structures: List (both arrays and LinkedLists are Concrete examples of the List ADT)
(Whiteboard (Left is ADT | Concrete Data Type))
ADT is like the API | Concrete is like backend - implementation details hidden from ADT (frontend)
- An ADT is like an interface in Java, a protocol in Swift.
- Types of arrays : dynamic, static
- Types of linked lists: doubly linked, single linked

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
