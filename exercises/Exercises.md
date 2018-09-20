# Exercises
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

[02](http://www.csc.villanova.edu/~mdamian/Past/csc2400fa13/assign/plab.pdf) - 