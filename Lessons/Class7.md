# Class 7: Sets & Circular Buffers

## Learning Objectives

By this end of this lesson, students should be able to...

1. Explain what a set is and what some varitions of a set are, such as a multiset
1. Explain other types of queues such as a circuluar buffer
1. Practice implementing more abstract data types backed by a data structure of their choice

## Topics
- Abstract data types: [set], [multiset (bag)][multiset]
- Concrete data structures: [hash table], [circular buffer (circular queue, ring buffer)][circular buffer]
- [Set operations]

## Resources
- Read Vaidehi Joshi's [article on sets and their use in databases][BaseCS sets] with beautiful drawings and excellent examples

## Challenges
- Implement `Set` class (abstract data type backed by data structure of your choice) with the following [set operations] as instance methods and properties:
    - `__init__(elements=None)` - initialize a new empty set structure, and add each element if a sequence is given
    - `size` - property that tracks the number of elements in constant time
    - `contains(element)` - return a boolean indicating whether `element` is in this set
    - `add(element)` - add `element` to this set, if not present already
    - `remove(element)` - remove `element` from this set, if present, or else raise `KeyError`
    - `union(other_set)` - return a new set that is the union of this set and `other_set`
    - `intersection(other_set)` - return a new set that is the intersection of this set and `other_set`
    - `difference(other_set)` - return a new set that is the difference of this set and `other_set`
    - `is_subset(other_set)` - return a boolean indicating whether `other_set` is a subset of this set
- Write unit tests to ensure the `Set` class is robust
    - Include test cases for each class instance method
- Annotate all instance methods with complexity analysis of running time and space (memory)
- Compare the behaviors of your `Set` class to those of the [Python `set` type] and [Swift `Set` type]

## Stretch Challenges
- Implement `CircularBuffer` class (backed by dynamic array) with the following instance methods and properties:
    - `__init__(max_size)` - initialize a new circular buffer that can store at most `max_size` items
    - `size` - property that tracks the number of items in the buffer
    - `is_empty` - check if the buffer is empty
    - `is_full` - check if the buffer is full
    - `enqueue(item)` - insert `item` at the back of the buffer
    - `front` - return the item at the front of the buffer
    - `dequeue` - remove and return the item at the front of the buffer
- Annotate `enqueue` and `dequeue` methods with running time complexity analysis
- Write unit tests to ensure the `CircularBuffer` class is robust
    - Include test cases for each class instance method and property
- Annotate `enqueue` and `dequeue` methods with running time complexity analysis


<!--## Minute-by-Minute

| **Elapsed** | **Time**  | **Activity**              |
| ----------- | --------- | ------------------------- |
| 0:00        | 0:35      | Activity - Drawing a Hashtable                |
| 0:35        | 0:45      | Code Review                  |
| 1:20        | 0:10      | Break       |
| 1:30        | 0:20      | TT - Sets                     |
| TOTAL       | 1:50      |                           |-->

## Break (10 min)

- Check out [accidently quadratic!](https://accidentallyquadratic.tumblr.com/post/153545455987/rust-hash-iteration-reinsertion)

## TT - Sets (20 min)

A **Set** is an abstract data type. It is an unordered collection (just like a map) but it only has individual items (no key/value pairs). We call these items **elements**

**Example Use Case**: find if a student is in a class (is this particular student element in the set or not)

But what if we want to know if a student is in two classes? We can use a set operation called **intersection**. Think of an intersection as like using an `and` operator. The below **Venn Diagram** illustrates this intersection:

![venn_intersect](assets/venn_intersect.png)

[Venn diagrams](https://en.wikipedia.org/wiki/Venn_diagram) are going to be super helpful for understanding sets.

### Set Operations

![venn-operations](assets/venn_operations.png)

There are other operations we can use to compare multiple sets:

- **Union** - consists of all elements in sets. Think of a union as like using an `or` operator
- **Symmetric Difference** - Items are in one set or the other, but not both. Think of a symmetric difference as like using an `exclusive or` (`XOR`)
    - `symmetric difference = union - intersection`

All of these methods can be used in [python](https://docs.python.org/3/library/stdtypes.html#set), [Swift](https://developer.apple.com/library/content/documentation/Swift/), and [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set) too!

### Set Terminology

- **Subset** - one set is _contained_ within the other
- **Superset** - opposite of a subset, one set is _containing_ another set (or multiple)
- **Disjoint** - two sets that don't share any elements at all
- **`frozenSet`** - an immutable set in python. It can only be created once, and then can no longer be edited, unlike a regular set where you can add/delete from it at any time

### Implementing Sets

Sets are _not_ hashable, but _elements we put in the sets can be hashable_

- We would do this if we want to look up an element using its hashcode!

Therefore, we could use a **hashtable** to implement a set. However, we could also use arrays, or linked lists if you don't need elements to be hashable.

## For Homework

- Read the [set theory article](https://medium.com/basecs/set-theory-the-method-to-database-madness-5ec4b4f05d79) (also linked in resources)
- Do the `Set` challenges (should have at least `contains`, `add`, `remove`, and one of the methods that use a `set` as an input by next class)
- Write unit tests for your challenges (write the first few before you begin the challenges)
    - Review past unit tests for previous challenges to see how to write them

[set]: https://en.wikipedia.org/wiki/Set_(abstract_data_type)
[multiset]: https://en.wikipedia.org/wiki/Set_(abstract_data_type)#Multiset
[set operations]: https://en.wikipedia.org/wiki/Set_(abstract_data_type)#Operations
[hash table]: https://en.wikipedia.org/wiki/Hash_table
[circular buffer]: https://en.wikipedia.org/wiki/Circular_buffer

[BaseCS sets]: https://medium.com/basecs/set-theory-the-method-to-database-madness-5ec4b4f05d79
[Python `set` type]: https://docs.python.org/3/library/stdtypes.html#set
[Swift `Set` type]: https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/CollectionTypes.html#//apple_ref/doc/uid/TP40014097-CH8-ID484
