# Class 2: Recursion & Search Algorithms

## Topics
- Compare [iteration] and [recursion] with [factorial] function
- Search algorithms: [linear search] and [binary search]

## Learning Objectives

By the end of this lesson, students should be able to...

1. Compare and contrast iterative and recursive implementations of a function
1. Compre and contrast linear and binary search
1. Practice algorithm analysis to find the running time of the algorithm

## Minute-by-Minute

| **Elapsed** | **Time**  | **Activity**              |
| ----------- | --------- | ------------------------- |
| 0:00        | 0:05      | Progress Tracker                |
| 0:05        | 0:10      | Factoid of the Day                  |
| 0:15        | 0:25      | Code Review in Pairs       |
| 0:40        | 0:30      | Code Review Presentation       |
| 1:10        | 0:05      | BREAK       |
| 1:20        | 0:25      | Card Sorting Activity       |
| 1:45        | 0:10      | TT - Recursion       |
| 1:55        | 0:04      | Recursive Binary Search Card Activity       |
| 1:59        | 0:01      | Wrap up       |
| TOTAL       | 2:00      |                           |

## Progress Tracker (5 min)

Fill out attendance, challenges completed, etc.

## Factoid of the Day (10 min)

There's a secret hexagram code known as [I Ching](https://en.wikipedia.org/wiki/I_Ching#Hexagrams). Here's an example of it:

![i-ching-secret](assets/i-ching-secret-code.png)

**Find out what this secret code means**

Tips

- There's 64 characters that make up this code. Why 64?
    - Demonstrate on the whiteboard that for every bar (x) that you add, you get 2^x possible combinations
    - Binary and the Ching code can be seen as the same representation!
    - This means with 6 bars, we can represent 64 numbers!

## Code Review in Pairs (25 min)

- In groups of 2-3, go over solutions for the Decode and Encode coding challenges from last class
- A few students will be chosen after to go up and present their solutions

## Code Review Presentation (30 min)

- Chosen students present their solutions for Decode and Encode 
- After presenting, the instructor goes over the solution in detail on a white board

**Tip:** Make a table to help walk through iterations of a for loop. This can help with mapping out predictions of what you expect the code to output.

## Break (5 min)

## Card Sorting Activity (25 min)

### Linear Search - "Special" sort

- Get into pairs, each pair should have a stack of cards. No computers!
    - Each deck should be pre-sorted by the instructor such that it takes 3-5 flips per pair to find their card
- Each deck should have exactly 8 cards with 1 duplicate. Pull out the duplicate, this will be the **target card**
- That one duplicate is the card you're going to be searching for
- Leave cards face down in a row, with the duplicate target card face up and off to the side.
- Pick face down cards one at a time, if it matches the target, you're done, if not, put it face down and then move onto the next one
- Note how many times you had to flip cards to find your target card

### Unsorted Linear Search

- Shuffle the deck, and now do the same exercise you just did
- Note how many times you had to flip cards to find your target card
- Reshuffle and do this one more time, noting the number of flips again

### Compare Results

- The worst case for number of flips is 7, since the card you were looking for could be the last one you flip
- When the decks were strategically sorted by the instructor, everyone gets aorund 3-5 flips
- When the decks were unsorted, it could take anywhere between 1-7 flips to find your card!
- Either way, **when we do linear search, we are always scanning from left to right**
- If the cards were truly sorted without strategic instructor tampering....could we do better?

### Phone Book Search

- Imagine you have a phone book, but it has no table of contents. It's in alphabetial order, but you have no idea where the "M's" start or end, and you're looking for the name McGregor
- Since you know it's in alphabetical order, one strategy could be:
    - Open to the middle of the book
    - From there, flip to the left or right depending on what letter you land on.
        - i.e. if you open up to the "K's", you know that "M" appears later, so you can flip to the right and ignore any pages to the left of the "K" page that you opened to.

### Phone Books and Cards

- Sort the cards lowest to highest and put them face down in a row
- Work with your partner for 2-3 minutes on this, and try the phone book strategy with your face-down, sorted cards
- Everyone should take _no more than 3 steps_ to find their card!
- This technique is known as **binary search**

### Binary Search

- The "phone book search" we just discussed is actually **binary search!**
- At a high level, the algorithm does the following, given an array and a target value:
    - Looks at the middle item (let's call it "mid") of the array, and decides if mid is equal to, less than, or greater than the target value
    - If it's equal, we're done, we've found it!
    - If it's less than the target value, we can ignore all items to the right of mid, and we can now look at all items in between the first item of the array and mid-1. From here, we start the algorithm over
    - If it's greater than the target value, we can ignore all items to the left of mid, and we can now look at all items in between the mid+1 and the last item in the array. From here, we start the algorithm over
- This is pretty small stakes with 7 cards and 1 target, but imagine Facebook with 1 billion people and trying to find 1 person. **With binary search, can do this in 32 steps in the worst case!**
    - We will analyze this in detail and write code for it in a future class!

**Two important notes on binary search:**

1. The array MUST be sorted
1. You must be able to compare items in the aray to establish which have "lesser" and "greater" values

## TT - Recursion (6 min)

### Factorial Definition on the Whiteboard

- A **factorial** is when a given number is multiplied by each number less than it. Use the "!" symbol to represent a factorial
    - i.e. 4! = 4 * 3 * 2 * 1 = 24
- Draw out 5! through 2!, what is the pattern seen?
    - 5! = 5 * 4! = 5 * 4 * 3! = 5 * 4 * 3 * 2! = 5 * 4 * 3 * 2 * 1! = 5 * 4 * 3 * 2 * 1
    - 0! = 1
    - **n! = n * (n-1) * )n-2) * ... * 2 * 1**
- **You can define factorials in terms of each other!**
- Factorial can be written recursively based on this principle:

```python
def factorial(n):
    if n == 1:
        return 1
    else:
        f = factorial(n-1)
        return n*f
```

**Think of recursion as only doing one thing yourself, and then passing the buck**

## Recursive Binary Search Card Activity (3 min)

- Sort your deck of cards again as you did before.
- Now you pick up one card. If you didn't find your target card, communicate what the other person has to do given what you found (i.e. do they search the first or second half of the deck?)
- Next the other person does the same, and the roles keep switching until the card is found

## Wrap up (1 min)

Overview of challenges to work on for next class session

## Resources
- Review Make School's [algorithm analysis slides]
- Read Vaidehi Joshi's [article on logarithms, binary search, and big O notation][BaseCS logarithms] with excellent, beautiful drawings
- Read Interview Cake's [article on logarithms and binary search][logarithms article]
- Read Interview Cake's [article on the idea behind big O notation][IC big O]
- Read Stack Overflow's [plain English explanations of big O notation][SO big O]
- Read Justin Abrams's [article on big O notation explained by a self-taught programmer][JA big O]
- Watch HackerRank's [recursive algorithms video], [binary search algorithm video], and [big O notation video]
- Watch Harvard's [old recursion video], [new recursion video], [stack frames video], [linear search video], [binary search video], [asymptotic notation video], and [computational complexity video]

### Challenges
- Implement iterative [factorial] function using [recursion starter code]:
    - Implement `factorial(n)` - the product of all integers 1 through `n`
    - Run `python recursion.py number` to test `factorial` on a number
        - Example: `python recursion.py 8` gives the result `factorial(8) => 40320`
    - Run `pytest recursion_test.py` to run the [recursion unit tests] and fix any failures
- Implement recursive linear and binary search algorithms using [search starter code]:
    - Implement `linear_search(array, item)` - the first index of `item` in `array`
    - Implement `binary_search(array, item)` - the index of `item` in sorted `array`
    - Run `pytest search_test.py` to run the [search unit tests] and fix any failures
- Annotate functions with complexity analysis of running time and space (memory)

## Stretch Challenges
- Implement recursive [permutation] and [combination] functions
- Make these functions efficient by avoiding repeated subproblems
- Write your own unit tests to ensure your algorithms are robust


[iteration]: https://en.wikipedia.org/wiki/Iteration
[recursion]: https://en.wikipedia.org/wiki/Recursion_(computer_science)
[factorial]: https://en.wikipedia.org/wiki/Factorial
[linear search]: https://en.wikipedia.org/wiki/Linear_search
[binary search]: https://en.wikipedia.org/wiki/Binary_search_algorithm
[permutation]: https://en.wikipedia.org/wiki/Permutation
[combination]: https://en.wikipedia.org/wiki/Combination

[logarithms article]: slides/Logarithms.pdf
[algorithm analysis slides]: slides/AlgorithmAnalysis.pdf
[big O notation video]: https://www.youtube.com/watch?v=v4cd1O4zkGw
[asymptotic notation video]: https://www.youtube.com/watch?v=iOq5kSKqeR4
[computational complexity video]: https://www.youtube.com/watch?v=IM9sHGlYV5A

[recursive algorithms video]: https://www.youtube.com/watch?v=KEEKn7Me-ms
[old recursion video]: https://www.youtube.com/watch?v=t4MSwiqfLaY
[new recursion video]: https://www.youtube.com/watch?v=VrrnjYgDBEk
[stack frames video]: https://www.youtube.com/watch?v=beqqGIdabrE

[linear search video]: https://www.youtube.com/watch?v=vZWfKBdSgXI
[binary search video]: https://www.youtube.com/watch?v=5xlIPT1FRcA
[binary search algorithm video]: https://www.youtube.com/watch?v=P3YID7liBug

[BaseCS logarithms]: https://medium.com/basecs/looking-for-the-logic-behind-logarithms-9e79d7666dda
[IC logarithms]: https://www.interviewcake.com/article/python/logarithms
[IC big O]: https://www.interviewcake.com/article/python/big-o-notation-time-and-space-complexity
[SO big O]: https://stackoverflow.com/questions/487258/what-is-a-plain-english-explanation-of-big-o-notation
[JA big O]: https://justin.abrah.ms/computer-science/big-o-notation-explained.html

[recursion starter code]: source/recursion.py
[recursion unit tests]: source/recursion_test.py
[search starter code]: source/search.py
[search unit tests]: source/search_test.py
