# 01 Pointer Exercises
#googlegoals

### Pointers
[01](http://www.csc.villanova.edu/~mdamian/Past/csc2400fa13/assign/plab.pdf)- Find out (add code to print out) the address of the variable x in foo1, and the variable y in foo2. What do you notice? Can you explain this?

```
#include <stdio.h>
void foo1(int xval) {
  int x;
  x = xval;
	/* print the address and value of x here */ 
	cout << &x << endl; //prints address of x using address-of operator
	cout << x << endl; //print value of x directly
}
void foo2(int dummy) {
	/* print the address and value of y here */ 
	int *y = &dummy; //assign the memory address of dummy to pointer variable y
	cout << 
}

int main() {
	foo1(7); 
	foo2(11); 
	return 0;
}
```

[02](http://www.csc.villanova.edu/~mdamian/Past/csc2400fa13/assign/plab.pdf) - The program below uses pointer arithmetic to determine the size of a 'char' variable. By using pointer arithmetic we can find out the value of 'cp' and the value of 'cp+1'. Since cp is a pointer, this addition involves pointer arithmetic: adding one to a pointer makes the pointer point to the next element of the same type.
For a pointer to a char, adding 1 really just means adding 1 to the address,
but this is only because each char is 1 byte.
1. Compile and run the program and see what it does.
2. Write some code that does pointer arithmetic with a pointer to an int and determine how big an int is.
3. Same idea – figure out how big a double is, by using pointer arithmetic and printing out the value of the pointer before and after adding 1.

```
// Example program
#include <iostream>
#include <string>
#include <stdio.h>

using namespace std;

int main()
{
    char c = 'Z'; 
    char *cp = &c;
    printf("cp is 0x%08x\n", cp);
    printf("The character at cp is %c\n", *cp);
    /* Pointer arithmetic - see what cp+1 is */ cp = cp+1;
    printf("cp is 0x%08x\n\n", cp);
    /* Do not print *cp, because it points to
    memory space not allocated to your program */
    
    int i = 5;
    int *ip = &i;
    cout << "i is " << ip << endl;
    cout << "The integer at ip is " << *ip << endl;
    ip = ip + 2;
    cout << "ip is " << *ip << endl;
    *ip = 7;
    cout << "ip is " << *ip << endl << endl;
    
    int d = 3.8;
    int *dp = &d;
    cout << "d is " << dp << endl;
    cout << "The double at ip is " << *dp << endl;
    dp = dp + 8;
    cout << "dp is " << *dp << endl;
    
    return 0;
}
```

```
#include <iostream>
#include <vector>

using namespace std;

int main() {
	vector<int> myvector;
	
	cout << "empty(): " << myvector.empty() << endl;
	myvector.push_back(2);
	myvector.push_back(5);
	
	vector<int>::iterator it;
	it = myvector.begin() + 1;
	it = myvector.insert(it,3);
	
	
	for(int i = 0; i < myvector.size(); i++){
	    cout << myvector.at(i) << " ";
	}
	
	cout << "\nis_empty(): " << myvector.empty() << endl;

	return 0;
}

```