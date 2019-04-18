# Class 6: Maps & Hash Tables

## Learning Objectives (5 min)

By this end of this lesson, students should be able to...

1. Explain the use cases for maps and hash tables and how they're related
1. Practice implementing various hash tables features
1. Describe various components of a hash table such as the hash function, collision resolution, load factor, and dynamize resizing

## Topics
- Abstract data types: [map (dictionary, associative array)][map]
- Concrete data structures: [hash table]
- [Hash functions], [collision resolution], [load factor], [dynamic resizing]

## Minute-by-Minute

| **Elapsed** | **Time**  | **Activity**              |
| ----------- | --------- | ------------------------- |
| 0:00        | 0:10      | Turn in Challenges So Far                |
| 0:10        | 0:15      | Activity - Stacks and Queues Worksheet - Overview  |
| 0:25        | 0:30      | Activity - Stacks and Queues Worksheet - Stack Portion       |
| 0:55        | 0:10      | TT - Amortization                     |
| 1:05        | 0:10      | BREAK      |
| 1:15        | 0:25      | Activity - Stacks and Queues Worksheet - Queue Portion      |
| 1:40        | 0:10      | Wrap Up - Abstract Types vs Concrete Data Structures      |
| TOTAL       | 1:50      |                           |

## Turn In Challenges So Far (10 min)

- Turn in CS 1.3 coding challenges for review, feedback, and grading!
- Deadline is end of day tomorrow (Thursday)
- Grading will start on Friday


## Activity - Stacks and Queues Worksheet - Overview  (15 min)

[Stacks and Queues Worksheet](https://docs.google.com/document/d/1zRnzN-QCKkejHTEBMzTQhdquY47Cu0JNbTNrliScVnw/edit?usp=sharing)

There are multiple ways we can implement abstract data types such as stacks and queues. Today we're going to go over four implementations each (eight total) for stacks and queues: two using a linked lists, and two using arrays

For each of the eight implementations, we will do the following:

1. Describe how we will implement the three key methods
    - `push`, `peek`, `pop` for stacks
    - `enqueue`, `front`, `dequeue` for queues
1. Provide the runtime for each operation
1. Decide which of the implementations is the best/worst for the abstract data type.
1. Update your code to match the better implementation

We'll fill out the worksheet one section at a time. Once you've completed a section, review with your partner, then go review with someone else in the class.

**The discussion goal** is to get as many opinions as possible on your implementation, and also to give feedback on as many different implementations as possible

**Reminder**: if runtime complexity is similar between implementations, think about **space complexity** when deciding what implementation to go with

- static (array) vs dynamic (linked list) memory space

### Tips

- Review your stacks and queues code from the previous challenge, see if you can find the good and bad decisions with each of the implementations you've already done. 
- Find out what decisions you made when building the functions for stacks and queues, and see if that will help with how you answer the worksheet

## Activity - Stacks and Queues Worksheet - Stack Portion  (30 min)

Take some time to fill in the stack portion of the worksheet. For the linked list section, you can assume we're using only singly linked lists

### Linked Lists

Draw a linked list with 3 nodes (top to bottom) such that top of stack is the head of the list

- Go through run times of each operation

Now draw the same list with the top of the stack at the tail of the list

- Go through the run times of each operation

### Arrays

Draw the array with the top of the stack at index 0
    - Draw array vertically, with the top cell being the top of the stack

**Tips:**

- Depending on the implementation, you may need to shift around items in the array for push and pop. This doesn't come at a "free" cost. Why?
- Arrays have constant time look up
- `Array.pop()` without an index will pop the `n-1` item


Now draw the array with the top of the stack at index n-1
    - Draw array vertically, with the bottom cell being the top of the stack

## TT - Amortization (10 min)

Think about **dynamic arrays** like tables at resturants:

- You have 5 people in your party, so you get seated at a table for 8
    - A dynamic array is similar: it has "extra seats" built in
- But what if you have a 9th person come? How do we append a new item at the end of the array if the array is full?
    - The resturant has to get a whole new 16 person table to accomodate everyone, and then everyone has to move over
    - Dynamic arrays are the same: they need to allocate a whole new, larger array to make this space, and then move all the items over to that larger array
- When the size needs to be increased, it takes `O(n)` time. But this is **a rare occurrence**
    -  This only happens when the array needs to double in size. Going back to the resturant, if you're at a table for 8, and a 9th person shows up, then you need to move to a 16 person table (`O(n)`), _but now you can add person 10-16 without having to change tables_ (`O(1)`)
- Therefore on average, adding items to the array still takes constant time, since the occasional times it takes `O(n)` is outwieghed by all of the times it usually takes `O(1)`
- However, we can't say it's `O(1)` due to the occasional `O(n)`, so we say it is **Amortized** constant time, denoated as `O(1)*` or `O(1) amortized` or `O(1) avg`.
    - Amortized means most of the time it's `O(1)`, but it is possible that it may take longer. This is rare enough though, that when we average it out, it's closer to constant time
 
## Break (10 min)

- An undo buffer (game, Photoshop, etc.) is an example of how you would use a stack!
- Fun example of this is [atom's scroll-through-time package](https://atom.io/packages/scroll-through-time)

## Activity - Stacks and Queues Worksheet - Queue portion (25 min)

- Same activity/directions as before, but now for queues!
- Reminder to talk to at least two other people and compare implementations


### Linked Lists

To draw the linked list, we reccomend the following steps:

- Draw the linked list going left to right
- Draw "head" and "tail" above the appropriate nodes 
- Then write "front" and "back" below the appropriate nodes

Just like before, first draw a queue using a linked list where the front of the queue is the tail of the list

Once you've solved that section, draw a queue using a linked list where the front of the queue is the head of the list

### Arrays

**Before you start:** Put an arrow next to the right of the chart on which implementation you think will be perform better.

First Draw an array (left to right) with index `0` on the leftmost side, index `n-1` on the rightmost side

- Put 4 elements in the array
- Label the leftmost element "back", and the rightmost element "front"

**Remember:** we _dequeue_ from the _front_ of the queue, and _enqueue_ from the _back_ of the queue

Fill out that section of the worksheet!

Once you're done, switch the "front" and "back" labels. The "front" of queue should now be at index `0`

**Tips:**

- Remember to check if something is _truly_ `O(1)` or if it's `O(1) avg`
- Sometimes there's no good choice for one implementation! i.e. sometimes it's clear to use a one data structure over the other

## Wrap Up - Abstract Types vs Concrete Data Structures (10 min)

![abstract-vs-concrete](./assets/abstract_concrete_comparision.png)

Make sure worksheet is filled out, with bad implementations crossed out

### Abstract Data Types

- Simliar to an API: they specify what operations you _can_ do. They're the "rules of the game"
- They do _not_ say how to implement it implemented
- A **List** is an ordered sequence of items
- **Stacks and queues** are special kinds of lists with special rules

### Concrete Data Strucutre

- These are _how you implement_ abstract data types
- Simlar to your backend: like deciding whether to build your server in node, python, go, etc.
- Things you can draw, and describe how they're allocated in memory
    - array (contiguous memory with indexes)
        - static (fixed size)
        - dynamic (resizeable)
    - linked list
        - singly
        - doubly

### Maps and Hashtables

#### Maps
- **Map** is another abstract data type
    - Same as a **dictionary** (swift, python), or an **associative array** (php, CS literature)
    - Does _not_ have an order to it. **It is an _unordered_ collection of _key/value pairs_**
    - A phonebook is an example of this: a person's name is the key, the value is the phone number
    - Generally, curly braces are used to denote these
    - Remember, this says _nothing_ about how it is organized, it just describes what the data in it looks like (key/value pairs)

#### Hashtable

![hashtable-implementation](./assets/hashtable_implementation.png)

- A **Hashtable** is a concrete data structure used to implement a map/dictionary. Python uses this to implement its dictionaries. 
- Small Side Note: you could implement a map with an array or linked list, but it wouldn't be as efficient
- A Hashtable is made up of the following parts:
    -  **hash function** - takes a key (`k`) and gives you a number (`n`)
        -  `h(k)` --> `n`
    -  **array** - a piece of contiguous memory that has indexes, which allow us to retrieve buckets in in constant time
    -  **linked list** -  each bucket in the array is a linked list of many elements. These could be empty
        -  Note: not all hashtables will use linked lists. Our implementation does use it though

#### Load Factor

-  The **load factor** (`L`) of a hashtable is the average length of each bucket = `(# entries in the hashtable)/(# of buckets)` = `n/b`
    - As the load factor gets higher, the buckets get longer. This is bad because it _increases the time it takes to iterate over buckets_, which negatively affects performance
- While the number of entries in the hashtable is not in our control (that's decided by the user; how many people they want in their phone book), the _number of buckets is in our control_.
- If we increase the number of buckets, we can get to a lower `L`, therefore dropping number of operations and _increasing performance_

#### Drawing Example

Draw a hashtable with 3 buckets and put 5 items in it

- The more buckets we have, the more space we have to store things
- Where does a new element land? Through **rehashing**: rearranging where items go to make sure they're in the appropriate spot in the **resized** hashtable
    - Remember the resturant tables example. The hashtable will need to be resized occasionally as you add more items
    - Rehash will give you a new index for items
    - More buckets means more memory!

## Resources
- Review Make School's [hash table slides]
- Watch Make School's [hash table video lecture]
- Read Vaidehi Joshi's [articles on hash tables][BaseCS hash tables] and [hash functions][BaseCS hash functions] with beautiful drawings and excellent examples
- Watch HackerRank's [hash table video]
- Watch Harvard's [old hash table video] and [new hash table video]
- Play with VisuAlgo's [interactive hash table visualization][visualgo hash table]

## Challenges
- Add new features to improve `HashTable` class using [hash table starter code]:
    - Add `size` property that tracks the number of hash table entries in constant time
    - Implement `load_factor` - return the [load factor], the ratio of number of entries to buckets
    - Implement `_resize` - perform [dynamic resizing] when `load_factor` exceeds `0.75` after an insertion (`set` is called with a new `key`) and rehash all key-value entries
    - Run `python hashtable.py` to test `HashTable` class instance methods on a small example
    - Run `pytest hashtable_test.py` to run the [hash table unit tests] and fix any failures
- Annotate methods with complexity analysis of running time and space (memory)

## Stretch Challenges
- Implement an alternative hash table [collision resolution] strategy instead of [separate chaining] (popular variants include [linear probing], [quadratic probing], and [double hashing])
- Write additional test cases to expand the [hash table unit tests] to ensure your collision resolution strategy is robust


[map]: https://en.wikipedia.org/wiki/Associative_array
[hash table]: https://en.wikipedia.org/wiki/Hash_table
[hash functions]: https://en.wikipedia.org/wiki/Hash_function
[load factor]: https://en.wikipedia.org/wiki/Hash_table#Key_statistics
[dynamic resizing]: https://en.wikipedia.org/wiki/Hash_table#Dynamic_resizing
[collision resolution]: https://en.wikipedia.org/wiki/Hash_table#Collision_resolution
[separate chaining]: https://en.wikipedia.org/wiki/Hash_table#Separate_chaining
[linear probing]: https://en.wikipedia.org/wiki/Linear_probing
[quadratic probing]: https://en.wikipedia.org/wiki/Quadratic_probing
[double hashing]: https://en.wikipedia.org/wiki/Double_hashing

[hash table slides]: slides/HashTables.pdf
[hash table video lecture]: https://www.youtube.com/watch?v=nLWXJ6IDKmQ
[hash table video]: https://www.youtube.com/watch?v=shs0KM3wKv8
[old hash table video]: https://www.youtube.com/watch?v=h2d9b_nEzoA
[new hash table video]: https://www.youtube.com/watch?v=tjtFkT97Xmc

[BaseCS hash tables]: https://medium.com/basecs/taking-hash-tables-off-the-shelf-139cbf4752f0
[BaseCS hash functions]: https://medium.com/basecs/hashing-out-hash-functions-ea5dd8beb4dd
[visualgo hash table]: https://visualgo.net/hashtable

[hash table starter code]: source/hashtable.py
[hash table unit tests]: source/hashtable_test.py
