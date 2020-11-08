# Arrays
An array organises items sequentially one after another in memory
Each element has an index starting from 0
### Strength
Fast lookups:-Retrieve elements at given index O(1) Time 
Fast Append:-Adding an element at the end takes O(1) Time
### Weakness

    1. Fixed Size:-Need to specify how many elements to store
    2. Costly insert and delete from in between:-

Worst Case Complexity
- Space :-O(n)
- lookup:-O(1)
- append:-O(1)
- insert:-O(n)
- delete:-O(n)


## Insertion:-
To insert an element we have to shift each element by one place
 
## Deletion:-

When we delete an elment we have to move back each element to the space where the element is deleted
Arrays are the basic blocks which are used as an intermediatery to complex data structure
When do not need to specify space  ahead of time:-dynamic array
When want to use something other to index element use unordred map

# Array Slicing

Array slicing involves taking a subset of an array and allocating a new array with those elements
This takes O(n) time and space

<h1 style="align:center"> In Place Algorithm</h1>
The call stack is what a program uses to keep track of the function calls. The call stack is made of stack frames one for each call
A stack frame usually consist of 
- Local variables
- Arguments passed into functions
- Information about the caller stack frame 
- The return address what the program should do after the function returns 


This calling of stack is usually used in recursive algorithm 

We must account for the stack space in recursive function as it may seem deceiving when we use recursive function and use stack space This can also lead to stack overflow when we do not return and not pop stack.Call stack is popped when function returns

If the very last thing a function does is call another function, then its stack frame might not be needed any more. The function could free up its stack frame before doing its final call, saving space. 

This is called tail call optimization (TCO). If a recursive function is optimized with TCO, then it may not end up with a big call stack. 

In general, most languages don't provide TCO. Scheme is one of the few languages that guarantee tail call optimization. 

Some Ruby, C, and Javascript implementations may do it. Python and Java decidedly don't. 

In-place algorithms are sometimes called destructive, since the original input is "destroyed" (or modified) during the function call. 

Careful: "In-place" does not mean "without creating any additional variables!" Rather, it means "without creating a new copy of the input." In general, an in-place function will only create additional variables that are O(1) space. 

Working in-place is a good way to save time and space. An in-place algorithm avoids the cost of initializing or copying data structures, and it usually has an O(1) space cost. 

But be careful: an in-place algorithm can cause side effects. Your input is "destroyed" or "altered," which can affect code outside of your function. For example: 

Generally, out-of-place algorithms are considered safer because they avoid side effects. You should only use an in-place algorithm if you're space constrained or you're positive you don't need the original input anymore, even for debugging. 

# Dynamic Array

A dynamic array is an array with automatic resizing


| Complexity  | Average Case | Worst Case |
| - - - - - - | - - - - - - -| - - - - - -|
|    space    |      O(n)    | 	  O(n)    |
|    lookup   |      O(1)    | 	  O(1)    |
|    append   |      O(1)    |    O(n)    |
|    insert   |      O(n)    | 	  O(n)    |
|    delete   |      O(n)    | 	  O(n)    |



### Strength

- Fast Lookup:-Retreiving an element takes O(1) time
- Variable Size:-Can add as many elment as we want will resize automatically
- Cache-Friendly:-Place element right next to each other making efficient use of cache
### Weakness

- Slow worst case append:-In the worst case append takes O(1) since it needs to resize and copy elements over
- Costly insert and delete:-Since the element are stored next to each other deleting an element from middle still takes moving back all the elements to freed up space

## Size vs Capacity

Size is the limit to which elemets are inserted and capacity overall size of the array in C++ it uses endIndex to keep track where the dynamic array ends and extra capacity begins

## Doubling Appends

When the capacity is full the extra append try to make capacity by increasing the size of the array usually by doubling the capacity 
> The array is not extended because the extra space might be taken by some other program

## Amortized Cost of appending

    1. The time cost of each special O(n) "doubling append" doubles each time.
    2. At the same time, the number of O(1) appends you get until the next doubling append also doubles.

These two things cancel out and we say each one has O(1) time of appending 


