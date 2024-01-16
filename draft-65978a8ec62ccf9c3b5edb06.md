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