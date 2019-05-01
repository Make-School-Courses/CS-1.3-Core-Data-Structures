## Start of class
- Raise hands if you completed add/remove and XX - 80% had done it.
[NOTE] Good - super easy way to get a read on the room.  

1:32 Code review with a worksheet in pairs or threes
- [SUGGESTION] - fill in one sample of the Core Data worksheet as you discuss - visual cue
- Just do top half of the worksheet - when done switch pairs

[1:58] Called on students to respond to fill in the worksheet - Implement Set using each of these four data structures (LinkedList, Dynamic Array, Sorted Array, Hash Table)
- Volunteers spoke from their seats - Alan updated the worksheet
- LinkedList:
    - add : implementation: append or prepend, time: O(1) + O(n) = O(n)
            - NOTE: must call contains first (a student caught this) since set is unique - so runtime is O(1) for add only but O(n) for contains
    - remove : implementation: traverse and delete, time: O(n)
    - contains: implementation: travers and find, time O(n)

- Dynamic Array
    - add: implementation: loop over to check if present, if not, append at end time: O(n)
[NOTE] : You / student changed the the language from traverse in LinkedList to loop over in the array - was this intentional ?
    - remove: implementation: loop over and if found, remove time: O(n)
    - contains: implementation: loop over using linear search time: O(n)
        - Note: The `in` keyword in Python is linear search


- Sorted Array
    - add: implementation: binary search to find, insert by shifting down time: binary search O(log n) + shift O(n) = O(n)
Discussion: Why is O(log n) + O(n) = O(n)? Drew graph of each on the board (and had students use their arm to show shape of log n).  Discussed that you can ignore the log n because as n gets big it doesn't contribute as much as n.
    - remove: implementation: binary search and remove via shift time: O(n)
    - contains: implementation: binary search time: O(log n)

- Hash Table
    - refresh your understanding of hash tables:
        - n=#entries
        - b=#buckets
        -l = load factor = n/b = average size of linked list in each bucket- in a resizable hash table (optimized) we can assume l is a small constant so O(1)  - if not resizable O(l)
    [ Link to Load Factor Slide ] - to refresh memory of Linear Probing and Chaining and how these work with load factor.
    -add: implementation: store element as key using .set method time:  O(1)
        - started with discussion of hash table code `hash_table.set(element,element)` - what does this do in Python - its a touple which stores (key, value) pairs not as values but as pointers so if the same value is sent for the key and value then each pointer will point to the same place. (so not much wasted space)
        - discussion: in dynamic languages like Python, and others - we often are working with pointers, not values.
    -remove: implementation:  hash to find bucket and delete on linked list in the bucket time: O(1)
    -contains: implementation: hash to find bucket and traverse linked list in the bucket time: O(1)

[2:31] Move onto the next part of the worksheet - pair up can use Hash Table implementation since as we learned int he first half of the worksheet the hash table implementation is the fastest.

[2:40] Clarified these operations use two sets so assume set 1 has size n, set two has size m and O will be in terms of m and n. EX O(mn)

[2:49] Student reviews code for hash table
- Student code
- Union
    - Used `__iter__` allows you to use an object in for loop
    - Used `yeild` - returns an item without exiting the function.  In python
        - Student question - should you use a variable in the loop instead of an expression? No, for loop optimizes to only call the expression once

- Intersection:
    - Student explained if else if flow
    - Alan - draw a picture of two overlapping sets one that is bigger - optimize code by looping through smaller one not larger (since both contain the intersection)
    - To the class: On worksheet - write the pseudocode for the student code
        - Alan: gave instructions - students: did it?
    - Complexity O(min(m,n))
    - What operations does this depend on ? (contains and add)

- Difference
    - Convention for the method `difference(self, other_set)` is to return everything in `self` that is not in the intersection.
    - Alan drew picture
    - Cannot optimize by looping over smaller set, have to loop over set that is the first argument
    - Complexity O(n) - independent of the size of the other set.

-Feedback on Student Code (Jackson):
    - Alan - how to improve code - use the `__iter__` method in the `difference` method - like he did in the union code.

[3:05 BREAK]

[3:10] Review blog posts in pairs - make sure to link to tracker.  Alan walked around to check in. Students engaged

[3:]
