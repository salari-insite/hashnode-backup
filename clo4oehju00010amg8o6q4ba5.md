---
title: "Learn the Basics of Python Programming: Control Flow"
seoTitle: "Python Control Flow Basics Guide"
seoDescription: "Master Python control flow: learn conditional statements, loops, loop controls for efficient programming with if, elif, else, for, while, break, conti..."
datePublished: Tue Oct 24 2023 18:44:33 GMT+0000 (Coordinated Universal Time)
cuid: clo4oehju00010amg8o6q4ba5
slug: learn-the-basics-of-python-programming-control-flow
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/mfxTRWrjtV0/upload/fab297742918565d57b03cf4e2e5ac3e.jpeg
tags: software-development, python, control-flow

---

# Introduction

> In this article, we explore the concept of control flow in Python, which determines the order of a program's instructions execution. We discuss conditional statements (if, elif, and else), loops (for and while), and loop control statements (break, continue, and pass). We also cover nested conditional statements, nested loops, and the use of the range() function for generating sequences of numbers. By understanding these concepts, you can create more efficient and versatile Python programs.

## Definition of control flow

Control flow is the order in which a program's instructions are executed and is determined by conditional statements, loops, and function calls.

It allows a program to make decisions, repeat specific tasks, and organize code into reusable functions, enabling complex algorithms and dynamic behavior.

Without control flow, a program would just be a long laundry list of predefined instructions.

Although, control flow allows your program to be able to handle user inputs/behavior, and be able to pivot the outputs/behavior of the program based on the user inputs/behavior.

---

## Overview of control flow in Python

In Python, control flow mainly consists of conditional statements (if, elif, and else), conditional/unconditional loops (for and while loops), and loop control statements (break, continue, and pass).

Another popular control flow method in other programming languages is switch/case statements. Up until very recently, Python didn't have the capability for switch/case statements. However, with the release of Python 3.10 in 2021, switch/case statements are now supported in Python.

I won't be covering switch/case statements in this article since they're still very new in the Python language, and they're not as widely used as the control flow methods I'll be covering.

Further, the logic of switch/case statements is very similar to if/elif/else statements. Traditionally, switch/case statements are used instead of if/elif/else statements if there are many different conditions/cases that the program has to handle.

Although, for general control flow, switch/case statements aren't always necessary.

---

## Conditional Statements

Conditional statements in Python are structured as a hierarchy of statements where the first statement is made with the "if" keyword. It should be noted that it is sufficient enough to *just* have an "if" statement. Although, you can also add another conditional statement starting with the "else" keyword after the "if" statement. Finally, if you need to control other conditions in your program, then you can do so with conditional statements placed in between the "if" and "else" statements and made with the "elif" keyword.

The logic behind conditional statements is:

1. If this condition is met/if this is a true statement: do this...
    
2. Elif this condition is met/if this is a true statement: do this...
    
3. Else: do this...
    

The if statement checks a condition, and if it's True, the code block within it is executed. The elif statement checks another condition if the previous conditions are not met. The else statement executes a code block if **none** of the previous conditions are met.

### The 'if' statement

The if statement begins with the "if" keyword, followed by a statement that returns a Boolean value (True or False).

As such, when you're checking if a certain condition is met, you use the double equals, exclamation equals, greater than, less than, greater than or equals to, or less than or equals to.

Alternatively, you can also use the "is" keyword or "is not" keyword to check logical equivalence, although this is only reserved for comparing Boolean values and the None value.

In addition, you can also construct conditional statements by using "or" or "and" keywords to check if at least one condition or multiple conditions are met before executing a block of code.

### Syntax

```python
# Basic syntax of if statement:
if 1 == 1: # True statement
    print(True)

##############################

if 2 != 1: # True statement
    print(True)

##############################

if 3 > 2: # True statement
    print(True)

##############################

if 2 < 3: # True statement
    print(True)

##############################

if 4 >= 3: # True statement
    print(True)

##############################

if 3 <= 4: # True statement
    print(True)

##############################

if None is None: # True statement
    print(True)

##############################

if False is not None: # True statement
    print(True)

##############################

if 2 == 2 or 2 == 3: # True statement 
    # This line will execute since at least one condition is met
    print(True)

##############################

if 3 == 3 and 4 == 4: # True statement
    # This line will execute since both conditions are met
    print(True)
```

### Example

```python
age = 21

# Basic if statement
# Check if the 'age' variable is greater than or equal to 21
if age >= 21:
    # This line will execute since the condition is met
    print("Do you want a glass of wine with your meal?")

##############################

animal = "cat"

if animal == "dog":
    # This line WON'T execute since the condition is not met
    print("Do you wanna go for a walk outside?!")
```

### The 'elif' statement

Elif statements are placed in between the if statement and the optional else statement.

In one if/elif/else control flow structure, there can be multiple elif statements, but only 1 if statement and 1 else statement.

Similar to the if statement, the elif statement evaluates a comparison or multiple comparisons.

If the original condition in the if statement is not met, then the program will skip to the proceeding elif statement to see if that condition is met.

It's important to note that an if/elif/else control flow structure stops evaluating statements as soon as a condition is met. This means that even if you have multiple elif statements that evaluate to true, only the first elif statement that evaluates to true will be the block of code that is executed.

Also, since each conditional control flow structure has to start with an if statement, this means that the program knows when a new control flow structure you write another if statement line (even if that if statement line is written after another if statement or an elif statement in another control flow structure above it).

### Syntax

```python
# Basic syntax of elif statement:

if 2 == 1: # False statement
    # This line won't execute
    print("2 is equal to 1")

elif 2 != 1: # True statement
    # This line will execute
    print("2 is not equal to 1")

elif 2 > 1: # True statement
    # This statement evaluates to true
    # But, this line won't execute since the elif above 
    # evaluated to true
    print("2 is greater than 1")

##############################

if 2 < 3: # True statement
    # This line will execute
    # Therefore the program won't even evaluate the elif
    # statements below.
    print("2 is less than 3")

elif 4 >= 5: # False statement
    print("4 is greater than or equal to 5")

elif 3 <= 4: # True statement
    print("3 is less than or equal to 4")

##############################

if False is None: # False statement
    # This line won't execute.
    # So, the program will evaluate the proceeding
    # elif statement.
    print("False is None")

elif True is not None: # True statement
    # This line will execute, so the program will 
    # not evaluate the elif statements below.
    print("True is not None")

elif 2 == 2 or 2 == 3: # True statement
    print("2 is equal to 2, or 2 is equal to 3")

elif 3 == 3 and 4 == 4: # True statement
    print(True)
```

### Example

```python
age = 10

if age >= 21: # False statement
    # This line won't execute
    print("Do you want a glass of wine with your meal?")

elif age < 12: # True statement
    # This line will execute
    print("Would you like a kids menu?")

##############################

animal = "dog"

if animal == "dog": # True statement
    # This line will execute.
    # Program won't evaluate the elif statement below.
    print("Do you wanna go for a walk outside?!")

elif animal == "cat": # False statement
    print("Do you want some catnip?!")
```

### The 'else' statement

Similar to the elif statement, the else statement is an optional statement that is placed at the very end of an if/elif/else control flow structure.

Unlike the if and elif statements, the else statement doesn't evaluate if a condition is met. Instead, the program will simply execute the code in the else block if all of the conditions above the else statement are not met.

### Syntax

```python
# Basic syntax of elif statement:

if 2 == 1: # False statement
    # This line won't execute
    print("2 is equal to 1")

else:
    # This line will execute, since the above condition wasn't met
    print("2 is not equal to 1")

##############################

if 2 != 1: # True statement
    # This line will execute
    print("2 is not equal to 1")

elif 2 > 1: # True statement
    print("2 is greater than 1")

else:
    print("2 is equal to 1")

##############################

if 5 < 3: # False statement
    # This line won't execute
    print("5 is less than 3")

elif 4 >= 5: # False statement
    # This line won't execute
    print("4 is greater than or equal to 5")

elif 5 <= 4: # False statement
    # This line won't execute
    print("5 is less than or equal to 4")

else:
    # The program will execute these lines, since
    # the above if/elif conditions were not met.
    print("5 is not less than 3")
    print("4 is not greater than or equal to 5")
    print("5 is not less than or equal to 4")
```

### Examples

```python
age = 18

if age >= 65: # False statement
    # This line won't execute
    print("Would you like a senior discount?")

elif age < 12: # False statement
    # This line won't execute
    print("Would you like a kids menu?")

else:
    # This line will execute, since the above conditions
    # were not met.
    print("Do you have a student ID for a student discount?")

##############################

animal = "fish"

if animal == "fish": # True statement
    # This line will execute.
    print("Check if aquarium needs fresh water")

else:
    print("Check if their water bowl needs more water")
```

### Nested conditional statements

Nested conditional statements in Python take basic conditional structures a step further. They involve placing one conditional statement inside another, allowing you to create more intricate decision-making logic within your code. This nested structure is particularly useful when you need to make more specific decisions within a broader context.

The key to understanding nested conditionals is the concept of indentation. In Python, indentation is not just a matter of style; it's crucial for defining the scope of code blocks. Indentation is what visually separates one level of nesting from another. When you nest one conditional statement inside another, the inner statement is indented to indicate that it's part of the outer block.

However, while nested conditionals are powerful, it's essential to balance complexity with readability. Excessive nesting can lead to code that is difficult to understand and maintain. In such cases, it's often a good practice to add comments to clarify the purpose of each level of nesting, making it easier for you and other developers to comprehend the code's logic.

### Syntax

```python
# Basic syntax of nested conditional statements:

if 2 == 1: # False statement
    # This line won't execute
    print("2 is equal to 1")

else:
    # This line will execute, since the above condition wasn't met
    print("2 is not equal to 1")
    # The program will next evalutate this condition
    if 2 == 2: # True statement
        # This line will execute since the above condition is met
        print("2 is equal to 2")

##############################

if 2 != 1: # True statement
    # This line will execute
    print("2 is not equal to 1")

    # The program will evalutate this condition next
    if 2 == (1 + 2): # False statement
        # This line won't execute since the above condition is not met
        # Program will now exit out of the original conditional flow structure
        print("1 + 2 = 2")

elif 2 > 1: # True statement
    print("2 is greater than 1")

else:
    print("2 is equal to 1")
```

### Examples

```python
age = 18

if age >= 21: # False statement
    # This line won't execute
    print("Would you like a glass of wine with your dinner?")
    # This statement won't be evalutated
    if age >= 65:
        print("Would you like to use a senior discount?")

elif age < 12: # False statement
    # This line won't execute
    print("Would you like a kids menu?")

else:
    # This line will execute, since the above conditions
    # were not met.
    print("Do you have a student ID for a student discount?")
```

---

## Looping Constructs

Loops in Python are essential for performing repetitive tasks and iterating over data structures. Python provides two primary types of loops: the for loop and the while loop.

* For loop: The for loop is used when you have a sequence of elements, such as a list, tuple, or string, and you want to iterate through each element one by one. The loop iterates over the elements in the sequence, and you can perform specific actions for each item within the loop's block
    
* While loop: The while loop is another type of loop in Python. It is used when you want to repeat a block of code as long as a specific condition is true. The loop checks the condition before each iteration and stops once the condition becomes false.
    

### The 'for' loop

The for loop in Python is a fundamental construct that allows you to iterate through a sequence of items or elements. This sequence can be a list, tuple, string, dictionary, or any other iterable object. The for loop follows a simple and elegant syntax that provides a clear way to execute a block of code for each item in the sequence.

The primary purpose of the for loop is to automate repetitive tasks, where you need to perform the same operation on multiple items. Instead of writing the same code for each item, you can encapsulate the operation within the loop, and Python takes care of the iteration for you.

The for loop is not limited to numerical sequences; it can work with any iterable data structure, including strings, where it iterates through each character, or dictionaries, where it iterates through keys or values.

### Syntax

```python
# Basic for loop syntax:

l = [2, 4, 6, 8, 10]

for i in l:
    # Prints each element in l in sequential order
    print(i)
```

### Examples

```python
# Example nesting a conditional statement inside a for loop

lucky_number = 3
l = [1, 2, 3, 4, 5]

# Iterate through each element in l
for i in l:
    # For each element of l, check if it equals the lucky number
    if i == lucky_number:
        # This line will execute ONCE
        print("Lucky number " + str(lucky_number))
```

### The 'range()' function

The range() function in Python is a versatile and essential tool for generating sequences of numbers. It is commonly used in conjunction with for loops to iterate over a range of values. The range() function creates a special type of iterable called a range object, which represents an immutable sequence of numbers.

The range() function is not limited to for loops; you can also convert a range object to a list or use it in other contexts where iterable sequences are required. It's a valuable tool for creating and managing sequences of numbers efficiently, which is especially useful in various programming scenarios, including counting, iterating, and indexing.

The arguments of the range() function are as follows:

* **start** (optional) is the initial value of the sequence. If omitted, it defaults to 0.
    
* **stop** is the endpoint of the sequence, and the generated sequence will not include this value.
    
* **step** (optional) is the increment by which each number in the sequence increases. It defaults to 1 if not provided.
    

```python
start = 10
stop = 20
step = 2

# This loop will start at i = 10, stop executing once i = 20, 
# and increment i by 2 each iteration
for i in range(start, stop, step):
    print(i)

# Output:
# 10
# 12
# 14
# 16
# 18

##############################
# Example with just the "stop" argument
# This loop will start at i = 0, stop executing once i = 10,
# and increment i by 1 each iteration.
for i in range(10):
    print(i ** 2)

# Output:
# 0
# 1
# 4
# 9
# 16
# 25
# 36
# 49
# 64
# 81
```

### The 'while' loop

The while loop is a powerful control structure that allows you to repeatedly execute a block of code as long as a specific condition remains true. Unlike the for loop, which is ideal for iterating through sequences, the while loop is excellent when you don't know in advance how many iterations you'll need, but you do know the condition under which the loop should continue.

The loop starts by evaluating the condition. If the condition is True, the code block beneath the while statement is executed. After the block is executed, the condition is evaluated again, and the loop continues to run as long as the condition remains True.

One key feature of the while loop is its adaptability. It's not limited to counting or numeric operations; it can be used for various tasks, such as searching through data or managing program flow based on dynamic conditions. However, it's crucial to ensure that the condition in a while loop will eventually become False, or you risk creating an infinite loop, which can lead to a program becoming unresponsive or even crashing.

### Syntax

```python
# Basic while loop syntax:

x = 0
y = 10

# While this condition remains true
while x < y:
    # This loop will stop executing once x >= y
    # Each iteration, we're incrementing x by 1
    # and decrementing y by 1
    x += 1
    y -= 1
    print("x: ", x)
    print("y: ", y)

# Output:
# x:  1
# y:  9
# x:  2
# y:  8
# x:  3
# y:  7
# x:  4
# y:  6
# x:  5
# y:  5

# As you can see, this loop will eventually stop since there's a moment
# when x is no longer less than y (when x = y = 5)
```

### Nested loops

Nested loops in Python refer to the practice of placing one loop inside another loop. This approach allows you to create more complex and multi-dimensional iterations. While Python supports both for and while loops, nested loops are often used in scenarios where you need to work with arrays, matrices, or perform operations on multiple levels of data.

The key concept behind nested loops is that the inner loop completes its entire cycle for each iteration of the outer loop. This results in all possible combinations of the inner and outer loop iterations being processed. For example, if you have a list of students and a list of subjects, you can use nested loops to generate all possible combinations of students and subjects

Nested loops are also used to work with multi-dimensional data structures, like lists of lists (2D arrays) or matrices. You can use nested loops to traverse and manipulate elements within these data structures.

It's important to consider the performance implications of nested loops, especially when dealing with large datasets. The time complexity of nested loops is often proportional to the product of the lengths of the sequences they iterate over. So, if you have two nested loops, each iterating over a list of length n, the total number of iterations becomes n \* n = n^2, which can be substantial for large n.

### Syntax

```python
# nested for loop

# Outer loop will start at 1, stop at 6, increment by 1
for i in range(1, 6):
    # Inner loop will start at 1, stop at 5, increment by 1
    for j in range(1, 5):
        result = i * j
        print(i, " * ", j, " = ", result)

# Output:    
# 1  *  1  =  1
# 1  *  2  =  2
# 1  *  3  =  3
# 1  *  4  =  4
# 2  *  1  =  2
# 2  *  2  =  4
# 2  *  3  =  6
# 2  *  4  =  8
# 3  *  1  =  3
# 3  *  2  =  6
# 3  *  3  =  9
# 3  *  4  =  12
# 4  *  1  =  4
# 4  *  2  =  8
# 4  *  3  =  12
# 4  *  4  =  16
# 5  *  1  =  5
# 5  *  2  =  10
# 5  *  3  =  15
# 5  *  4  =  20


# nested for and while loop
for i in range(5):
    j = 0
    while j < i + 1:
        print("*", end=" ")
        j += 1
    print()

# Output:
# * 
# * * 
# * * * 
# * * * * 
# * * * * * 


# Nested while loop
outer_count = 1

while outer_count <= 3:
    inner_count = 1

    while inner_count <= 3:
        print("Outer Count: ", outer_count, "Inner Count: ", inner_count)
        inner_count += 1

    outer_count += 1

# Output:
# Outer Count:  1 Inner Count:  1
# Outer Count:  1 Inner Count:  2
# Outer Count:  1 Inner Count:  3
# Outer Count:  2 Inner Count:  1
# Outer Count:  2 Inner Count:  2
# Outer Count:  2 Inner Count:  3
# Outer Count:  3 Inner Count:  1
# Outer Count:  3 Inner Count:  2
# Outer Count:  3 Inner Count:  3
```

---

## Loop Control Statements

Loop control statements are essential tools for managing the flow of loops, whether they are for or while loops. These statements allow you to modify the behavior of a loop, control the iteration process, and handle exceptional conditions. In Python, there are three primary loop control statements: break, continue, and pass.

1. **break**: The break statement is used to prematurely exit a loop before it reaches its normal conclusion. When a break statement is encountered within a loop, the loop is terminated immediately, and the program continues executing the code after the loop.
    
2. **continue**: The continue statement is used to skip the rest of the current iteration of a loop and move to the next iteration. It is handy when you want to avoid executing certain code within a loop for specific iterations while continuing with the remaining iterations.
    
3. **pass**: The pass statement is a placeholder that does nothing. It's often used when a statement is syntactically required but you don't want to perform any action. It can be helpful when you're in the process of developing code and need to define a placeholder for future implementation.
    

These loop control statements give you the flexibility to handle various scenarios efficiently. They allow you to control the flow of loops based on specific conditions, skip iterations when needed, and create placeholders for future code development. By mastering these control statements, you can write more versatile and robust loops in your Python programs.

### The 'break' statement

The break statement is particularly useful in situations where you need to stop the execution of a loop based on a specific condition or handle exceptions.

When Python encounters a break statement within a loop, it immediately terminates the loop and continues executing the code after the loop.

It's worth noting that while the break statement is a valuable tool, its use should be handled with care. Misuse of the break statement can lead to unexpected program behavior or make the code less readable. As such, it's important to document the intended behavior and reasons for using the break statement when working on larger and more complex projects.

### Syntax

```python
numbers = [1, 3, 5, 7, 9, 11]
target = 7

# This loop will iterate through each element of the 'numbers' list
for number in numbers:
    # For each number in 'numbers' list, check if the number is
    # equal to the target (7).
    if number == target:
        # If the number in iteration is equal to the target,
        # print the statement below and exit the for loop.
        print("Found the target number: ", target)
        break

# Output:
# Found the target number:  7

# As you can see with the above example, the break statement allows
# us to save compute time by automatically ending the loop once
# we have the information that we need.
```

### The 'continue' statement

The continue statement is a versatile control structure in Python that allows you to skip the remaining code within the current iteration of a loop and move to the next iteration. It's particularly useful when you want to selectively exclude certain iterations from being processed within a loop based on specific conditions.

Another common use of the continue statement is to control loop behavior when processing data. For example, in data validation or data processing tasks, you may want to skip over certain entries or conditions and continue with the rest of the data.

As with any control structure, it's important to use the continue statement judiciously and document your code appropriately. Overusing continue statements or using them inappropriately can lead to code that is hard to understand and maintain.

### Syntax

```python
# syntax of the continue statement

# Start at 1, end at 11
for i in range(1, 11):
    # If i mod 3 is equal to 0, then don't do anything and continue iterating
    if i % 3 == 0:
        continue
    # This line below will only execute when the above condition is not met.
    # In other words, if i mod 3 is not equal to 0.
    print(i)

# Output:
# 1
# 2
# 4
# 5
# 7
# 8
# 10
```

### The 'pass' statement

The pass statement is a simple, yet valuable, control structure in Python that serves as a placeholder for future code. It is a no-operation statement, meaning it does nothing when executed. The primary purpose of the pass statement is to provide a syntactically required statement that doesn't perform any action, allowing you to create empty code blocks, functions, or classes without triggering syntax errors.

The pass statement is useful in several situations:

* **Creating a Placeholder**: Often, during the development of a program, you may need to define functions, classes, or blocks of code that are not yet implemented. In such cases, you can use the pass statement to create a placeholder until you are ready to add the actual code. This allows you to maintain code integrity and readability while indicating that certain parts of the program are intentionally left incomplete.
    
* **Avoiding Syntax Errors**: In Python, certain structures, such as loops or conditional statements, require an indented block of code, even if that code is empty. Without the pass statement, an empty block would trigger a syntax error. Using pass prevents such errors and allows you to maintain proper code structure.
    
* **Temporary Bypass**: The pass statement can also be used to temporarily bypass certain parts of code, helping you to debug or test your program while excluding specific sections without deleting them.
    

### Syntax

```python
# pass in if-else statement
car = {
"color": "red",
"miles": 80000,
"year": 2018}

if car["miles"] >= 100000:
    pass  # Placeholder for future code

else:
    print("Your car is still under 100,000 miles")
```

---

## Conclusion

I hope after reading this article, you now have a deeper understanding of the concept of controlling the flow of Python programs, and how to implement the best practices in controlling flow.

In this article, you learned the significance of conditional statements like 'if,' 'elif,' and 'else' in enabling the execution of different code blocks based on specific conditions. Additionally, you explored the versatility of loops, both 'for' and 'while,' in facilitating repetitive tasks.

If you have any questions or suggestions for a topic you want me to cover in the future, then feel free to leave a comment down below.

Lastly, make sure to follow my newsletter to never miss out on when I post new content!