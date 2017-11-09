## Class 7: Sets & Circular Buffers

### Topics
- Abstract data types: [set], [multiset (bag)][multiset]
- Concrete data structures: [hash table], [circular buffer (circular queue, ring buffer)][circular buffer]
- [Set operations]

### Challenges
- Implement `Set` class (set with hash table) with the following [set operations] as instance methods and properties:
    - `__init__(elements=None)` - initialize a new empty set structure, and add each element if a sequence is given
    - `size` - property that tracks the number of elements in constant time
    - `contains(element)` - return a boolean indicating whether `element` is in this set
    - `add(element)` - add `element` to this set, if not present already
    - `remove(element)` - remove `element` from this set, if present, or else raise `KeyError`
    - `union(other_set)` - return a new set that is the union of this set and `other_set`
    - `intersection(other_set)` - return a new set that is the intersection of this set and `other_set`
    - `difference(other_set)` - return a new set that is the difference of this set and `other_set`
    - `is_subset(other_set)` - return a boolean indicating whether `other_set` is a subset of this set
- Write unit tests for to ensure the `Set` class is robust
    - Include test cases for each class instance method
- Annotate all instance methods with complexity analysis of running time and space (memory)
- Compare the behaviors of your `Set` class to those of the [Python `set` type]

### Stretch Challenges
- Implement `CircularBuffer` class with dynamic array
- Write unit tests for to ensure the `CircularBuffer` class is robust
    - Include test cases for each class instance method
- Annotate `enqueue` and `dequeue` methods with running time complexity analysis


[set]: https://en.wikipedia.org/wiki/Set_(abstract_data_type)
[multiset]: https://en.wikipedia.org/wiki/Set_(abstract_data_type)#Multiset
[set operations]: https://en.wikipedia.org/wiki/Set_(abstract_data_type)#Operations
[hash table]: https://en.wikipedia.org/wiki/Hash_table
[circular buffer]: https://en.wikipedia.org/wiki/Circular_buffer
[Python `set` type]: https://docs.python.org/3/library/stdtypes.html#set
