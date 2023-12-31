---
title: "Beginner's Guide to Error Handling in Python"
seoTitle: "Beginner's Guide to Python Error Handling"
seoDescription: "Beginner's guide to Python's try-except blocks, custom exceptions, and best practices for smooth program execution"
datePublished: Tue Oct 10 2023 19:51:52 GMT+0000 (Coordinated Universal Time)
cuid: clnkqn4wv000g09ji8pxh4czx
slug: beginners-guide-to-error-handling-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/bPVM4nOy0Rg/upload/b21095bbbfebba55200756fe9eb1937c.jpeg
tags: python, error-handling, exceptions

---

*Disclosure: When you purchase through links on my site, I may earn an affiliate commission. As an Amazon Associate, I earn from qualifying purchases.* [**Read the full disclosure**](https://scrappedscript.com/disclaimers)

> In this article, we discuss error handling in Python, including its importance in software development, how to work with exceptions and best practices for implementing error handling. We cover the use of try-except blocks, defining and raising custom exceptions, using additional clauses in the try-except block, and various tips for effective error handling.

---

# Introduction

![a person typing on a laptop on a desk](https://cdn.hashnode.com/res/hashnode/image/upload/v1694158493008/jsZzIo77t.jpg?w=800&auto=compress&auto=compress,format&format=webp align="center")

**This article is part of a series called "**[**Bit by Bit**](https://scrappedscript.com/series/bit-by-bit)**", a series devoted to all things programming. Whether you're still a computer science undergrad or the CTO of Apple, there's something for you here.**

**New articles in this series are posted every Tuesday!**

---

## Amazon Free Trial

[![a person holding a box with the amazon prime logo on it](https://m.media-amazon.com/images/G/01/pvc/PV1.jpeg align="center")](https://amzn.to/3RHIB0B)

**Free 30-day trial for Amazon Prime:** [https://amzn.to/46do6NE](https://amzn.to/46do6NE)

[![a woman holding a box with amazon prime on it](https://cdn.hashnode.com/res/hashnode/image/upload/v1696024499520/2a95658c-353a-4083-afba-1b1bc89b358f.jpeg?auto=compress,format&format=webp align="center")](https://amzn.to/46do9sO)

*For college students*; **Free 6-month trial for Amazon Prime Student**: [https://amzn.to/3Q6ocBg](https://amzn.to/3Q6ocBg)

---

## I. What is error handling?

Error handling is a systematic approach in programming that includes the anticipation, identification, and resolution of potential errors that may occur during the execution of a program.

On the most basic level, to effectively manage errors, programmers use methods such as including the use of error-handler blocks of code and the raising of exceptions in a program's code. This methodology not only prevents the program from crashing but also allows programmers to give some type of useful response in the form of an error message to the user.

---

## II. Overview of exceptions in Python

In Python, error handling involves utilizing try-except blocks to capture one or more exceptions or errors within a specific code segment in a program.

To catch an exception, you as the programmer have to specify which exception(s) to catch.

If you've already spent some time programming, you might've noticed that Python has a long list of predefined errors, including SyntaxError, NameError, TypeError, KeyError, AttributeError, and many more.

But what are these errors and where do they even come from?

As it turns out, just like everything else in Python, these predefined errors are just objects/classes.

![Python idle](https://cdn.hashnode.com/res/hashnode/image/upload/v1696543636803/e7d9d66a-043c-4e56-84b4-ac88dd2ef411.png align="center")

With this in mind, let's take a quick analysis of what makes up these predefined exceptions in Python.

First, if you use Python's `dir` method, you can see all of the methods and parameters that are defined for `SyntaxError`.

![Python idle](https://cdn.hashnode.com/res/hashnode/image/upload/v1696543780449/9d21a2d7-8db9-4a1d-91e7-c161ca023cbf.png align="center")

All of these methods and parameters work together to be able to reliably tell a programmer when they have a syntax error in their code.

As you can see below, when Python detects a syntax error, it automatically prints a message to the programmer: "SyntaxError: invalid syntax".

![Python idle](https://cdn.hashnode.com/res/hashnode/image/upload/v1696543987030/013cfcc9-97b8-402c-9c97-c8c005dd7ebf.png align="center")

### b) Defining custom exceptions in Python

While it's amazing that the engineers behind Python are nice enough to include these predefined exceptions in Python's native software, what if there's a very specific error that could be encountered in your program and Python's long list of predefined exceptions don't automatically detect this particular error?

Well lucky for you, you can define your very own exceptions tailored to your program :D

Before you start coding away on defining an exception class, let's see if maybe all of these predefined exceptions in Python come from somewhere else (in other words, if they have a "superclass").

![Python idle](https://cdn.hashnode.com/res/hashnode/image/upload/v1696544663218/d56270d5-3600-4a3e-8140-35e36c657e17.png align="center")

Sure enough, all of the predefined exceptions in Python inherit a base class structure from another class.

If you notice, KeyError's direct superclass is LookupError (which is just another type of exception), and LookupError's direct superclass is Exception. I included this example on purpose to show you that all of the predefined exceptions in Python ultimately inherit their base class structure from the Exception object/class.

With this in mind, we can use the same idea to quickly and conveniently define our own exceptions by inheriting the base structure from Python's Exception class and then adding in whatever custom functionality or attributes we want our specific exception to have.

```python
# Define custom exception's class and inherit
# attributes and methods from Exception class

class CustomError(Exception):
    # The pass keyword is just here as a placeholder
    pass
```

With the above code, keep in mind that the only "necessary" components are that you use the `class` keyword to define your exception as a class and that you inherit the Exception class by putting it in the parentheses after the class name (which can be named whatever you want, but it's best practice to follow the same syntactical style of Python's predefined exceptions by naming it a capitalized word followed by "Error").

And just to reiterate one of the comments I wrote in the code block, the `pass` keyword does nothing and is just there so that you don't get an error for leaving the `class` body empty.

---

## III. Overview of error handling

Now that we've covered what exceptions are, we can start learning how to work with exceptions in Python (aka, error handling).

The root of error handling in Python is using try-except blocks to "catch" exceptions.

The main idea is that by coding in unique error handling, we're either telling Python "I already know that this might give an error, and I want to handle the error in this way..." or we're telling Python "I want you to catch this potential, custom error from users, and I want to handle the error in this way...".

### a) The try-except block

The two necessary keywords in a try-except block are, unsurprisingly, `try` and `except`.

All of the code in the `try` section is technically run in Python but is not officially executed **unless** the code in the `try` section returns no error(s).

All of the code in the `except` section is **only** executed if the code in the `try` section returns an error.

You might be wondering why it's even worthwhile to catch Python's predefined exceptions. I mean, after all, it does seem redundant to catch an error that is already being caught by Python.

But in cases of catching Python's predefined exceptions, the usefulness lies in being able to customize the way the error is handled in the context of your program/software.

To illustrate this point, imagine you have a website that receives user requests for information about movies and all of the movie information is stored in your database on a server.

Let's say that this movie info is returned as JSON and is then converted to a dictionary in Python. In that case, if a user requests information about a movie that isn't listed in your database/dictionary, Python would return a KeyError (an error that's raised when you try returning a key's value for a key that doesn't exist).

Not only is this not really what's happening (the "real" error is that the movie isn't included in the database), but also this causes the program to crash.

This is a perfect example of a case where you should catch a predefined Python exception so that your program runs smoothly.

```python
# Dictionary of movie information
movies = {
        "Annihilation": {
            "year": 2018,
            "director": "Alex Garland"
        },
        "Ready Player One": {
            "year": 2018,
            "director": "Steven Spielberg"
        },
        "Interstellar": {
            "year": 2014,
            "director": "Christopher Nolan"
        } 
    }

try:
    
    # This line won't return an error
    interstellar_info = movies["Interstellar"]
    
    # This will return a KeyError since "Wall-E" isn't a key
    # in our dictionary
    wall_e_info = movies["Wall-E"]

except KeyError:

    print("The movie you requested info for isn't listed in our database :(")
```

When you execute the code above, you completely bypass Python's built-in KeyError handling/message, and instead, our custom message is what's returned. Most importantly, we're preventing the program from crashing.

![terminal window](https://cdn.hashnode.com/res/hashnode/image/upload/v1696553209668/c6317752-cb89-4ccb-964d-a59d2a0fdc3c.png align="center")

### b) Catching custom exceptions

Catching custom exceptions is the same process as catching predefined exceptions.

The only difference is that we have to first define our custom exception, as we had done earlier.

Additionally, we have to specify when our custom error is supposed to be raised.

I should note that generally, you probably won't need to define custom exceptions unless you're building some intricate software application. The reason for this is that for most general purposes, the if-else conditional statements do a good enough job of pivoting the output of a program for different use cases.

Although, I think it's still helpful to at least be exposed to the idea of being able to create/handle your own exceptions.

```python
# Define the custom exception
class CustomError(Exception):

    pass


try:
    # Raise the custom exception
    raise CustomError

# Handle the custom exception
except CustomError:

    print("Custom error message")
```

One important thing I want to note about the code example above is that it's not necessary to place the `raise` keyword within the try-except block. You can raise your custom exception at any point in the program you feel is necessary.

The only reason I included it in the try-except block is to show a simple example of raising a custom exception.

### c) Catching multiple exceptions

In Python, you can handle multiple exceptions within one try-except block.

You simply do this by defining a tuple of which exceptions to handle.

```python
try:

    raise SyntaxError

except (KeyError, SyntaxError):

    print("Custom error message")
```

If you're trying to error-handle one particular part of your program that might cause more than one type of error, then this will come in handy.

### d) The else clause

Try-except blocks have a couple of clauses that can be added but are not always necessary.

One of those clauses is the `else` clause. The `else` clause is only executed if there were no errors raised in the `try` section.

For example, if a user is trying to log in with two-factor authentication, then you'd first want to make sure that their credentials are correct when they attempt to log in before sending a code to their email/text.

```python
class UserError(Exception):

    pass

my_account = {
    "email": "email@email.com",
    "password": 12345
}

not_my_account = {
    "email": "mail@mail.com",
    "password": 123
}

def log_me_in(user):

    if user != my_account:

        raise UserError

try:
    
    # This will raise UserError
    log_me_in(not_my_account)

except UserError:

    print("Looks like you're not me!")

else:

    print("Welcome back! Enter the code we sent you")
```

When you execute the code above, the `else` clause won't execute, but the `except` clause will.

![terminal window](https://cdn.hashnode.com/res/hashnode/image/upload/v1696556035043/b49aff91-7318-4131-9fbc-d3e57bc97d64.png align="center")

Let's change the code to instead attempt to log me in instead.

```python
class UserError(Exception):

    pass

my_account = {
    "email": "email@email.com",
    "password": 12345
}

not_my_account = {
    "email": "mail@mail.com",
    "password": 123
}

def log_me_in(user):

    if user != my_account:

        raise UserError

try:
    
    # This won't raise UserError
    log_me_in(my_account)

except UserError:

    print("Looks like you're not me!")

else:

    print("Welcome back! Enter the code we sent you")
```

When we execute the code above, the UserError is not raised, so the `else` clause is then executed.

![terminal window](https://cdn.hashnode.com/res/hashnode/image/upload/v1696556152789/1f7837c9-c0fd-4a9b-88c0-a5a54a81b40a.png align="center")

### e) The finally clause

The other clause that we can add to a try-except block is `finally`.

The `finally` section executes regardless of whether an error was raised.

This might be useful in a case where the program has to release a file that was submitted by a user.

```python
class UserError(Exception):

    pass

my_account = {
    "email": "email@email.com",
    "password": 12345
}

not_my_account = {
    "email": "mail@mail.com",
    "password": 123
}

def log_me_in(user):

    if user != my_account:

        raise UserError

try:
    # This will raise UserError
    log_me_in(not_my_account)

except UserError:
    # This will execute
    print("Looks like you're not me!")

else:
    # This won't execute
    print("Welcome back! Enter the code we sent you")

finally:
    # This will execute
    print("No matter who you are, have a wonderful day!")
```

In the above code, even though UserError was raised, the `finally` section is executed.

![terminal window](https://cdn.hashnode.com/res/hashnode/image/upload/v1696556672254/0bfaa0f7-7428-4718-9852-96fb62db97c5.png align="center")

Just to show you that the `finally` clause will also execute when there isn't a UserError, let's try logging in `my_account`.

```python
class UserError(Exception):

    pass

my_account = {
    "email": "email@email.com",
    "password": 12345
}

not_my_account = {
    "email": "mail@mail.com",
    "password": 123
}

def log_me_in(user):

    if user != my_account:

        raise UserError

try:

    log_me_in(my_account)

except UserError:

    print("Looks like you're not me!")

else:

    print("Welcome back! Enter the code we sent you")

finally:

    print("No matter who you are, have a wonderful day!")
```

After executing the code above, we see that the `finally` clause is still executed.

![terminal window](https://cdn.hashnode.com/res/hashnode/image/upload/v1696556850185/0420060f-7324-4784-9a46-e4d9a4b7f88f.png align="center")

---

## V. Best practices for error handling

Whenever you're implementing error handling into your code, there are certain things to pay attention to so that you truly reap the benefits of error handling.

### a) Catching exceptions as specific as possible

First, you want to make sure that you're not taking advantage of the fact that you can catch multiple exceptions at once.

Catching mutliple exceptions isn't a tool meant to overcome laziness per se, it's a tool to be able to handle a specific part of your program that might cause more than one type of error.

Additionally, you want to make sure that you're tailoring an error response specific to your program and the nature of the error.

### b) Graceful degradation

Finally, make sure that your program is always able to run smoothly.

I don't know anyone who enjoys the moment when an app crashes for apparently no reason.

One of the most noteworthy benefits of error handling is not only that you have control over what happens when an error occurs, but you also have the control to prevent the program from crashing!

If an error is raised and it's not properly handled, you risk damaging the functionality of the rest of the program and upsetting your users.

---

## VI. Conclusion

I hope that you now have a better understanding of error handling in Python, and feel comfortable enough to start catching/handling errors and even defining/raising your own errors.

In this article, we went over the basic concept behind error handling, how to implement error handling in Python, how to define and raise custom exceptions, how to use additional clauses in the try-except block, and discussed some of the best practices when error handling.

Down below, I've linked some additional resources if you're interested in learning more about error handling in Python.

If you have any lingering questions or suggestions for a topic you want me to cover in the future, then please make sure to leave a comment down below.

Lastly, make sure to follow my newsletter to never miss out on when I post new content!

---

## VII. Additional resources

### a) Amazon Prime Free Trial

[![a person holding a box with the amazon prime logo on it](https://m.media-amazon.com/images/G/01/pvc/PV1.jpeg align="center")](https://amzn.to/3tiK6Iy)

**Free 30-day trial for Amazon Prime:** [https://amzn.to/3PLmWBT](https://amzn.to/3PLmWBT)

[![a woman holding a box with amazon prime on it](https://cdn.hashnode.com/res/hashnode/image/upload/v1696051026485/dee0034b-2580-45a5-9ae5-7a51c5e06360.jpeg?auto=compress,format&format=webp align="center")](https://amzn.to/3rE6RWQ)

*For college students*; **Free 6-month trial for Amazon Prime Student**: [https://amzn.to/45j4tT9](https://amzn.to/45j4tT9)

### b) Videos

[Exception Handling Tips in Python](https://www.youtube.com/watch?v=ZsvftkbbrR0)

%[https://www.youtube.com/watch?v=ZsvftkbbrR0] 

If you want to dive deeper into the concepts and techniques behind error handling, then I recommend checking out this video. Even if you're still a beginner, it might be beneficial to at least hear about some more advanced concepts so that you can start to think more creatively.

### c) Articles

* [Errors and Exceptions](https://docs.python.org/3/tutorial/errors.html)
    
    * This is an all-inclusive tutorial straight from the official Python docs
        
* [Python's raise: Effectively Raising Exceptions in Your Code](https://realpython.com/python-raise-exception/)
    
    * I really like the way this author talks about when/how to use custom exceptions