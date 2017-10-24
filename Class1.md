## Class 1: Number Bases

### Topics
- number bases: [decimal], [binary], [hexadecimal]
- [signed number representations]: signed magnitude, [ones' complement], [two's complement]

### Resources
- review Make School's [slides on number bases][number bases slides]
- read BetterExplained's [article on number systems and bases][number bases article]
- play with Dan Wolff's live-updating [base conversion calculator]
- review Wikipedia's [comparison table] of signed number representations
- print and make a [Flippy Do] binary converter following Code.org's [instructions][Flippy Do instructions]

### Challenges
- practice binary and hexadecimal conversions on [number bases worksheet]
- implement base conversion functions for unsigned numbers using [starter code]:
    - implement `decode` - decode digits in any base to a number
    - implement `encode` - encode a number to digits in any base
    - implement `convert` - convert digits in any base to digits in any base
    - run `python bases.py number base1 base2` to test `convert` on `number`
        - example: `python bases.py 42 10 2` should give the result `101010`
    - run `pytest bases_test.py` to run the [unit tests] and fix any failures
    - write additional unit tests to ensure your conversion algorithms are robust

### Stretch Challenges
- implement base conversion for fractional numbers using a [radix point] (try playing with the [base conversion calculator] to see how this works)
- implement base conversion for negative binary numbers (using [two's complement])


[decimal]: https://en.wikipedia.org/wiki/Decimal
[binary]: https://en.wikipedia.org/wiki/Binary_number
[hexadecimal]: https://en.wikipedia.org/wiki/Hexadecimal
[signed number representations]: https://en.wikipedia.org/wiki/Signed_number_representations
[comparison table]: https://en.wikipedia.org/wiki/Signed_number_representations#Comparison_table
[ones' complement]: https://en.wikipedia.org/wiki/Ones%27_complement
[two's complement]: https://en.wikipedia.org/wiki/Two%27s_complement
[radix point]: https://en.wikipedia.org/wiki/Radix_point

[number bases slides]: slides/NumberBases.pdf
[number bases worksheet]: slides/NumberBasesWorksheet.pdf
[number bases article]: https://betterexplained.com/articles/numbers-and-bases/
[base conversion calculator]: https://baseconvert.com/
[Flippy Do]: https://drive.google.com/file/d/0B6iNirqJ5EuVVTlla0RpR2RIa2s/view
[Flippy Do instructions]: https://docs.google.com/document/d/1QnD9khmPUz1az3ZLc5L8vavR6lU0uScspotRhORnHxE/edit

[starter code]: source/bases.py
[unit tests]: source/bases_test.py
