# Google Goals
One of the things on my impossible list is to work at Google as a Software Engineer. And of course, in order to achieve this goal, I have to improve my skill set. I found a Google Interview study plan on [Github](https://github.com/xiewenya/google-interview-university) and I'll be following this to start off my review.
# Algorithmic complexity

> Algorithmic complexity is concerned about how fast or slow particular algorithm performs.

[Source](https://www.cs.cmu.edu/~adamchik/15-121/lectures/Algorithmic%20Complexity/complexity.html)

Algorithmic complexity describes the efficiency, or how fast or slow a particular algorithm performs. This analyzes how fast a program's run time grows asymptotically. 

### Best Case, Worst Case and Expected Case



### Asymptotic Notations

In order to represent the time function, we use the **big-O** notation. Big O time is the language and metric we use to describe the efficiency of algorithms. [*](http://www.crackingthecodinginterview.com/) 

**Big O** - Upper bound on the time

It is a function whose curve on a graph, at least after a certain point on the x-axis (input size), will always be higher on the y-axis(time) than the curve of the run time. [*](https://medium.com/@.RT/total-n00bs-guide-to-big-o-big-%CF%89-big-%CE%B8-aa259ae8a1c2) 

Meaning, that the run time of an algorithm will be *at least as fast* as the denoted big O. This has a *less-than-or-equal-to* relationship. This denotes the slowest possible running time.

**Big Ω** - Lower bound of time

Big omega is the inverse of big O. This denotes the fastest possible running time of an algorithm. A function will never perform faster than its big omega.

**Big θ** - Tight bound on run time

A function is bit theta of another if and only if that function is both Big O and Big Omega of it. 



Suppose you are to count how many characters there are in the string "cat". The simplest way is by going through letter by letter and adding one to the counter for each character. This method is said to run in **linear time** with respect to the number of characters. For the string "cat", number of characters *n* = 3. It will take O(n) or O(3) which means that the time required to traverse the string is proportional to the number of characters. [*](https://www.youtube.com/watch?v=iOq5kSKqeR4)