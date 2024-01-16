---
title: "Reasons to Avoid Using "var" for Declaring Variables in JavaScript"
slug: reasons-to-avoid-using-var-for-declaring-variables-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/1bNQVGzuy0U/upload/3fca3613486a39e55c7195ae735ac668.jpeg

---

# Introduction

## Scope of variables declared with var

Variables declared using the `var` keyword exhibit function-scoping behavior, which is different from the block-scoping behavior of variables declared with `let` or `const`. Function-scoped variables are accessible throughout the entire function in which they are declared, regardless of the block they are defined in. This can lead to unintended issues, especially when working with nested functions or blocks, as variables declared with `var` might be accessible in places where they were not intended to be used.

In contrast, block-scoped variables declared with `let` or `const` are only accessible within the block they are defined in, providing a more predictable and controlled environment for managing variable visibility and lifetime. This helps to reduce the likelihood of encountering bugs related to variable scope and makes the code easier to understand and maintain.

## Variable hoisting

The second reason to avoid declaring variables with var is due to a phenomenon known as hoisting.

Hoisting is a phenomenon that takes place when all variable declarations are shifted, or hoisted, to the beginning of their respective scope before the code is executed. This process happens automatically by the JavaScript engine during the compilation phase. The consequence of hoisting is that variables declared with `var` can be accessed and manipulated before their actual declaration in the code, which can lead to unexpected results and make the code harder to understand and maintain.

In contrast, when using `let` and `const` for variable declarations, hoisting still occurs, but the variables are not initialized until their actual declaration is reached in the code. This creates a temporal dead zone (TDZ) between the beginning of the scope and the point of declaration, during which accessing or manipulating the variables would result in a ReferenceError. This behavior helps to prevent unintended consequences and encourages a more predictable coding environment.

## Redeclaring variables

The last significant reason to avoid using `var` when declaring variables in JavaScript lies in the fact that variables declared with `var` can be re-declared without any warnings or error messages. This lack of feedback can result in unintentional overwriting of variables, which may lead to unexpected behavior in your code and create hard-to-find bugs.

When a variable is re-declared using `var`, the original value is simply replaced with the new one, and the code continues to execute without any indication that something may have gone wrong. This can be particularly problematic in larger codebases or when working with multiple developers, as it increases the likelihood of accidentally overwriting a variable that was intended to remain constant throughout the code.

In contrast, using `let` or `const` to declare variables provides a safeguard against this issue. If you attempt to re-declare a variable that has already been declared with `let` or `const`, JavaScript will throw an error, alerting you to the potential problem and preventing the code from executing further until the issue is resolved. This behavior encourages more predictable and reliable coding practices, reducing the risk of unintended consequences and promoting a more stable development environment.

## Conclusion

In summary, although the `var` keyword in JavaScript was once the standard, its potential pitfalls make it less desirable compared to `let` and `const`.

The function-scoping behavior, hoisting peculiarities, and the possibility of re-declaration without warnings make `var` a less predictable and potentially riskier choice.

On the other hand, `let` and `const` provide block-scoping, controlled hoisting, and protection against re-declaration, fostering a more reliable and maintainable coding environment.

If you have any lingering questions or suggestions for an article you want me to cover in the future, feel free to leave a comment in the comment section below.

Lastly, make sure to follow my newsletter so you never miss out on when I post new content! When you subscribe to my newsletter, you'll be able to read my articles straight from your inbox as soon as they're released.

---

![a person typing on a laptop on a desk](https://cdn.hashnode.com/res/hashnode/image/upload/v1694158493008/jsZzIo77t.jpg?w=800&auto=compress&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp align="center")

This article is part of a series called [**Bit by Bit**](https://scrappedscript.com/series/bit-by-bit), a series devoted to all things programming. Whether you're still a computer science undergrad or the CTO of Apple, there's something for you here.

New articles in this series are posted every Tuesday!