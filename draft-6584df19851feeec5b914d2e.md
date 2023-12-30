---
title: "An Honest Review of GitHub Copilot"
slug: an-honest-review-of-github-copilot
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/UT8LMo-wlyk/upload/6585adde93b70e5db702a81ce15e6e1b.jpeg
tags: copilot, github, productivity

---

# Introduction

In case you're not familiar, GitHub Copilot is GitHub's "AI pair programmer" that provides intelligent code completion and a chatbot capable of answering any programming-related questions.

The concept behind GitHub Copilot is to enable developers to generate code more quickly, primarily by minimizing the amount of typing needed for boilerplate code and saving time when searching for answers to questions. Instead of using Google to find a solution, you can simply enter your question into the chatbot integrated with your IDE and receive a detailed, customized answer for your program in seconds.

In this review, I will provide my honest feedback on my experience using GitHub Copilot in various contexts, such as learning a new programming language, learning and practicing machine learning in Python, and developing a personal project. I will discuss some of the standout features that I use, identify areas where I believe improvements could be made, and share my overall evaluation of Copilot.

To preface, although this is not a sponsored post, I am able to use Copilot for free as a university student. My access to GitHub's student developer pack, which includes a free Copilot subscription, is granted due to my student status. As a result, my review may be somewhat biased, as the average person would need to pay for a subscription.

In addition to the point above, as a student, my experience with Copilot may be biased because I lack professional experience as a software engineer. Consequently, I cannot attest to how Copilot would perform in a "real-world" setting.

My goal in this review is to offer insights into how Copilot functions, as well as its features and drawbacks, before someone decides to purchase a subscription for its use.

---

## The Pros: Unveiling the Strengths

GitHub Copilot is an incredibly powerful developer tool that, at times, feels as if you have an additional developer by your side, attentively observing your every move and offering assistance. This unique characteristic can be both a strength and a weakness, depending on the specific situation. In this section, we will focus on the positive aspects and strengths of GitHub Copilot, shedding light on its capabilities and potential benefits for users.

As a cutting-edge AI-powered tool, GitHub Copilot brings a wealth of knowledge and experience to the table, assisting developers in writing code more efficiently and effectively. By providing real-time suggestions and recommendations, it can help streamline the development process, reduce the time spent on repetitive tasks, and even offer insights into best practices and coding standards.

Moreover, GitHub Copilot's ability to learn from a vast repository of code and adapt to individual coding styles makes it a versatile and valuable asset for developers across various skill levels and programming languages. This adaptability allows it to cater to the unique needs and preferences of each user, fostering a more personalized and productive coding experience.

In summary, GitHub Copilot's strengths lie in its powerful AI-driven capabilities, real-time assistance, and adaptability to individual coding styles. These features combine to create a tool that can significantly enhance the development process and help users achieve their goals more efficiently. However, it is essential to consider that this level of assistance can also present challenges in certain situations, which we will explore in the following sections.

### Efficiency and productivity

![a laptop computer sitting on top of a wooden desk](https://images.unsplash.com/photo-1499750310107-5fef28a66643?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D align="center")

One of the most appealing features of GitHub Copilot is how little code I sometimes need to type. In very simple scenarios, it can suggest precisely, or almost precisely, what I intended to type. Moreover, the suggestions aren't just brief lines here and there; Copilot's recommendations can span several lines and complete entire functions. Consequently, you naturally spend less time fussing with typing boilerplate code and code that feels rudimentary to type.

For example, I recently embarked on a learning journey through the free lectures hosted on FreeCodeCamp's website, aiming to complete the certification for ["Machine Learning with Python"](https://www.freecodecamp.org/learn/machine-learning-with-python/). Throughout the entire process, I had Copilot as my trusty companion in VSCode. To my amazement, I found myself typing very little code, even when the lectures delved into more complex, code-heavy topics.

Since Copilot is trained on a vast array of code sources available online, I surmise that it may have been exposed to the code featured in these lectures, which also appears on the TensorFlow website. Regardless of whether this was the case, the experience of not having to type out any code and instead being able to concentrate on grasping the underlying concepts of machine learning was truly refreshing.

This was particularly beneficial considering that machine learning code often involves a significant amount of boilerplate code and intricate syntax that even seasoned developers aren't expected to recall by heart. In such scenarios, Copilot truly shines as an invaluable tool, enabling learners and developers to focus on understanding the principles and techniques of machine learning, rather than getting bogged down by the minutiae of code syntax and structure.

Consequently, you feel incredibly productive and efficient as a developer who is in the process of learning something new, since you can complete entire programs while also focusing on understanding the concepts.

### Accuracy and usefulness

As previously mentioned, Copilot not only provides code suggestions at every step of the development process, but it also demonstrates remarkable accuracy in specific contexts.

For example, when I used Copilot while learning machine learning in Python, I was amazed to find that Copilot's code suggestions were accurate down to the finest details, even including the exact URL of the datasets I wanted to use in my programs. This level of accuracy is truly impressive and sets Copilot apart from other tools.

![a man sitting at a table using a laptop computer](https://images.unsplash.com/photo-1456406644174-8ddd4cd52a06?q=80&w=2048&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D align="center")

In my experience, I'd estimate that for basic tasks, Copilot's suggestions are accurate about 99% of the time. This makes Copilot an incredibly valuable resource for developers, especially when compared to traditional methods like Google searches, which don't always yield accurate results quickly. With Copilot, not only is the answer available in real-time, but you can also trust that it's highly likely to be accurate.

This high level of accuracy and real-time assistance can significantly improve a developer's workflow, reducing the time spent searching for solutions and increasing overall productivity. By providing reliable and contextually accurate suggestions, Copilot has the potential to become an indispensable tool for developers of all skill levels.

### Time savings

![a close up of a person wearing a watch](https://images.unsplash.com/photo-1495704907664-81f74a7efd9b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D align="center")

Finally, let's discuss time savings. As suggested by my first point, Copilot saves a considerable amount of time that would otherwise be spent typing boilerplate code or basic code.

However, there's another significant area where Copilot demonstrates its ability to save time: documentation. By providing developers with accurate and contextually relevant suggestions, Copilot can help streamline the process of writing comprehensive documentation for software projects. This not only saves time but also ensures that the documentation is consistent, well-structured, and easy to understand.

Developers often spend a considerable amount of time researching and writing documentation to ensure that their code is easily maintainable and understandable by others. With Copilot's assistance, developers can focus more on the core functionality of their projects, while the AI-powered tool takes care of generating relevant documentation.

For instance, I recently utilized Copilot to rapidly generate documentation for several of my personal projects. I was genuinely impressed by the quality and depth of the content it produced in the README files. The AI-powered tool was able to understand the core functionality of my projects and generate relevant explanations, making it easier for others to comprehend the code and its purpose.

However, it's important to note that Copilot's documentation capabilities, while impressive, are not entirely comprehensive. This means that certain aspects of the projects were left unexplained or not covered in sufficient detail. As a result, developers may still need to invest some time in manually creating or refining documentation to ensure that all critical components and nuances are adequately addressed.

However, for kickstarting documentation, Copilot is a decent tool. I don't know about you, but documentation is typically my least favorite part of the development process, so I'll gladly accept any time savings I can get in this area.

---

## The Cons: Addressing the Limitations

This wouldn't be an honest review if I didn't discuss some of the cons and drawbacks that I personally encountered, and which I believe others may experience as well.

I will discuss 3 major cons, but keep in mind that there are plenty more that I won't be mentioning, which have been previously addressed by others in their commentary.

It's important to acknowledge that AI tools are still quite new, and as a result, they're in their early stages regarding how advanced they are at accomplishing their tasks and goals. I believe that as time goes on and these tools continue to be developed, they will only improve.

I also want to preface by saying that I don't buy into the fear-mongering that tools like Copilot will take the jobs of software engineers and developers. As these tools continue to improve, I believe they will simply be integrated into the workflow for developers, making each developer more capable and productive. Ultimately, the primary goal of these tools is to enhance developer productivity, not to create tools that will replace developers themselves.

### Ambiguous/incorrect code suggestions

### Cost

### Code quality

---

## Conclusion