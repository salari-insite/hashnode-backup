---
title: "Comparing Data Structures: Lists vs Linked Lists"
seoTitle: "Data Structures: Lists vs Linked Lists Comparison"
seoDescription: "Investigate lists, linked lists in programming; understand their properties, pros, cons, and Python manipulation"
datePublished: Tue Nov 21 2023 16:51:42 GMT+0000 (Coordinated Universal Time)
cuid: clp8kp7w2000209kyd6yy8qkh
slug: comparing-data-structures-lists-vs-linked-lists
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/BW0vK-FA3eg/upload/908ca908b79a4463343f88adf6155d3e.jpeg
tags: python, data-structures, linked-list, 2articles1week

---

# Introduction

> In this article, we explore the similarities and differences between lists and linked lists, two common data structures in programming.
> 
> We discuss their characteristics, advantages, and disadvantages, as well as how to create and manipulate them in Python. By understanding the strengths and weaknesses of each data structure, you can make informed decisions on which to use for your specific tasks.

---

## I. Lists

Lists consist of ordered, mutable elements. They enable simple insertion, deletion, and traversal of elements while offering dynamic resizing capabilities.

With lists, all elements are stored contiguously in memory. This characteristic enables lists to quickly return elements at a specified index.

In many programming languages, lists are a built-in data structure. This means that you don't have to manually create lists and their associated methods.

### a) Creating a list in Python

```python
# Creating an empty list
new_list = []

# Creating list with values
names = ['Jack', 'Jill', 'Jane', 'Jeff']

# Creating list with 'list' function
# (Python requires iterable argument)
digits_set = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}
digits_list = list(digits)
```

In the final example of creating a list in Python, we needed to provide an iterable data type, such as a tuple, string, set, or dictionary.

Python converts the iterable data type into a list.

For tuples and sets, this simply means that Python converts all the elements directly into a list while maintaining the same order.

For strings, Python slices the string into individual characters and creates a list element for each character in the string.

For dictionaries, Python creates a list element for each key in the dictionary.

### b) List methods

* append(*el*) - adds *el* to the end of the list
    
* insert(*index*, *el*) - adds *el* to specified *index* (shifts the elements to the right by 1 index)
    
* remove(*el*) - removes the first instance of *el* in the list
    
* pop() - removes the last element of the list, and returns the element it removed
    
* clear() - deletes all the elements from the list
    
* index(*index*) - returns element at the specified *index* (this can also be done with square bracket syntax: `l[index]`)
    
* count(*value*) - returns the number of elements that contain the value *value*
    
* sort() - sorts the list from least to greatest (or alphabetically for a list of strings)
    
* reverse() - sorts the list from greatest to least (or reverse alphabetically for a list of strings)
    

### c) Advantages

The primary advantage of lists lies in their simplicity and the fact that they come pre-built in most programming languages.

Secondly, lists provide quick access to elements at a specified index, as they are stored contiguously in memory.

This means that the time complexity of indexing an element in a list is constant:

$$O(1)$$

### d) Disadvantages

The primary drawback of lists is that they are somewhat slow when it comes to removing and inserting elements at specific indices.

This is due to the necessity of shifting all elements to maintain contiguity in memory, which results in slower insertion and removal of elements at specific indices.

This means that the time complexity for removing and inserting elements in a list is linear:

$$O(n)$$

## II. Linked lists

Linked lists are a data structure composed of nodes, with each node containing an element and a reference to the subsequent node in the sequence. This enables efficient insertion and deletion of elements at any position but demands more memory and offers slower element access compared to lists.

Unlike lists, linked lists are not built-in data structures, which means you will need to manually code and create linked lists along with their associated methods.

### a) Creating a linked list

```python
# Class to construct new nodes
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

# Class to construct new linked lists
class LinkedList:
    def __init__(self):
        self.head = None
    
    # Method to add new nodes to linked list
    def append(self, data):
        # If linked list is empty
        if self.head is None:
            self.head = Node(data)
            return

        last_node = self.head
        while last_node.next is not None:
            last_node = last_node.next
        last_node.next = Node(data)

# Example usage:
linked_list = LinkedList()
linked_list.append(1)
linked_list.append(2)
linked_list.append(3)
```

### b) Linked list methods

All the methods you've seen for lists can be adapted for linked lists; however, you'll need to manually code each method yourself.

### c) Advantages

The primary benefit of linked lists lies in their efficiency when it comes to inserting and removing nodes.

Since nodes are not stored contiguously in memory but are instead referenced or pointed to by the previous node, this allows for constant-time insertion and removal of nodes.

Thus, the time complexity for inserting and removing nodes in linked lists is:

$$O(1)$$

### d) Disadvantages

The primary drawback of linked lists is retrieving the value of a node at a specific index.

Since the nodes are not stored contiguously in memory, it means that to retrieve a node at a specific index, we must start at the first node and continue iterating through the linked list until we find the desired node.

Thus, the time complexity for retrieving a node at a specific index is linear:

$$O(n)$$

If you wish to learn more about the linear search algorithm, I have written a comprehensive article comparing and contrasting linear search and binary search algorithms: [Comparing Search Algorithms: Linear Search vs Binary Search.](https://scrappedscript.com/comparing-search-algorithms-linear-search-vs-binary-search)

%[https://scrappedscript.com/comparing-search-algorithms-linear-search-vs-binary-search] 

In the article, I discuss the reasons why binary search is faster than linear search.

After reading the article, please leave a comment below with your answer to the question: *Can we use the binary search algorithm for a linked list?*

## III. Conclusion

I hope that you now understand the similarities and differences between lists and linked lists.

Both lists and linked lists have their own set of advantages and disadvantages.

This means that it's important to consider the task(s) you want to solve before choosing whether you want to implement a list or linked list.

If you want to primarily be able to index elements, then a list may be the better option. On the other hand, if you want to primarily be able to insert and remove values from specific indices, then a linked list is the better option.

If you have any lingering questions or suggestions for an article you want me to cover in the future, feel free to leave a comment in the comment section below.

Lastly, make sure to follow my newsletter so you never miss out on when I post new content! When you subscribe to my newsletter, you'll be able to read my articles straight from your inbox as soon as they're released.

---

![a person typing on a laptop on a desk](https://cdn.hashnode.com/res/hashnode/image/upload/v1694158493008/jsZzIo77t.jpg?w=800&auto=compress&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp align="center")

This article is part of a series called [**Bit by Bit**](https://scrappedscript.com/series/bit-by-bit), a series devoted to all things programming. Whether you're still a computer science undergrad or the CTO of Apple, there's something for you here.

New articles in this series are posted every Tuesday!