# **Stacks in C**

A stack is a linear data structure in which the insertion of a new element and removal of an existing element takes place at the same end represented as the top of the stack. Stacks follow the LIFO, or Last-In-First-Out, Principle. According to this approach, the last item to be inserted will be the first one to be removed. An example from real life is a stack of plates where the plate placed on top is the most recently added. Since we typically take the top plate off first, we can conclude that the last plate added will be the first one to be removed.

A stack can be represented as follows:

![Visual representation of a stack](https://www.softwaretestinghelp.com/wp-content/qa/uploads/2019/06/pictorial-representation-of-stack.png)

## Operations on Stacks:
- push() to insert an element into the stack
- pop() to remove an element from the stack
- top() Returns the top element of the stack.
- isEmpty() returns true if stack is empty else false.
- size() returns the size of stack.

The push() and pop() operations are described further in detail below:

### **push()**
The push operation is used to add an item to the top of a stack. It involves two steps:

1. Check if the stack is full: If the stack is full, it cannot accommodate any more items, and the push operation fails.
2. Add the item to the top of the stack: If the stack is not full, the item is added to the top of the stack. This involves incrementing the top pointer to the next empty position and storing the item at that position.

Algorithm:

```
begin
 if stack is full
    return
 endif
else  
 increment top
 stack[top] assign value
end else
end procedure
```

### **pop()**
The pop operation is used to remove the item at the top of a stack. It involves two steps:

1. Check if the stack is empty: If the stack is empty, there are no items to remove, and the pop operation fails.
2. Remove the item at the top of the stack: If the stack is not empty, the item at the top of the stack is removed. This involves retrieving the item at the top position, decrementing the top pointer to the previous position, and updating the stack to reflect the removal of the item.

Algorithm:

```
begin
 if stack is empty
    return
 endif
else
 store value of stack[top]
 decrement top
 return value
end else
end procedure
```

The program in this repository shows the implementation of a stack using arrays in C.

### Code:

```
// program to implement a stack using an array

#include <stdio.h>

#define MAX 10

int stk[MAX];
int top = -1;

void push();
void pop();
void display();

int main()
{
    int choice;
	char c;
	
	printf("Stack Operations: \n");
	printf("1. push\n2. pop\n3. display\n");
	
	do
	{	
		printf("\nEnter 1, 2 or 3 to perform a stack operation from the list above, or 4 to exit: ");
		scanf("%d", &choice);
	
		switch(choice)
		{
			case 1:
				{
					printf("\n\nEntered choice: %d\n", choice);
					push();
					break;
				}
			case 2:
				{
					printf("\n\nEntered choice: %d\n", choice);
					pop();
					break;
				}
			case 3:
				{
					printf("\n\nEntered choice: %d\n", choice);
					display();
					break;				
				}
			case 4:
				{
					printf("\n\nTerminating...");
					break;
				}
			default:
				{
					printf("\n\nInvalid choice. Terminating...");
					break;
				}		
		}
		
	}while(choice == 1 || choice == 2 || choice == 3);
	
	return 0;

    return 0;
}

// push function
void push()
{
    int n;

	printf("Enter an integer: ");
	scanf("%d", &n);

    if(top == (MAX - 1))
    {
        printf("stack overflow, cannot push element into the stack");
    }
    else
    {
        top++;
        stk[top] = n;

        printf("Element entered.\n\n\n");
    }

}

//pop function
void pop()
{
    if(top < 0)
    {
        printf("stack underflow, cannot pop element from the stack");
    }
    else
    {
        top--;
        printf("Element removed.\n\n\n");
    }

    return;
}

//display function
void display()
{
    int i;

    printf("Available stack: ");

    for(i = 0; i <= top; i++)
    {
        printf("%d\t", stk[i]);
    }

    printf("\n\n\n");
    
    return;
}
```

### Output:

![stacks.c output 1](https://github.com/Aditi-exe/C-Stacks/blob/main/stacks1.PNG)

![stacks.c output 2](https://github.com/Aditi-exe/C-Stacks/blob/main/stacks2.PNG)

![stacks.c output 3](https://github.com/Aditi-exe/C-Stacks/blob/main/stacks3.PNG)

![stacks.c output 4](https://github.com/Aditi-exe/C-Stacks/blob/main/stacks4.PNG)

![stacks.c output 5](https://github.com/Aditi-exe/C-Stacks/blob/main/stacks5.PNG)

![stacks.c output 6](https://github.com/Aditi-exe/C-Stacks/blob/main/stacks6.PNG)


