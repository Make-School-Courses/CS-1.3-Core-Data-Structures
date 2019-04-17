# Class 2a: Recursion & Search Algorithms

## Topics
- Compare [iteration] and [recursion] with [factorial] function
- Search algorithms: [linear search] and [binary search]

## Learning Outcomes

By the end of this lesson, students should be able to...

1. Compare and contrast iterative and recursive implementations of a function
1. Compare and contrast linear and binary search
1. Practice algorithm analysis to find the running time of the algorithm


## Minute-by-Minute

| **Elapsed** | **Time**  | **Activity**              |
| ----------- | --------- | ------------------------- |
| 0:00        | 0:03      | Progress Tracker                |
| 0:03        | 0:02      | Factoid of the Day                  |
| 0:05        | 1:20      | Code Review + Presentations       |
| 1:25        | 0:10      | TT - Algorithm Analysis                     |
| 1:35        | 0:10      | Break      |
| 1:45        | 0:05      | Wrap up      |
| TOTAL       | 1:50      |                           |

## Progress Tracker (3 min)

- Fill out attendance, challenges completed, etc.
- Turn in Binary/Integers worksheet up at the front of class

## Factoid of the Day (2 min)

[Binary Coins from Thingiverse](https://www.thingiverse.com/thing:3512086) that represent powers of two


## Code Review + Presentations (80 min)

### Code Review in Pairs - Iterative Factorial (10 min)

- In partners, go over solutions for the Iterative Factorial coding challenge from last class
- Once each of you have discussed the problem, find a new partner, and trade approaches again to see more ways on how people went about the problem
- A few students will be chosen after to go up and present their solutions

### Code Review Presentation (15 min)

Chosen students present their solutions for Iterative Factorial

**Tips:**

- Use two variables: One to track which number in the factorial you're looking at, and one to track the factorial (product) so far
- It's important to start with 1 here, starting with 0 would screw it all up. Remember `0! = 1`
- It's important to have a starting value, whether it's multiplication (starting at 1) or addtion (starting at 0)
- Given `n` is the input number to the factorial function, you can start at `n` and move down to 1, or start from 1 and go up to `n`. Each approach is the same

### Code Review in Pairs - Recursive Linear Search (5 min)

- In partners, go over solutions for the Recursive Linear Search coding challenge from last class
- Specifically, **look at what operators you're using** - are you doing things that could potentially slow your code down? Or speed it up?
- Once each of you have discussed the problem, find a new partner, and trade approaches again to see more ways on how people went about the problem
- A few students will be chosen after to go up and present their solutions

### Code Review Presentation (15 min)

Chosen students present their solutions for Recursive Linear Search

**Tips:**

- Notice the similar structures between the recursive and iterative solutions
- Make sure you're checking for an invalid index for your array (remember this could happen both through the recursive call or through user input). Remember you need to check for _all valid array lengths_
- Remember to comment your code to make it clear!
- Can we do this without an index?
    - Yes! through array slicing: `array[1:]`
    - _But_ this is slow. Given `n` is the length of the array, it takes `n-1` steps to copy the array. Since this operation takes linear time, and we would have to call this operation a linear number of times, the algorithm would have a runtime of **n<sup>2</sup>**. Yikes!
    - **Avoid slice operators for recursive code**. You run the risk of becoming [accidently quadratic](https://accidentallyquadratic.tumblr.com/)


### Code Review in Pairs - Recursive/Iterative Binary Search (15 min)

- In _new_ partners from the previous two code reviews, go over solutions for the Recursive/Iterative Binary Search coding challenge from last class
- Once each of you have discussed the problem, find a new partner, and trade approaches again to see more ways on how people went about the problem
- A few students will be chosen after to go up and present their solutions

### Code Review Presentation - Iterative Binary Search (10 min)

Chosen students present their solutions for Iterative Binary Search

**Tips:**

- Using multiple indexes (i.e. `left` starting at the beginning of the array, `right` starting at the end) is fine, but once they _meet or cross over_, some action should take place
- Once an item in the array has been checked to see if it matches, you shouldn't search over that item again
- What do you return if you _can't_ find the item?
- Make sure you are guaranteed an _integer_ value when finding the median in the array


### Code Review Presentation - Recursive Binary Search (10 min)

Chosen students present their solutions for Iterative Binary Search

**Tips:**

- If you can't calculate the value of a parameter in the function definition, set it to `none`, and then calculate it in the function when you have access to what you need
- The iterative solution's looping conditional _should be the same_ as the base case of recursive solution
- Compare your iterative/recursive solutions and see where they're the same or differ
    - Almost every line of code can be matched between the two algorithms
    - The loop in the iterative solution iterative will be called the same number of times as the number of recursive calls in the recursives solution
    - **Runtime should not differ here for this function**

## TT - Algorithm Analysis (10 min)

![linear vs binary search](assets/binary-and-linear-search-animations.gif)

Credit to [Mathwarehouse](https://www.mathwarehouse.com/programming/gifs/binary-vs-linear-search.php) for the animation!

### Linear Search

- **Best case:** The item we're looking for is the first one in the list: `O(1)`
    - Contant time since we only have to do 1 operation regardless of the length of the list
- **Worst case:** The item we're looking for is at the end of the list: `O(n)`
    - Where `n` is the number of items in the array
    - Linear time since we may have to search the length of the list to find the item.
- This is why it is called _linear_ search. It takes _linear_ time!
- You don't need to make any assumptions about the input: sorted and unsorted both have the same runtime
- This is slower though than other algorithms

### Binary Search

- **Best case:** The item we're looking for is exactly in the middle: `O(1)`
    - Never examine data, just checked the middle and found it
    -  `O(1)` space too, since it's just local variables
- **Worst case:** The item we're looking for is first, last, or one off from the median in the array: Given `n` is the length of the input array, `O(log(n))`
    - We're _splitting the array in half_ each time until we have 1 item.
    - **If you double the length of the array, in the worst case, you only increase the number of steps it takes to find the item by one**
        - i.e. a 7 item array takes at most 3 steps to find the item. A 14 item array would take at most 4 steps (try it out yourself!)
- This algorithm runs _really_ fast, but only works if the array is _sorted_

### Graph It

- Binary search has _constant run-time operations_ for checking for the target item and changing pointers
- Given `n` is the length of the array, our range of items that we're searching through goes from `n` --> `n/2` --> `n/4` --> ... 1
    - i.e. for a 7 item list, our number of items that we need to look through goes from 7 --> 3 --> 1
- This follows the **log function**
    - This is a slow growing function because we are _dividing by two_ as we grow
- Exponent and log are **inverses** of each other - exponent is fast growing (doubles), log is slow growing (halves)

See the graph below to compare exponent, linear, and log:

![graph](assets/algorithm_graphs.jpg)

## Break (10 min)

## Wrap Up (5 min)

Go over what the challenges for next class, and allow for clarifying questions
