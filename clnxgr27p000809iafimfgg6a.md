---
title: "An Introduction to the Binary Tree: One of the Essential Data Structures in Computer Science"
seoTitle: "Binary Tree Intro: Basic Data Structures in Computer Science"
seoDescription: "Learn about binary tree terminology, traversal (preorder, inorder, postorder, level order) with Python code, operations (insertion, deletion, searching)"
datePublished: Thu Oct 19 2023 17:35:59 GMT+0000 (Coordinated Universal Time)
cuid: clnxgr27p000809iafimfgg6a
slug: an-introduction-to-the-binary-tree-one-of-the-essential-data-structures-in-computer-science
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/Xi-yGUFC1R0/upload/11693068b567fc6279910dc4a1da654a.jpeg
tags: python, data-structures, binarytrees

---

*Disclosure: When you purchase through links on my site, I may earn an affiliate commission. As an Amazon Associate, I earn from qualifying purchases.* [**Read the full disclosure**](https://scrappedscript.com/disclaimers)

> In this article, we explore binary trees and their importance in computer science. We cover the terminology, four main traversal methods (preorder, inorder, postorder, and level order), and some basic operations such as insertion, deletion, and searching. By understanding binary trees and their applications, you can optimize data structures and improve your problem-solving skills in computer science and mathematics.

---

# Introduction

![woman writing digital logic on whiteboard](https://images.unsplash.com/photo-1596496181871-9681eacf9764?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1486&q=80 align="center")

This article is part of a series called [Log Base Two](https://scrappedscript.com/series/log-base-two), a series dedicated to the relationship between math and computer science.

Just to give a bit of background on my experience in math, I've excelled in a total of 10 college courses in math:

1. **Single-variable differential calculus**
    
2. **Single-variable integral calculus**
    
3. **Multi-variable differential and integral calculus**
    
4. **Multi-variable differential and integral calculus of vector-valued functions**
    
5. **Linear Algebra**
    
6. **Differential equations**
    
7. **Probability and statistics**
    
8. **Data analysis using R programming language**
    
9. **Multivariate statistics**
    
10. **Discrete math**
    

For a large majority of those 10 classes, I ended up with A's.

Although, before college, I struggled a lot with math in the classroom, even though math had always been my favorite subject since I was in elementary school. I found it hard to truly grasp the concepts taught because my high school teachers were too focused on skill assessment. Instead of focusing on the actual concept being taught, I was too worried about how I was going to pass the test the following week.

Once I got to college, I realized that your math grade (or any grade for that matter) truly doesn't define your potential. Further, I'd argue that your success in math *education* is heavily influenced by the quality of the teacher/professor's teaching.

My mission with this series is to show other people that math isn't so scary if you break down mathematical concepts into digestible bouts of information and investigate use cases of math in your primary field of interest (in this case, computer science). Along the way, I hope to also supplement your math education with quality content. I believe that **everyone** is capable of learning and truly loving mathematics.

**New articles in this series are posted every Thursday!**

---

[![two people surrounded by phone, tablet, and tv](https://m.media-amazon.com/images/G/01/pvc/PV_Benefits_Devices_UPDATED.png align="center")](https://amzn.to/3tul3lG)

[Prime Video Channels free trial](https://amzn.to/46T71IH)

Enjoy Thursday Night Football and other Amazon Originals, popular movies, and hit TV shows — all available with your Prime membership.

Members can also subscribe to 100+ channels and get special deals to rent or buy new release movies and more.

If you're not a Prime member yet, then start your [free 30-day trial](https://amzn.to/403dfDW) today!

[![a person holding a box with the amazon prime logo on it](https://m.media-amazon.com/images/G/01/pvc/PV1.jpeg align="center")](https://amzn.to/3FkrA5h)

---

## I. Overview of binary trees

![dead tree with branches](https://images.unsplash.com/photo-1506670223639-c9c8ab811391?auto=format&fit=crop&q=80&w=1470&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D align="center")

In math, a binary tree is a type of graph that falls under the category of trees (as implied by the name).

Due to the simplistic structure and logic of binary trees, they've played an integral role as one of the foundational data structures used in computer science.

Like all data structures, trees are simply representations of a set of data points (aka nodes) that are connected via edges.

The best way to think of binary trees is to imagine a family ancestral tree (sort of).

In a family ancestral tree, you have a hierarchy of people defined by generation. At the very bottom are the youngest, and at the very top are the oldest.

Additionally, no one in the family ancestral tree is directly connected to any family member above the level right before them (their parents). Similarly, no one in the family ancestral tree is directly connected to any family member below the level right after them (their children).

Binary trees are structured similarly but not as complicated.

To start, binary trees begin with a single node (called the root node) at the highest level of the hierarchy.

Also, instead of having 2 parents, each node in a binary tree only has 1 parent.

Finally, each node can have no more than 2 child nodes (simply referred to as the left and right child).

### a) Importance of binary trees in computer science

The entire motivation behind the study of data structures in computer science is to understand which data structures are most efficient for storing data for a particular type of application, algorithm, or task.

The idea is that by optimizing your data structure, you can shorten the time it takes to build the data structure based on the nature of your data, optimize the time it takes to add or retrieve data and optimize the size of the data structure in computer memory.

In computer science, binary trees are typically used in data compression applications, database indexing, sorting algorithms, decision trees in supervised machine learning, and much more.

## II. Binary tree terminology

```plaintext
    1 <-- root/parent node
   / \
  2   3 <-- parent/child node
 / \   \
4   5   6 <-- child/leaf node

levels: 3

__________________________

subtree with root at node 2

  2
 / \
4   5
```

### a) Node

A node is a single data point.

In the above binary tree, all of those numbers are values held within nodes.

Since binary trees are just sets, you can also think of the data within a node as being an element of the set defined by the binary tree.

### b) Root

The root of a binary tree is the node that is at the highest level within the tree.

In the above binary tree, the node containing the value 1 is the root node.

You can think of the root as being the "starting point" for the binary tree.

From the root, edges branch out to child nodes of the root, and then those child nodes of the root branch out edges to their child nodes and so on until the tree is populated with all of the data points.

The root node is the only node that doesn't have a parent node.

### c) Parent, child, and sibling nodes

A parent node is any node that has at least 1 child node. More specifically, a parent node is a parent to the node(s) in the level right below it that it's connected to via edges.

In the above binary tree, 2 is the left child of the root node and is also the parent of its left child (4) and its right child (5).

A child node is any node that has a parent node. By definition, every node in a binary tree is a child node except for the root node. Child nodes are classified even further by which side they fall under their parent node. If a child is to the left of the parent node, then it's called the "left child". Alternatively, if a child is on the right of the parent node, then it's called the "right child".

A sibling node is any child node that is connected to the same parent node as another child node. By definition, each node can have either 0 or 1 sibling node.

### d) Leaf nodes

A lead node is any node that does not have any child nodes.

In the above binary tree, the node containing the value 4 is a leaf node.

By definition, all of the nodes in the bottom level of the tree are considered leaf nodes.

### e) Level and height

In a binary tree, the hierarchy of each node about all the other nodes is determined by its level and height.

The highest level is level 1, and this is the level that contains the root node. From there, the child nodes of the root node makeup level 2 and so on.

The height of a node is defined by the longest path from that node to a leaf node. The height is measured in units of edges. So if a binary tree has 3 levels, this would mean that the root node has a height of 2 (since you'd have to traverse 2 edges from the root node to a leaf node in the bottom level). By definition, each leaf node has a height of 0.

### f) Subtree

We can break down a binary tree into subtrees where we define the root node and then build our subtree by including the edge(s) and child node(s) of that node and so on.

## III. Binary tree traversal

One important question to ask with any data structure is: what are the ways that I can sequentially list out every single data point contained in the data structure?

For binary trees, there are 4 main ways that we can traverse the tree and be able to visit each node.

Besides simply being able to return each node contained in a binary tree, tree traversals also serve as a required step in many of the operations that can be performed on binary trees as you'll see in the section further down.

### a) Preorder

The basic principle of preorder traversal is to start at the root node, then visit each node on the left side of the tree, followed by the right side of the tree.

When we do preorder traversal, we think of each node as being a root node of its own subtree. As such, the algorithm used in preorder traversal is recursive.

The preorder traversal algorithm works like this in Python:

```python
# Create node class to create nodes as objects
class Node:

    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

# Pass in the root node to begin the algorithm
def preorder_traversal(root):
    
    # Condition to stop recursion if node doesn't have child
    if root is None:
        return []
    
    result = []
    # Start at root
    result.append(root.value)
    # Recursively traverse left subtree
    result += preorder_traversal(root.left)
    # Recursively traverse right subtree
    result += preorder_traversal(root.right)

    return result

#example

#    1
#   / \
#  2   3
# / \   \
#4   5   6
# preorder traversal:
# 1, 2, 4, 5, 3, 6

root = Node(1)
root.left = Node(2)
root.right = Node(3)

root.left.left = Node(4)
root.left.right = Node(5)

root.right.right = Node(6)

print(preorder_traversal(root))
```

### b) Inorder

With inorder traversal, we start by traversing the left subtree, then the root node, followed by the right subtree.

In Python, we'd implement the inorder traversal like this:

```python
class Node:

    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

def inorder_traversal(root):

    if root is None:
        return []

    result = []

    result += inorder_traversal(root.left)
    result.append(root.value)
    result += inorder_traversal(root.right)
    
    return result

#example

#    1
#   / \
#  2   3
# / \   \
#4   5   6
# inorder traversal:
# 4, 2, 5, 1, 3, 6

root = Node(1)
root.left = Node(2)
root.right = Node(3)

root.left.left = Node(4)
root.left.right = Node(5)

root.right.right = Node(6)

print(inorder_traversal(root))
```

If you notice, the code for inorder traversal is almost identical to the code for preorder traversal, except we switched the order for two lines: `result += inorder_traversal(root.left)` and `result.append(root.value)`.

### c) Postorder

In postorder traversal, we start by traversing the left subtree, then the right subtree, followed by the root node.

With Python, we could implement postorder traversal like this:

```python
class Node:

    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

def postorder_traversal(root):

    if root is None:
        return []

    result = []
    
    result += postorder_traversal(root.left)
    result += postorder_traversal(root.right)
    result.append(root.value)

    return result

#example

#    1
#   / \
#  2   3
# / \   \
#4   5   6
# postorder traversal:
# 4, 5, 2, 6, 3, 1

root = Node(1)
root.left = Node(2)
root.right = Node(3)

root.left.left = Node(4)
root.left.right = Node(5)

root.right.right = Node(6)

print(postorder_traversal(root))
```

As you can see, postorder traversal is almost identical to inorder traversal except we switch two lines of code: `result += postorder_traversal(root.right)` and `result.append(root.value)`.

### d) Level order

Out of all the traversal methods here, level order is the most unique.

The main idea of level order traversal is to traverse the tree by level. Starting at level 1 (the root node), then visiting each node in level 2, and so on.

Since we typically don't define a node's level in programming, level order traversal relies on the use of a list traditionally called a queue. In the queue, we sequentially store the left and right child nodes of the current root node. Then, we remove the first node in the queue and recursively run the function on that first node we removed from the queue.

With Python, we could write a level order algorithm like this:

```python
class Node:

    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

def level_order_traversal(root, queue = []):

    result = []
    
    # Add in current node value
    result.append(root.value)
    
    if root.left is not None:
        # If current node has left child, add it to queue
        queue.append(root.left)
    
    if root.right is not None:
        # If current node has right child, add it to queue
        queue.append(root.right)
    
    # If there are nodes in the queue:
    if len(queue) > 0:
        # Simultaneously remove the first node from the queue
        # and define/store it in a variable
        node = queue.pop(0)
        # Recursively run algorithm
        result += level_order_traversal(node, queue)
    
    return result

#example

#    1
#   / \
#  2   3
# / \   \
#4   5   6
# level order traversal:
# 1, 2, 3, 4, 5, 6

root = Node(1)
root.left = Node(2)
root.right = Node(3)

root.left.left = Node(4)
root.left.right = Node(5)

root.right.right = Node(6)

print(level_order_traversal(root))
```

## IV. Binary tree operations

There are many different operations that we can perform on binary trees to return information about the tree, return nodes, return subtrees, or modify the data within a binary tree.

I'm going to cover some of the most basic operations that can be performed on binary trees, but again, this is not even close to being a comprehensive list of all the operations you can perform.

### a) Insertion

Insertion involves adding a new node to the binary tree while still maintaining the original structure, properties and logic of the binary tree.

To insert a node into a binary tree, we start at the root node. From the root node, we compare the new node's value with the root node's value. If the new value is less than the root node's value, compare the new node to the left child; otherwise, compare the new node to the right child. We repeat this process until we find an empty spot to place the new node in the bottom level.

### b) Deletion

Alternative to adding new nodes with insertion, we can remove nodes with deletion.

The basic principle of deletion is that when we remove a node, we're technically replacing the old node with a node that will fill the same spot in the tree that the old node was.

The node that replaces the deleted node is the lowest and rightmost node.

In practice, this is accomplished by first locating the node we want to delete and the lowest, rightmost node. After that, we assign the value of the node we want to remove to the value of the lowest, rightmost node's value. Finally, we delete the lowest, rightmost node from the tree.

### c) Searching

If we want to see if a particular node is an element of the binary tree, then we use an operation called searching.

We first choose a traversal technique, then we define our traversal algorithm to stop once the node we're searching for is the current node.

If the entire tree is traversed and the node isn't found, then we'll know that the node isn't an element of the binary tree.

## V. Conclusion

After reading this article, I hope you now understand what binary trees are and the different operations that we can perform on them.

You learned about all the different components/terminology of binary trees, the 4 main methods of traversing a binary tree, and some of the basic operations that we can perform on binary trees.

If you have any lingering questions, please feel free to leave a comment down below.

Lastly, make sure to follow my newsletter so you never miss out on when I post new content.