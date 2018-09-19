# Google Goals
One of the things on my impossible list is to work at Google as a Software Engineer. And of course, in order to achieve this goal, I have to improve my skill set. I found a Google Interview study plan on [Github](https://github.com/xiewenya/google-interview-university) and I'll be following this to start off my review.

These review notes are compiled from various sources which will be indicated with asterisk marks (*). The main companion I am using is the [Cracking the Coding Interview](http://www.crackingthecodinginterview.com) book by Gayle Laakmann McDowell and other sources over the internet. I do not take credit to any of their work. Some explanations may come from my personal understanding so, if any information is incorrect, please do let me know!

# Algorithmic complexity

> Algorithmic complexity is concerned about how fast or slow particular algorithm performs.  
[Source](https://www.cs.cmu.edu/~adamchik/15-121/lectures/Algorithmic%20Complexity/complexity.html)

Algorithmic complexity describes the efficiency, or how fast or slow a particular algorithm performs. This analyzes how fast a program's run time grows asymptotically.

To give you an idea of what we are measuring, imagine a data transfer through electronic transfer and airplane transfer. [*](https://www.youtube.com/watch?v=v4cd1O4zkGw)

**Electronic Transfer O(n)** would depend on how large the data, represented by _n_,is.  The larger the size n is, the longer it would take for the data to transfer.

Let's say that the data is stored in a physical storage device and **transferred by plane**, it would take the same time to transfer it no matter how large the data is on the device. This means that the transfer is constant O(1).

Figure 1

where x is size and y is time

### Best Case, Worst Case and Expected Case
We measure the run time of an algorithm by counting the number of steps it takes to complete an operation. [*](http://www3.cs.stonybrook.edu/~algorith/video-lectures/2007/lecture2.pdf)

**Worst Case Complexity** of an algorithm is the function defined by the **maximum** number of steps taken on any instance size _n_

**Best Case Complexity** of an algorithm is the function defined by the **minimum** number of steps

**Average Case Complexity** of an algorithm is the function defined by the **average** number of steps

Since it is hard to measure the exact complexity of an algorithm, _upper and lower bounds_ of a function is used. This is called the Asymptotic Notations.

### Asymptotic Notations
In order to represent the time function, we use the **big-O** notation. Big O time is the language and metric we use to describe the efficiency of algorithms. [*](http://www.crackingthecodinginterview.com/)

**Big O** - Upper bound of the time

It is a function whose curve on a graph, at least after a certain point on the x-axis (input size), will always be higher on the y-axis(time) than the curve of the run time. [*](https://medium.com/@.RT/total-n00bs-guide-to-big-o-big-%CF%89-big-%CE%B8-aa259ae8a1c2)

Meaning, that the run time of an algorithm will be _at least as fast_ as the denoted big O. This has a _less-than-or-equal-to_ relationship. This denotes the slowest possible running time.

**Big Ω** - Lower bound of time

Big omega is the inverse of big O. This denotes the fastest possible running time of an algorithm. A function will never perform faster than its big omega.

**Big θ** - Tight bound on run time

A function is bit theta of another if and only if that function is both Big O and Big Omega of it.

### How to Calculate Big O
For example, we have an array of elements [*](https://stackoverflow.com/a/3368)

`int array[n];`

And we want to access the first element from this array. This would take constant time O(1) since no matter how big the array is, it always takes the same constant time to get the first item.

`x = array[0];`

Now, for example, we want to display all the numbers in the given array:

```java
for(int i = 0; i < n; i++){
    System.out.println(array[i]);
}
```

The time it takes to display all the elements on the array would depend on the number of elements. This means that if an array has ten elements, it would take O(n = 10) or O(n).

### Basic Rules
**Multi-part Algorithms**

When dealing with multiple loops, it is easy to confuse whether to multiply or add the runtimes of these loops.

When your algorithm is in forms of "do this _and then_ do that", you **add the run times.** The following algorithm shows that the run time is O(A + B). Adding the run time for array A and array B.

```java
for(int i = 0; i < sizeA; i++){
	System.out.println(arrayA[i]);
}
for(int i = 0; i < sizeB; i++){
	System.out.println(arrayB[i]);
}
```

However, if your algorithm is in forms of "do this _for each_ time you do that", you **multiply the runtimes.** The following algorithm shows that, for every element in array A, you must also get the value of each element of B. This results to a runtime of O(A * B).

```java
for(int i = 0; i < sizeA; i++){
    for(int j = 0; j < sizeB; j++){
		System.out.println(arrayA[i] + ", " + arrayB[j]);
    }
}
```

**Drop the Constants**

Some other rules show that constants in runtimes must be omitted. This is because multiplying a function by a constant only influences its growth rate by a constant amount, so linear functions still grow linearly, logarithmic functions still grow logarithmically, exponential functions still grow exponentially and so on. [*](https://stackoverflow.com/a/22188943)

The following code shows O(2N) runtime but given the rule to drop the constants, O(N) is the actual runtime.

```java
for(int i = 0; i < n; i++){
    for (int j = 0; j < n; j++){
        System.out.println(i + " " + j);
    }
}
```

**Drop the Non-Dominant Terms**

As mentioned earlier, when getting the Big O notation of an algorithm, we are concerned about the upper bound of the time. Hence, when we encounter cases such as O(N + log N), we omit log N because it grows more slowly than N. See Order of Growth to see comparisons of each notation.

### Order of Growth
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

**Constant O(1)**
	* Computes in constant time

**Logarithmic O(log n)**
	* Time increases in logarithmic proportion to input
	* Considered a divide and conquer algorithm
	* When you see a problem where the number of elements in the problem space gets halved each time
	* One good example of logarithmic runtime is the binary search [*](http://www.crackingthecodinginterview.com).

**Quadratic O(n<sup>2</sup>)**
	* Time increases exponentially in proportion to inputs

**Base 2 Exponential O(2<sup>n</sup>)**
	* Growth doubles with each addition to the input
	* Usually found in tree like structures
	* Trees: O(2^n) represents O(branches ^ tree-depth)
—

Suppose you are to count how many characters there are in the string “cat”. The simplest way is by going through letter by letter and adding one to the counter for each character. This method is said to run in **linear time** with respect to the number of characters. For the string "cat", number of characters _n_ = 3. It will take O(n) or O(3) which means that the time required to traverse the string is proportional to the number of characters. [*](https://www.youtube.com/watch?v=iOq5kSKqeR4)

 to be continued

# Data Structures
> Data Structure is a way of collecting and organizing data in such a way that we can perform operations on these data in an effective way. [*](https://www.studytonight.com/data-structures/introduction-to-data-structures)  

Data Structures provides an effective way of organizing data in order for you to efficiently manipulate operations on it. It is used to reduce complexity and increases efficiency.

### Arrays
> Array is a container object that holds a fixed number of values of a single type. [*](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html)  

[ ] Practice coding using arrays and pointers

**Pointer variable** - stores a memory address

An asterisk mark (`*`) before the name indicates that the variable is a pointer variable.

Declaring a pointer:		`type *ptr;` 	example:   `int *ptr;`
 
To initialize a pointer variable, the ampersand sign (`&`) is used to get the address of its operand. This is called the **Address-of operator**, a unary operator that returns the address of its operand.

Initialize a pointer:
```
int x = 10;	//initialize a variable
int *ptr;		//declare a pointer variable
p = &x; 		// get the address of x and assign it to p
```

Since a pointer stores the memory address of a certain variable/object, it can be used to directly access the value of the object it is pointing. **Deferencing operator** used as unary operator, `*` refers to object to which its operand points.

```
//continuing the code above

cout << *p << endl; //prints the value stored in the memory location pointed by p

//output: 10
```

