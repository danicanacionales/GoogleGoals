# 00 Google Goals
#googlegoals
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
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png)

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

**Pointer variable** - stores a memory address

An asterisk mark (`*`) before the name indicates that the variable is a pointer variable.

Declaring a pointer:		`type *ptr;` 	
Example:   `int *ptr;`
 
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

**Importance of Pointers** [*](https://graphics.ethz.ch/~chschuma/info1_13/exercise7_slides.pdf)
	* Allocating memory during runtime
	One example is if you want to declare an array, but decide on the 	size of the array while the program is running. 
	* Passing pointers as function arguments
	This allows the function to change the value outside the scope of the function	

**Pointers and Arrays** [*](https://graphics.ethz.ch/~chschuma/info1_13/exercise7_slides.pdf)
Arrays are internally represented by pointers. 
```
int myArray[5] = { 1, 2, 3, 4, 5 };
int *pArray = &myArray[0];	//first statement
pArray = myArray;				//second statement
```

The first and second statement would actually have the same values. It would both point to the address of the first element. Now, pointers can also be used to access the other elements in the array.

This can be used by adding the array type’s byte size to the pointer. You may look at the example below.

```
int myArray[5] = { 11, 12, 13, 14, 15 };
int *pArray = &myArray[0];
	
for(int i = 0; i < 5; i++){
	pArray = myArray + i;
	cout << (pArray) << "'s value: " << *pArray << endl;
}

// Output: 
// 0x7fffba804100's value: 11
// 0x7fffba804104's value: 12
// 0x7fffba804108's value: 13
// 0x7fffba80410c's value: 14
// 0x7fffba804110's value: 15
```

In this example, we can see that the for loop is iterating through the array. For every iteration, we can see that we are incrementing by one and adding it to the address _myArray_. This is done so that in every iteration, it would assign the pointer to the next element in an array. It is incremented by one because integers has the byte size of one.

**Array Size**
In C++, we make use of the `sizeof()` function, which returns the size of an object, in order to get the size of an array.

```
int myArray[5]= { 11, 12, 13, 14, 15 };
cout << sizeof(myArray[0]);
cout << sizeof(myArray);
cout << (sizeof(myArray)/sizeof(*myArray));
```

The first output statement returns the byte size of the first element, an integer, which is 4 bytes.
The second output statement returns the byte size of the entire array which contains five integers, then the result would be 20.
The third statement would return the number of elements inside the array. This is done by dividing the total byte size of the array by the byte size of one element. 20 bytes / 4 bytes = 5.

**Vector**
> sequence of containers representing arrays that can change in size.  

Vectors is basically an array which can store a dynamic number of elements. Using arrays however, you can only store a fixed number of elements. 

How do vectors work? In order for a vector (dynamic array) to have a dynamic size, it may internally reallocate in order to grow in size when new elements are inserted. This means that it allocates a new array and moving all elements to it. [*](http://www.cplusplus.com/reference/vector/vector/) 

[ ] Practice coding using arrays and pointers
Exercise 1 [*](http://www.csc.villanova.edu/~mdamian/Past/csc2400fa13/assign/plab.pdf)

### Linked List
A linked list is a linear data structure, in which the elements are stored as separate objects. Each element in a linked list _links_ or points to its next element in the sequence. 

**Main Components**
The main components of a linked list are the head and the node. 

The head is a pointer that points to the first element of the list. 

While the nodes, which can be a class, a struct or something similar, contains a key and a next pointer. The key contains the actual value being stored and the next pointer stores or points to the next element in the list.
![linked list node](https://github.com/danicanacionales/googlegoals/blob/master/images/03%20linked%20list%20node.png?raw=true)

One way we can do this in code is by creating a class Node
```
class Node {
	public:
		string value;
		Node next;
}
```

**Array vs. Linked List**
Arrays are stored next to each other in sequence.
![array](https://github.com/danicanacionales/googlegoals/blob/master/images/04%20array.png?raw=true)
However, for a linked list, each variable is stored in its own memory. Not necessarily next to each other. With the help of the next pointer stored in the node, it can point to the element next to the other.
![linked list](https://github.com/danicanacionales/googlegoals/blob/master/images/05%20linked%20list.png?raw=true)

**Advantages of Linked Lists**
Main advantage of using linked list is the efficient insertion and deletion from the list. For instance, we want to insert Y after the element B.

Given the array illustrated above, in order for us to insert an element, we have to:
	1. Resize the array. This can be done by declaring a new array with larger size
	2. Copy the elements to the new array. We must keep in mind to leave the index you want to insert on empty.
	3. Insert the new element.

For a linked list, here are the general steps to insert an element.
	1. Create a new node with its value.  We then store the reference of the succeeding node in order for us to determine which element is next.
	For this example, we create a new node with element Y, and getting 	the next pointer of element B and assign it to element Y.
	2. Point the preceding node to the new node by changing its next pointer to the address of the new node.
![linked list insertion](https://github.com/danicanacionales/googlegoals/blob/master/images/06%20linked%20list%20insertion.png?raw=true)

**Functions**
push_back(value) - adds an item at the end
```

```


### Stack
> Data structure that can be logically thought of as a linear structure represented by a real physical stack or pile, a structure where insertion and deletion of items takes place at one end called top of the stack. [*](https://en.wikibooks.org/wiki/Data_Structures/Stacks_and_Queues#Stacks)  

The basic idea of a stack is a stack of books where you can only take the top item off the stack in order to remove things from it.

The basic implementation of a stack is also called as a LIFO or Last In First Out.

The basic functions for a stack are:
	* push() - This will insert the item on top of the stack.
	* pop() - This will remove the topmost item from the stack.

###  Queues
> Container of objects that are inserted and removed according to the first-in first-out (FIFO) principle. [*](https://www.cs.cmu.edu/~adamchik/15-121/lectures/Stacks%20and%20Queues/Stacks%20and%20Queues.html)  

The most basic example of queues is a line of customers in a fast food restaurant. The first customer will be the first one to order and be served and removed from the queue while the next customers will have to line up behind them.

The basic functions for a queue are:
	* enqueue - insert an item into the back of the queue
	* dequeue - remove the front item

### Hash Table










