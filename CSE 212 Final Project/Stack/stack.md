# STACKS
## In this lesson I am going to talk about Stacks and some examples where stacks can applied in real life.
## I will cover what a Stack is.
## And I will cover Stack Operations that incude Push, Pop and Peek and O notaion and time complexity for all operarions
## What is a stack?
A stack is very similar to the idea of what a physical stack would look like. The  stack data structure
allows us to place a variabel or object on it. A very s imple example of how the idea of stacks can be explained is to think
of four books. Book A, Book B Book C and Book D and they are spread accross a table.
Lets say you organize these books with A being the first one then you pile up B,C and D on top of each other.
We now have a bice stack of Books!
If we want to read book A we need to take down books starting with D then C and then B to get  to A
That is the idea behind a data structure stacks.

## Diagram of Stack
![My image file](https://media.geeksforgeeks.org/wp-content/uploads/20210716162942/stack-660x345.png)

## Things to note Big O for  each operation stacks
Lucky for us the time complxity for push(), pop() and peek() all take O(1) time. We do not run any loop in any of these operations.

# STACK OPERATIONS
Wwe have the Push Pop and Peek.

## We will start with the Push.
The operation  to insert elements in a stack is called a push. When you push  the book on a stack we put the 
book on top the previous book or element. When we say push elements onto a stack we insert an element on to a 
stack and the last element to be added is the usually on top of the stack.

## Pop
Popping is when we take the top most book on our stack and put it down.  When we remonve an elemtn from a stack the stack
follows the First in Last out property. This means that the top element which is last to eb inserted is removed
when we perfrom the pop operation.

## Peek
The Peek  opertion retruns the top most element in stack. Lets say we pop the first two books in our stack
the peek function will retyrn the top most book in our stack. So if remove Book D and Book C, what will
the peek function return? Book B.
## Application of Stacks
There are some popular ways that stacks have been used to make our experience while using softwares easier. Think of Google Chrome. It is a browsing application. Lets say you are browsing the internet and want to opne up an article and on that new article you opne up another article. But now you wanna go back to the previous article. How do you think these articles are saved? If you guessed using stacks then you are hella smart.

## Live Example
Now enough with the talking lets look at a coding example. 
We are going to look at some code and see the basics of  how stacks works

``` python
stack = []
 
#append() function to push
#element in the stack
stack.append('a')
stack.append('b')
stack.append('c')
 
print('Initial stack')
print(stack)
 
#pop() function to pop
#element from stack in
#LIFO order
print('\nElements popped from stack:')
print(stack.pop())
print(stack.pop())
print(stack.pop())
 
print('\nStack after elements are popped:')
print(stack)
 
#uncommenting print(stack.pop())
#will cause an IndexError
#as the stack is now empty

Here is the outpit for this code

Initial stack
['a', 'b', 'c']

Elements popped from stack:
c
b
a

Stack after elements are popped:
[]
```


## Sample Problem
In this section I am going to ask you a question and then you are going to solve it.
## Question 1
Given a string path which is an absolute path starting with a slash '/') to a file or directory in a Unix style file system, convert it to a the simplified canoical path

In Unix style file system a period '.' refers to the current directory a double period '..' refers to the directory up a level.

``` python
class Solution:
    def simplifyPath(self, path:str) -> str:
        stack = []
        cur = ""

        for c in path + "/":
            if c == "/":
                if cur == "..":
                    if stack : stack.pop()
                    elif cur!= "" and cur != ".":
                        stack.append(cur)
                    cur = ""
            else: cur += c
        return "/" + "/".join(stack)
```




