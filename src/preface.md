# Preface
    
Welcome to _A Remade Introduction to Rust_. 

## Why Remaking?

I am writing this book because I want to change how people learn this language. 

Right now, I am a student at Carnegie Mellon University. I am taking a course called 98-008 (StuCo: Intro to Rust Lang). "StuCo" is a special type of class where students like me are the primary teachers. Our main textbook is the [official Rust documentation](https://doc.rust-lang.org/stable/book/}). Most people just call it "The Book."

"The Book" is very famous, but I found it hard to use. This was true even though I already knew how to code in C and C++. "The Book" tries to show you every single feature of Rust at the same time. It is like trying to learn how to drive by looking at a giant map of every road in the country. When I read it, I felt "dizzy." I would read a chapter, but I could not remember what I learned five minutes later. This made me have to look back at the documentation every time I'm trying to write some code. Instead of an introductory tutorial to Rust, "The Book" functions more like an encyclopedia of all the Rust features. Just like it is almost impossible to learn Spanish from a dictionary, the documentation is not optimal for learning.

Since it is 2026, a more valuable question to think about is: why do we even need to learn a new programming language if we already have ChatGPT? I mean, you can use AI to write an entire software in Rust even without any knowledge in Rust. Before Large Language Models (LLMs) were invented, a large part of learning programming involves memorizing the syntax: you have to memorize how to write a `for` loop, how to use an array, etc., in order to write code in that language, or else you just have to constantly check the documentation. Now it's different: if you forget how to pass a vector as a parameter to a function, you can just Google it, and a perfect response crafted by AI, with the answer highlighted, is at the top. The cost of looking something up become much less, so the value of memorization consequently become less.

So what's valuable? If you have learned a programming language, think about this: why is the syntax designed like this? For example. why do variables have types? The design choices behind those syntaxes is what's valuable. It is a piece of artwork that describes how the computer is operated, that enalbes people to operate it safely and efficiently, and that serves as a bridge between human logic and machine instructions. 

## About this Book

With the landscape of the new era, I am remaking this introduction to truly bring people into Rust. I will not just list features. Instead, I will focus on the most important parts of Rust: we will look at real examples and stay with them until they make sense, and we will dive into the concepts and see what makes Rust a unique language. 

Hands-on experience is the most important part of learning a programming language, so this book aims to make you write code while learning. Instead of spending a long time on theory, you will write your first Rust program after a chapter of "why Rust" and a chapter of setting up.

At the end of each chapter, there is a lab. While there are projects like the Guessing Game or the Command Line Program in the official documentation, the amount of projects in the documentation is far less than enough. What makes learning fun is the sense of achievement of successfully doing something, so instead of the common "debug" or "fill-in-the-blank" style, you will actually have the chance to make something that you would be proud of. 

Most people do not learn Rust as their first language. For example, at CMU, most computer science students learn C in an introductory programming class called 15-122. Because of this, my book will sometimes use examples in C for analogies. Comparing Rust to C will help you see why Rust is special. Therefore, this book is primarily intended for anyone with prior programming experience in C equivalent to one semester of introductory programming course. If you know a little bit of C, this book will be easier to read. However, I will try my best to make sure people with different programming backgrounds will understand it.
