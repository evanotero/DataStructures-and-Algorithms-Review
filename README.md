# DataStructures-and-Algorithms-Review

### To be added...
1. Searching and Sorting
2. Trees
3. Binary Search Trees
4. Heaps and Priority Queues
5. Sets and Maps
6. Mutli-Way Search Trees
7. Graphs
8. Huffman Trees
9. Hashing
...

## Analysis of Algorithms
- The order of an algorithm is found by eliminating constants and all but the dominant term in the algorithm's growth function
- The order of an algorithm provides an upper bound to the algorithm&#39;s growth function
- The time complexity of a loop is found by multiplying the complexity of the body of the loop by how many times the loop will execute
- The analysis of nested loops must take into account both the inner and the outer loops
![complexity chart](http://i.imgur.com/aqiWneL.png)
_image source: http://bigocheatsheet.com/_

## Introduction to Collections – Stacks
- A collection is an object that gathers and organizes other objects
- A collection is an abstraction wherein the details of the implementation are hidden
- An abstract data type is a data type whose values and operations are not inherently defined within the programming language.
- An abstract class is a class that is declared abstract—it may or may not include abstract methods.
  - Abstract classes cannot be instantiated or used as a data type
  - Abstract classes are similar to interfaces in the fact that they cannot be instantiated and that they may contain mix of methods declared with or without an implementation.
    - However, with abstract classes, you can declare fields that are not static and final, and define public, protected, and private concrete methods.
      - Use an abstract class if:
        - You want to share code among severely closely related classes.
        - Expect that classes that extend your abstract class have many common methods or fields, or require access modifiers other than public.
        - You want to declare non-static or non-final fields.  This enables you to define methods that can access and modify the state of the object to which they belong.
    - With interfaces, all fields are automatically public, static, and final, and all methods that you declare or define (as default methods) are public.
      - Use an interface if:
        - You expect that unrelated classes would implement your interface.
        - You want to specify the behavior of a particular data type, but not concerned about who implements its behavior.
        - You want to take advantage of multiple inheritance of type.
    - In addition, you can only extend one class, whereas you can implement any number of interfaces.
- Stack elements are processed in a LIFO manner
- A stack is the ideal data structure to use when evaluating a postfix expression
- A Java interface defines a set of abstract methods and is useful in separating the concept of an abstract data type from its implementation
  - Interfaces cannot have instance variables, concrete methods, be instantiated, or be used as a data type.
- By using the interface name as a return type, we ensure that the interface doesn&#39;t commit the method to the use of any particular class that implements a stack
- A generic type is a placeholder for an object type that is not made concrete until the class that refers to it is instantiated
- Arithmetic expressions
  - Infix
    - Traditionally, arithmetic expressions are written in _infix_ notation, meaning that the operator is placed between its operands in the form:
      - _&lt;operand&gt; &lt;operator&gt; &lt;operand&gt;_
        - ex. 4 + 5
  - Postfix
    - In a _postfix_ expression, the operator comes after its two operands.  Therefore, a postfix expression takes the form:
      - _&lt;operand&gt; &lt;operand&gt; &lt;operator&gt;_
        - ex. 6 – 9 (_infix_)    6 9 – (_postfix_)
    - The process of evaluating a postfix expression can be stated in one simple rule: _Scanning from left to right, apply each operation to the two operands immediately preceding it, and replace the operator with the result_.
  - Prefix
    - In a _postfix_ expression, the operator comes before its two operands.  Therefore, a postfix expression takes the form:
      - _&lt;operator&gt; &lt;operand&gt; &lt; operand &gt;_
        - ex. 6 – 9 (_infix_)    – 6 9  (_prefix_)
  
## Linked Structures – Stacks
- Array vs. ArrayList
  - Arrays are a lower level and cannot use Generics along with them.  ArrayLists are enhanced arrays that allow you to use Generics to ensure type-safety.
  - Arrays are fixed size and ArrayLists expand automatically
  - Arrays use indexing (a[i] = 34;) and ArrayLists use method calls (list.add(34); list.set(i, 34);).
  - You instantiate an array with:
    - Object[] name = new Object[];
  - You instantiate an ArrayList with:
    - ArrayList&lt;Object&gt; name = new ArrayList&lt;Object&gt;();
- A linked list is composed of objects that each points to the next object in the list
  - The LinkedList class itself contains references to the head node and the tail node in the list
  - It also keeps track of the number of items in the list
- A linked list dynamically grows as needed and essentially has no capacity limits
- The order in which references are changed is crucial to maintaining a linked list
- A linked implementation of a stack adds elements to, and removes elements from, one end of the linked list
- Recursive processing can be simulated using a stack to keep track of the appropriate data
- A doubly linked list is a linked list in which each node references to both the next node and the previous node in the list
  - One issue we say in implementing a singly-linked list, is that code frequently needs to include special cases to handle operations at the head or tail.  In particular, adding the first data item to a list or removing the last node from a list often requires special coding
    - The need for such special cases can frequently be reduced or eliminated through the use of one more _sentinel nodes_.
      - A _sentinel node_ is a dummy list node which contains no data, but is merely a placeholder at the beginning or end of a list.
      - When sentinel nodes are used, even an empty list contains at least one node (the sentinel), so we are never faced with the problem of adding the first node or removing the last
      - For a doubly linked list, one approach is to place a sentinel node at the head and tail of every list.  In this way, even an empty list always contains a minimum of two nodes, the header and the trailer.
- Circular linked list
  - In a singly linked list, the next pointer of the last node points to the first node.
  - In a doubly linked list, the next pointer of the last node points to the first node and the previous pointer of the first node points to the last node making the circular in both directions.

## Queues
- Queue elements are processed in a FIFO manner
- A linked implementation of a queue is facilitated by references to the first and last elements of the linked list
- The enqueue and dequeue operations work on opposite ends of the collection
- The shifting of elements in a noncircular array implementation creates a O(n) complexity

## Lists
- List collections can be categorized as ordered, unordered, or indexed
- The elements of an ordered list have an inherent relationship defining their order
- The elements of an unordered list are kept in whatever order the client chooses
- An indexed list maintains a contiguous number index range for its elements
- The Java API does not provide a class that implements an ordered list
- Only Comparable objects can be stored in an ordered list
- Efficiency (worst-case run times):
  - Unordered Array List:
    - add(item): O(1)
    - remove(0): O(n)
    - get(index): O(1)
    - contains(item): O(n)
  - Unsorted Linked List:
    - add(item): O(1)
    - remove(0): O(1)
    - get(index): O(n)
    - contains(item): O(n)
  - Sorted Linked List:
    - add(item): O(n)
    - remove(0): O(1)
    - get(index): O(n)
    - contains(item): O(n)

## Iterators
- An iterator is an object that provides a way to access each element in a collection in turn
- A collection is often defined as Iterable, which means it provides an Iterator when needed
- The optional remove method of an iterator makes it possible to remove an element without having to traverse the collection again
- An iterator class is often implemented as an inner class of the collection to which it belongs

## Recursion
- Recursion is a programming technique in which a method calls itself
- Any recursive definition must have a nonrecursive part, called the base case, that permits the recursion to eventually end
- Each recursive call to a method creates new local variables and parameters
- The order of a recursive algorithm can be determined using techniques similar to those used in analyzing iterative processing.
  - Analyzing a recursive algorithm is a matter of determining the order of the recursion (the number of times the recursive definition is followed) and multiplying that by the order of the body of the recursive method.
- Indirect recursion is the type of recursion in which a method calls another method, which may call yet another, and so on until the original method is called.
- Direct recursion is the type of recursion in which a method invokes itself directly
