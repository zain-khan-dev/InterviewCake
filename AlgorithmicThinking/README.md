# Big O notation
Big O notation is the language we use for talking about how long an algorithm takes to run.
    
    - It tells us how quickly the runtime grows
    - It is relative to the input
    - It depicts when the input is arbitarily large (Asymptotic when the input is very large)
    - We drop the Constant and the less signifcant terms
    - Worst case is implied can also tell best case 
    - We are talking about extra space dont talk about the space taken by input
    - Sometimes the constant matters
    - Beware of premature optimization:-Sometimes improving time or space complexity negatiively impact readability	
# Data Structure
What we will implement

   - Random access memory
   - Binary numbers
   - Fixed width Integers
   - Arrays
   - Strings
   - Pointers
   - Dynamic Arrays
   - Linked List
   - Hash Tables
## Random Access Memory
When a computer is running code, it needs to keep track of variables (numbers, strings, arrays, etc.). 
RAM is not where mp3s and apps get stored. In addition to "memory," your computer has storage (sometimes called "persistent storage" or "disk"). While memory is where we keep the variables our functions allocate as they crunch data for us, storage is where we keep files like mp3s, videos, Word documents, and even executable programs or apps. 
Memory (or RAM) is faster but has less space, while storage (or "disk") is slower but has more space. A modern laptop might have ~500GB of storage but only ~16GB of RAM. 
Spinning hard drives don't have this "random access" superpower, because there's no direct connection to each byte on the disk. Instead, there's a reader—called a head—that moves along the surface of a spinning storage disk (like the needle on a record player). Reading bytes that are far apart takes longer because you have to wait for the head to physically move along the disk. 
Even though the memory controller can jump between far-apart memory addresses quickly, programs tend to access memory that's nearby.
The processor has a cache where it stores a copy of stuff it's recently read from RAM. 


## Binary Numbers
Computers dont have 10 digits but only two states on and off thus we use base 2 to address things in computer
The places in binary are sequencial power of two instead of power of 10
Fractions :-store two numbers numerator and denominator
Decimal:- Store two numbers one with decimal taken out other where decimal goes(how many digits over from the leftmost digit)
Negative Number:- Leftmost digit for the sign of number 0 for positive and 1 for negative

We usually take 32 or 64 bits to store integers depending upon the processer 
There is a danger of overflowing the bits 
When is 32 bits not enough? When you're counting views on a viral video. YouTube famously ran into trouble when the Gangnam Style video hit over 231 views, forcing them to upgrade their view counts from 32-bit to 64-bit signed integers. 
Most integers are fixed-width or fixed-length, which means the number of bits they take up doesn't change. 
It's usually safe to assume an integer is fixed-width unless you're told otherwise. Variable-size numbers exist, but they're only used in special cases. 
ecause they have a constant number of bits, most simple operations on fixed-width integers (addition, subtraction, multiplication, division) take constant time (O(1) time). 

## Arrays
RAM is basically an array 
address of nth bit is =array start+n
To build an array of 64-bit (8 byte) integers on top of our 8-bit (1 byte) memory slots
We simply give each array index 8 address slots instead of 1: 
address of nth item in array= address of array start+(n∗size of each item in bytes)all the math we're using here to get the address of the nth item in the array takes O(1) time. 

This works only if
    • Each item in the array is the same size
    • The array is contiguous in memory
## Strings
A series of characters is called a string
The mapping of numbers to characters is called character encoding.The most common is ASCII.We can express string as an array of 8 bit numbers mapped as characters
## Pointer
Instead of storing arrays as a fixed size we can replace them with a pointer which is just an address and points to another address in the memory
Using pointer instead of array have a tradeoff of cache not being stored
This pointer-based array requires less uninterrupted memory and can accommodate elements that aren't all the same size, but it's slower because it's not cache-friendly. 
## Dynamic Array
When we allocate the array we have to specify how much space it will take so any other variable does not take up that space
We dont want some other program overwriting the array
Dynmaic array:-To allocate some space and then resize it whenever necessary
When dynamic array gets filled it increases it size usually doubling
then copy each element from old array to new array
Free up the old space
Append new items
Worst case appending of O(n)
Since copying occurs at the rate of doubling and is done very less times The amortized time is O(1) for this
## Linked List
We can use a structure that store a character and a pointer that points to the next structure of same type.Each element is called node and series of nodes called linked list
The first node is called head and the last node is called tail
Worst case appending of O(1)
Prepending an item takes O(1)
Arrays have O(1) time lookups linked list have O(n)
Walking down a linked list does is not cache friendly
Hash Tables
We can use storing of data and lookup of data in constant time at least amortized.
We can convert any element to a hash and then force that number under some range using modulus operator
The process of translating a key into an array index is called a hashing function
But what if two keys hash to same index:-This is called hash collision 
Some common techniques to overcome this 
    • Instead of storing actual value store linked list holding the count of all words that hash to it and storing the word as well.In the worst case it is O(n) but in industry we say that collision are rare and in average it takes O(1) time 
      
## Summary
Arrays have O(1)-time lookups. But you need enough uninterrupted space in RAM to store the whole array. And the array items need to be the same size. 
But if your array stores pointers to the actual array items (like we did with our list of baby names), you can get around both those weaknesses. You can store each array item wherever there's space in RAM, and the array items can be different sizes. The tradeoff is that now your array is slower because it's not cache-friendly. 
Another problem with arrays is you have to specify their sizes ahead of time. There are two ways to get around this: dynamic arrays and linked lists. Linked lists have faster appends and prepends than dynamic arrays, but dynamic arrays have faster lookups. 
Fast lookups are really useful, especially if you can look things up not just by indices (0, 1, 2, 3, etc.) but by arbitrary keys ("lies", "foes"...any string). That's what hash tables are for. The only problem with hash tables is they have to deal with hash collisions, which means some lookups could be a bit slow. 
Each data structure has tradeoffs. You can't have it all. 
So you have to know what's important in the problem you're working on. What does your data structure need to do quickly? Is it lookups by index? Is it appends or prepends? 
Once you know what's important, you can pick the data structure that does it best. 

# Logarithms
What power must we raise this base to n in order to get the answer
x^n=p
logx(p) x called base as it is at bottom
Solving for n when n is an exponent
Rules
    • Simplification: log<sub>b</sub>​(bx)=x . . . Useful for bringing a variable down from an exponent. 
    • Multiplication: log<sub>b</sub>(x∗y)=log<sub>b</sub>​(x)+log<sub>b</sub>​(y) 
    • Division: log<sub>b</sub>(x/y)=log<sub>b</sub>(x)−log<sub>b</sub>(y) 
    • Powers: log<sub>b</sub>(x<sup>y</sup>y)=y∗log<sub>b</sub>​(x) 
    • Change of base: log<sub>b</sub>(x)=log<sub>b</sub>​(b)log<sub>c</sub>(x)​ . . . Useful for changing the base of a logarithm from b to c. 
"How many times must we double 1 before we get to n" is a question we often ask ourselves in computer science. Or, equivalently, "How many times must we divide n in half in order to get back down to 1?" 
The answer to both of them is same log<sub>2</sub>(n)
### Logarithm in binary search
    1. Start with the middle number: is it bigger or smaller than our target number? Since the vector is sorted, this tells us if the target would be in the left half or the right half of our vector. 
    2. We've effectively divided the problem in half. We can "rule out" the whole half of the vector that we know doesn't contain the target number. 
    3. Repeat the same approach (of starting in the middle) on the new half-size problem. Then do it again and again, until we either find the number or "rule out" the whole set. 
This way we are diving the array in half and therefore time complexity till we reach 1 is log2(n)
### Logarithms in Sorting
nlog2(n) is the best worst case for sorting.This is for comparison based sorting if we can bound our numbers we can bring down time complexity to O(n)
In merge sort we divide the array until it contains one element this implies the array is sorted then we merge these sorted arrays.To reach the array diving it into half is log<sub>2</sub>(n) and merging at each level takes O(n) time thus time complexiy is nlog<sub>2</sub>(n)

### Logarithm in Trees
Each level in a tree is full this type of tree is called a perfect tree
At each level the number of nodes doubles thus the height of tree we can conclude is log<sub>2</sub>(n)
This means how much time we take to reach n from 1 doubling at each level or how many times should we double 1 to reach n
The exact formula for the number of nodes on the last level is: 
2n+1
Where does the +1 come from? 
The number of nodes in our perfect binary tree is always odd. We know this because the first level always has 1 node, and the other levels always have an even number of nodes. Adding a bunch of even numbers always gives us an even number, and adding 1 to that result always gives us an odd number. 
Taking half of an odd number gives us a fraction. So if the last level had exactly half of our n nodes, it would have to have a "half-node." But that's not a thing. 
Instead, it has the "rounded up" version of half of our odd n nodes. In other words, it has the exact half of the one-greater-and-thus-even number of nodes n+1. Hence 2n+1
h≈log<sub>2</sub>​((n+1​)/2)+1
h=log<sub>2</sub>(n+1)
lg is interpreted as log<sub>2</sub>
