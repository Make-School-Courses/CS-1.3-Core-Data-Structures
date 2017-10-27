## Class 3: String Algorithms

### Topics
- [Palindromes]: strings that read the same forwards and backwards, ignoring punctuation, whitespace, and letter casing
- [String searching]: find occurrences of a pattern in a longer string of text
- [Permutation]: arrangement of all items in a set into a sequence or order
- [Anagrams]: permutations of words or phrases that produce another word
- [Unit testing]: testing code in isolation using repeatable test cases with known results

### Resources
- Read Stack Overflow's answers to the question "[What is unit testing?]"
- Read The Hitchhiker's Guide to Python's tutorial on [testing your code]
- Consult documentation for Python's [`unittest` module] and [`pytest` tool]
- Play around with Wordsmith's [Internet Anagram Server]

### Challenges
- Implement palindrome checking functions using [palindromes starter code]:
    - Implement `is_palindrome_iterative` - iterative version of `is_palindrome`
    - Implement `is_palindrome_recursive` - recursive version of `is_palindrome`
    - Run `python palindromes.py string1 string2 ... stringN` to test `is_palindrome`
        - Example: `python palindromes.py ABC noon RaceCar 'Taco, Cat'` gives the result:
        > `FAIL: 'ABC' is not a palindrome`<br/>
        > `PASS: 'noon' is a palindrome`<br/>
        > `PASS: 'RaceCar' is a palindrome`<br/>
        > `PASS: 'Taco, Cat' is a palindrome`<br/>
    - Run `pytest test_palindromes.py` to run the [palindromes unit tests] and fix any failures
- Implement string searching functions (try both iterative and recursive versions):
    - Implement `contains(string, pattern)` - a boolean indicating whether `string` contains all of `pattern`
    - Implement `find_index(string, pattern)` - the starting index of the first occurrence of `pattern` in `string`
    - Implement `find_all_indexes(string, pattern)` - a list of the starting indexes of all occurrences of `pattern` in `string`
- Write your own unit tests to ensure your string searching algorithms are robust
    - Include several test cases that are both positive (examples) and negative (counterexamples)
- Refactor functions to increase code reuse and avoid duplication ([DRY principle])
- Annotate functions with complexity analysis of running time and space (memory)

### Stretch Challenges
- Implement permutation generating functions (try both iterative and recursive versions)
- Implement anagram generating functions (try both iterative and recursive versions)
    - *Hint:* Use the Unix dictionary words list located at: `/usr/share/dict/words`


[unit testing]: https://en.wikipedia.org/wiki/Unit_testing
[`unittest` module]: https://docs.python.org/3/library/unittest.html
[`pytest` tool]: http://docs.pytest.org/en/latest/
[what is unit testing?]: http://stackoverflow.com/questions/1383/what-is-unit-testing
[testing your code]: http://docs.python-guide.org/en/latest/writing/tests/
[DRY principle]: https://en.wikipedia.org/wiki/Don%27t_repeat_yourself

[string searching]: https://en.wikipedia.org/wiki/String_searching_algorithm
[palindromes]: https://en.wikipedia.org/wiki/Palindrome
[permutation]: https://en.wikipedia.org/wiki/Permutation
[anagrams]: https://en.wikipedia.org/wiki/Anagram
[Internet Anagram Server]: http://www.wordsmith.org/anagram/

[palindromes starter code]: source/palindromes.py
[palindromes unit tests]: source/test_palindromes.py
