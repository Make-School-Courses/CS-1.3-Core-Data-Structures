## Class 11: Iterative Sorting Algorithms

### Topics
- Algorithm to check if items in a list are in sorted order
- Counting how many [inversions] there are in a list
[inversions]: https://en.wikipedia.org/wiki/Inversion_(discrete_mathematics)
- Classic iterative [sorting algorithms]: [bubble sort], [selection sort], [insertion sort]

### Resources
- Play with VisuAlgo's [interactive sorting visualizations][VisuAlgo sorting] including bubble, selection, and insertion sort
- Play with USF's [interactive sorting animations][USF sorting] including bubble, selection, insertion, and Shell sort
- Watch Toptal's [sorting animations] to see how algorithms compare based on input data and read the discussion section
- Watch videos to observe patterns: [9 sorting algorithms], [15 sorting algorithms], [23 sorting algorithms]
- Watch Barack Obama's answer to a [Google interview question on how to sort one million 32-bit integers][Obama sorting question]

### Challenges
- Implement these classic iterative sorting functions using [sorting starter code]:
    - `is_sorted(items)` - return a boolean indicating whether all `items` are in ascending order
    - `bubble_sort(items)` - swap adjacent items that are out of order, repeat until all `items` are sorted
    - `selection_sort(items)` - find minimum item in unsorted `items`, swap it with first unsorted item, repeat until all `items` are sorted
    - `insertion_sort(items)` - take first unsorted item, insert it in sorted order in front of `items`, repeat until all `items` are sorted
- Annotate functions with complexity analysis of running time (operations) and space (memory usage)
- Write a thorough suite of [sorting unit tests] to ensure your sorting algorithms are robust
    - Write tests in a way that lets you add new sorting functions without needing to write more tests
    - Include a variety of test cases that cover many different input types, orderings, and distributions

### Stretch Challenges
- Extend sorting algorithms with an `order` parameter to specify ascending or descending order
- Extend sorting algorithms with a `key` parameter to specify a function to call on each item when making comparisons (read about Python's [`sorted` function] and how to use [`key` functions] for more information)
- Implement an insertion sort variation using binary search to find the position to insert each item
- Implement improved iterative sorting algorithms: [cocktail shaker sort], [library sort], or [Shell sort]
- Annotate functions with complexity analysis of running time (operations) and space (memory usage)


[sorting algorithms]: https://en.wikipedia.org/wiki/Sorting_algorithm
[comparison sorting]: https://en.wikipedia.org/wiki/Comparison_sort
[bubble sort]: https://en.wikipedia.org/wiki/Bubble_sort
[selection sort]: https://en.wikipedia.org/wiki/Selection_sort
[insertion sort]: https://en.wikipedia.org/wiki/Insertion_sort

[cocktail shaker sort]: https://en.wikipedia.org/wiki/Cocktail_shaker_sort
[library sort]: https://en.wikipedia.org/wiki/Library_sort
[Shell sort]: https://en.wikipedia.org/wiki/Shellsort
[`sorted` function]: https://docs.python.org/3/library/functions.html#sorted
[`key` functions]: https://docs.python.org/3/howto/sorting.html#key-functions

[VisuAlgo sorting]: https://visualgo.net/en/sorting
[USF sorting]: https://www.cs.usfca.edu/~galles/visualization/ComparisonSort.html
[sorting animations]: https://www.toptal.com/developers/sorting-algorithms/
[3 sorting algorithms]: https://www.youtube.com/watch?v=jHPexHsDxwQ
[9 sorting algorithms]: https://www.youtube.com/watch?v=ZZuD6iUe3Pc
[15 sorting algorithms]: https://www.youtube.com/watch?v=kPRA0W1kECg
[23 sorting algorithms]: https://www.youtube.com/watch?v=rqI6KT6cOas
[Obama sorting question]: https://www.youtube.com/watch?v=k4RRi_ntQc8

[sorting starter code]: source/sorting.py
[sorting unit tests]: source/sorting_test.py
