---
title: "Comparing Search Algorithms: Linear Search vs Binary Search"
seoTitle: "Compare Linear vs Binary Search Algorithms"
seoDescription: "Investigate the linear and binary search algorithms, including Python code snippets, time complexity analysis, and pros/cons of each algorithm"
datePublished: Tue Nov 07 2023 21:05:02 GMT+0000 (Coordinated Universal Time)
cuid: clootl30r00090al97enp9ynh
slug: comparing-search-algorithms-linear-search-vs-binary-search
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/uv5_bsypFUM/upload/9a76e3e4c4a68d19e4ee2dd1c54b86f7.jpeg
tags: algorithms, python, linearsearch, binary-search-algorithm

---

# Introduction

In this article, I'm going to explain how the linear search and binary search algorithms work. In particular, I'm going to review how these algorithms operate as a general list of steps when applied to the context of searching for an element of a sorted list.

In addition, I'll be including Python code snippets for you to follow along and practice implementing these search algorithms in code.

Lastly, I'll briefly give an overview of the time complexity for both of these search algorithms and go over some advantages and disadvantages for each.

---

## I. Linear search

### a) Algorithm steps

Linear search is a very easy algorithm to implement. If you're a beginner programmer, then chances are, you've probably already implemented this algorithm without even realizing it.

The linear search algorithm works as follows:

1. Start at the first element in the list and compare its value to the target value
    
2. If they're equal, the algorithm is complete
    
3. If they're not equal, repeat step 1 with the next element in the list
    
4. If you've searched through the whole list and haven't found the target value, you know that the target value isn't in the list
    

### b) Code snippet

```python
def linear_search(array, target):
    for i in range(len(array)):
        if array[i] == target:
            return i

    # If the element isn't found, function will return -1
    return -1
```

### c) Time complexity

The worst case for linear search is if the target value isn't in the list OR the target value is the last element of the list.

In this case, we'd have to compare each element in the list to the target value, meaning that we'd make *n* comparisons.

Therefore the time complexity of linear search is:

$$O(n)$$

Time complexity graph:

<iframe src="https://www.desmos.com/calculator/b9eokg3rat?embed" width="800" height="500" style="border:1px solid"></iframe>

### d) Advantages

The main advantage of linear search is that this algorithm can be applied to both sorted and unsorted lists.

### e) Disadvantages

Of course, the biggest disadvantage of linear search is that it can be very slow and inefficient as a search algorithm.

---

## II. Binary search

### a) Algorithm steps

Binary search is easy to understand, but a little harder to implement than linear search.

Keep in mind that the binary search algorithm assumes that the list you're searching is already sorted from least to greatest (or sorted alphabetically from a-z if you have a list of strings).

The binary search algorithm works as follows:

1. Start at the middle element in the list and compare its value to the target value
    
2. If they're equal, the algorithm is complete
    
3. If the target value is greater than the middle element, then re-search the list starting with the element indexed right above the middle element
    
4. If the target value is less than the middle element, then re-search the list ending with the element indexed right below the middle element
    
5. Repeat until the target element is found
    
6. If the target value is not in the spot in the list that it should be, then you know that the target value is not in the list
    

### b) Code snippet

```python
def binary_search(array, target):
    low = 0 
    high = len(array) - 1

    while low <= high:
        mid = (low + high) // 2

        if array[mid] == target:
            return mid

        elif array[mid] > target:
            # If our target is below the middle value,
            # we'll shift the high point right below the middle
            # so our search space decreases to the bottom half of
            # the list on the next iteration
            high = mid - 1

        else:
            # If our target is above the middle value,
            # we'll shift the low point right above the middle
            # so our search space decreases to the top half of
            # the list on the next iteration
            low = mid + 1
    
    # If the target isn't found, the function will return -1
    return -1
```

### c) Time complexity

The worst case for binary search is if the element isn't in the list (similar to linear search).

For binary search though, since we're halving the search space each iteration, we don't have to search through every element in the list to know that the element isn't in the list.

The most comparisons we have to do to find out that an element isn't in the list is:

$$log_2{n}$$

Therefore, the time complexity of binary search is:

$$O(log {n})$$

Time complexity graph:

<iframe src="https://www.desmos.com/calculator/drwmtfwfbh?embed" width="800" height="500" style="border:1px solid #ccc"></iframe>

As you may remember from calculus, logarithm functions increase very slowly. Additionally, the logarithm of a variable will always be less than the variable itself.

$$log(x) < x$$

This means that for any size list, binary search will always be faster than linear search.

### d) Advantages

The main advantage of binary search is obviously that it's always faster than linear search, and is considerably faster for very large lists.

### e) Disadvantages

The biggest disadvantage of binary search is that it only works for lists that are already sorted.

This means that you'll need to apply a primary sorting algorithm to your list before applying the binary search algorithm for searching for elements from that list.

---

## III. Conclusion

I hope that after reading this article, you now have a deeper understanding of the linear search and binary search algorithms.

In this article, you learned the basic steps behind both the linear search and binary search algorithms, you followed along with example Python code snippets for both algorithms and got to see the time complexity for both algorithms.

If you have any lingering questions or suggestions for an article you want me to cover in the future, feel free to leave a comment in the comment section below.

Lastly, make sure to follow my newsletter so you never miss out on when I post new content! When you subscribe to my newsletter, you'll be able to read my articles straight from your inbox as soon as they're released.

---

![a person typing on a laptop on a desk](https://cdn.hashnode.com/res/hashnode/image/upload/v1694158493008/jsZzIo77t.jpg?w=800&auto=compress&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp align="center")

This article is part of a series called [**Bit by Bit**](https://scrappedscript.com/series/bit-by-bit), a series devoted to all things programming. Whether you're still a computer science undergrad or the CTO of Apple, there's something for you here.

New articles in this series are posted every Tuesday!