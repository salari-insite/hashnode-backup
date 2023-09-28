---
title: "Training Neural Networks: A Starter's Guide to Gradient Descent"
seoTitle: "Neural Networks Training: Gradient Descent Guide"
seoDescription: "Master neural networks using this beginner's guide covering gradient descent, optimization, cost functions, partial derivatives, gradients, and learni..."
datePublished: Thu Sep 28 2023 21:31:22 GMT+0000 (Coordinated Universal Time)
cuid: cln3owvg8000009le8vzq08ft
slug: training-neural-networks-a-starters-guide-to-gradient-descent
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1695251986785/c801fb9a-0d47-4012-b5bc-7275134b2236.jpeg
tags: artificial-intelligence, data-science, machine-learning

---

> In this article, we explore the concept of optimization in machine learning models and the math behind gradient descent. We discuss the components of gradient descent, including cost functions, partial derivatives, gradients, and learning rates. By understanding these concepts, we can improve the accuracy of machine learning models.

# Introduction

![a woman writing on a whiteboard with a marker](https://images.unsplash.com/photo-1596496181871-9681eacf9764?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1486&q=80 align="center")

**This article is part of a series called "**[**Log Base Two**](https://scrappedscript.com/series/log-base-two)**", a series dedicated to the relationship between math and computer science**.

Just to give a bit of background on my experience in math, I've **excelled** in a total of 10 college courses in math:

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

# Optimization

Imagine for a moment that you're in the process of trying to teach basic shapes to your child.

You might start by using a variety of strategies to have your child exposed to different shapes.

For example, you might use art activities, playtime, children's books, and children's TV shows to start.

Although, you start to notice that your child is most interested in shapes during playtime.

As a result, to optimize their shape learning, you start focusing more on playtime activities and techniques, and less on other strategies.

In machine learning models, computer scientists use this same concept to train neural networks and increase the accuracy of a machine learning model's output.

## Optimization in machine learning

![a computer circuit board in the shape of a brain](https://images.unsplash.com/photo-1677442135703-1787eea5ce01?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1632&q=80 align="center")

In machine learning models, the main goal is to increase the output accuracy of the model's results.

Each time we run data through a model, we go back and make adjustments to the neural network to optimize how the model learns.

One of the ways to optimize neural networks is with a technique called gradient descent.

## Overview of gradient descent

Gradient descent is a technique from multi-variable calculus.

The main idea of gradient descent is to take some function with multiple independent variables and find where that function has its lowest output value. In calculus, this lowest value is called a local minimum.

The process of gradient descent starts with taking some random input, and then moving some distance in the direction of the negative gradient. We keep iterating this step until we reach the local minimum of the function.

It's as if someone plops you in the middle of a hilly terrain with a blindfold on and your goal is to go towards the lowest nearby point in the hilly terrain. You can accomplish this by iteratively taking steps toward the direction where it feels like you're moving downhill. Eventually, after enough steps, you'll reach the local minimum.

---

# Components of gradient descent

The gradient descent algorithm has 5 main components to understand:

* **The current value of the parameter**
    

$$\theta_j$$

* **The cost function**
    

$$J(\theta)$$

* **The size of each step (this is called the learning rate in machine learning)**
    

$$\alpha$$

* **The direction of steepest descent (the partial derivative of the cost function with respect to the parameter)**
    

$$\frac{\partial J(\theta)}{\partial \theta}$$

* **The next value of the parameter**
    

$$\theta_{j+1}$$

Putting it all together in a mathematical equation:

$$\theta_{j+1} = \theta_j - \alpha \frac{\partial J(\theta)}{\partial \theta}$$

## Cost function

A cost function is a function that calculates the "cost" of one or more variables/parameters.

The cost of a function is an intuitive function to calculate the difference between predicted values and actual values.

The cost function you use in a model depends on the type of problem you're trying to solve.

If you're trying to make a prediction, then you'll use a regression cost function. Alternatively, if you're trying to classify data, you'll use a binary or multi-class classification cost function.

An example of a regression cost function is the mean absolute error:

$$\text{MAE} = \frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y}_i|$$

The mean absolute error calculates the sum of the differences between predicted values and actual values and is then divided by the amount of data points in the dataset to find the average error value.

As stated before, the cost function you use in your gradient descent algorithm will vary based on the problem you're trying to solve and the nature of your dataset.

## Gradients and partial derivatives

### Derivatives

If you've taken single-variable calculus, you're probably familiar with derivatives of single-variable functions.

$$\frac{d}{dx}f(x)$$

If not, then just understand that the main idea of a derivative is to find the rate at which a variable is changing with respect to another variable.

For example, the speed of a car is the rate, or derivative, at which the car is moving with respect to time (e.g. miles *per* hour).

### Partial derivatives

In functions with multiple independent variables, we take the partial derivative of the dependent variable with respect to an independent variable, while holding the other independent variables constant.

$$\frac{\partial}{\partial x}f(x,y)$$

For example, to find the rate at which the height of water in a glass changes, we'd take the partial derivative of the height of the glass with respect to the volume of the glass.

### Gradients

![a person holding a cell phone with a map on it](https://images.unsplash.com/photo-1604357209793-fca5dca89f97?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1528&q=80 align="center")

To encapsulate all of the partial derivatives of a function, we take the gradient of a function.

$$\nabla f(x, y) = \pmatrix {\frac{\partial}{\partial x} f(x,y) \\ \frac{\partial}{\partial y} f(x,y) }$$

The gradient of a function is a vector field that represents the direction of the greatest change of a function. Each element in the gradient vector is a single partial derivative with respect to some independent variable.

If you're not sure what vectors are, then make sure to go read my article from last week: The Matrix Is Everywhere: Linear Algebra Concepts Relevant to Computer Science.

For example, to find the direction to walk to reach the top of a hill, we'd take the gradient of the height of the hill. The first element in this gradient would tell me how far to go north or south, and the second element would tell me how far to go east or west.

In gradient descent, we take the gradient of the cost function to find the direction of the greatest error in our predictions (and then intuitively go in the negative direction so we reach the point at which the error in our predictions is minimized).

## Learning rate

The last gradient descent component to analyze is the learning rate.

In supervised machine learning models, you assign the learning rate of the model.

The learning rate ultimately controls how far the model goes in the direction of steepest descent (the negative of the gradient of the cost function).

It should be noted that the learning rate is not constant, and there are many different algorithms used to optimize the learning rate.

Similar to the cost function, the learning rate you use is dependent on the problem you're trying to solve.

If the learning rate is too small, then the training of the model will take too long.

Alternatively, if the learning rate is too large, then the model may "overshoot" the local minimum.

---

# Conclusion

In this article, we went over the very basics of the math used in gradient descent. You learned about the concept of optimization in machine learning models, the intuition behind gradient descent, and all of the components of gradient descent broken down.

If you have any lingering questions or suggestions for a topic you want me to cover in the future, then please make sure to leave a comment down below.

Lastly, make sure to follow my newsletter to never miss out on when I post new content!