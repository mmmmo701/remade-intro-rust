# Control Flow

## The `if` Statements

So far, what we have learned allows us to write Rust programs that do things sequentially, such as printing strings, or using variables. What if we want our programs to do different things depending on some conditions? If you have learned a programming language before, you might remember the `if` statement from your language that does such things. In Rust, there is also an `if` statement, and it's a little more powerful than most other languages.

### The Usual Way

Same as most other language, the condition goes after the `if`, and what happens goes inside the bracket.

```rust
if [condition] {
    [what happens];
}
```

Note that I did not wrap the condition around a parenthesis. This is because it is the standard style of Rust.

You can also use `else` to state "if something not happens". For example, if you want to make a program that determines whether or not a student passes a class, you write something like this.

```rust
fn main() {
    let score = 70;
    if score >= 60 {
        println!("pass");
    } else {
        println!("fail");
    }
}
```
This program declares the variable `score` and initializes it with value 70. Then, if `score` is bigger than or equal to 60, then prints out `pass`. Otherwise, it prints out `fail`. Therefore, if you run this program, it should print out `pass`. To make it truly interact with human, you can also modify it so that the user inputs the score using the way described at the end of the previous section. 

### The Unusual Way

So, what's special about the `if` statements in Rust if it's just the same as all other languages? You will see the answer here. 

In Rust, you can not only branch on instructions, but also branch on expressions. For example, if I declare a variable like this:

```rust
let bonus = if bug < 5 { 100 } else { 0 };
```

then it is equivalent to saying

```rust
let mut bonus;
if bug < 5 {
    bonus = 100;
} else {
    bonus = 0;
}
```

Why do we care that we can write it like this? 

1. **Safety**: Imagine you write code using the second way, and you forgot to write the `else` branch, and your program will have bugs. Even worse, if you are writing it in C, there will be undefined behaviors! In Rust, these problems are solved by using the first way.
2. **Immutability**: Notice that in the first declaration the variable `bonus` is immutable, but in the second declaration `bonus` must be mutable. By writing an `if` expression using the first way instead of an `if` statement using the second way enables us to initialize an immutable variable based on different cases. By keeping the variable `bonus` immutable, it ensures that the variable will not be changed later.
3. **Efficiency**: The compiler will usually compile the first way into faster instructions than the second way.




## Loops

Loop means repeatedly doing something in a program. If you have used [Scratch](https://scratch.mit.edu), you might remember using a block called "repeat 10" or "repeat until". If you have learned a programming language like C, you might have learned the "for" loop and the "while" loop. There are also "for" loops and "while" loops in Rust, and there is even more loops besides them. We will start with what you are familiar with.

### The "For" Loop and the "While" Loop

While loops are almost identical to those in C. The condition goes after the "while" keyword", then you use a pair of curly braces to indicate what is repeated. For example,

```rust
let mut val = 0;
while val < 10 {
    println!("{}", val);
    val += 1;
}
```

This will print out numbers from 0 to 9 (inclusive).

Instead of the C style, "for" loops are more like Python style. The way you use it is "for [variable] in [range]". For example, to do the same ting: printing out numbers from 0 to 9 using a "for" loop, this is how you would do it.

```rust
for i in 0..10 {
    println!("{}", i);
}
```

If you want to make it print out 0 to 10 instead, change `0..10` to `0..=10`.

### "Continue" and "Break"

Consider this task: someone lets you print out numbers from 0 to 9, but he said he does not like the number 4. How would you skip it? The answer is using `continue`. When `continue` instruction is executed inside a loop, it immediately goes to the next iteration. The program below prints out numbers from 0 to 9, except 4. 

```rust
for i in 0..10 {
    if i == 4 {
        continue;
    }
    println!("{}", i);
}
```

Now, imagine your friend says: once the next number you are going to print is greater than 6, exit the loop immediately. How would you do that? The answer is using `break`. This program prints out numbers from 0 to 6, because when `i >= 7`, the `break` instruction is executed.

```rust
for i in 0..10 {
    if i >= 7 {
        break;
    }
    println!("{}", i);
}
```

This might look silly for now as we can just do `for i in 0..6`, but `break` will have its own use when we write programs that are more complex.

### The "Loop" loop

In Rust, the "loop" loop is like the `while(true)` loop in C. It repeatedly executes its body. For example,

```rust
loop { 
    println!("I live."); 
}
```

prints out `I live` continuously until you manually stops the program. 

Another powerful use of the "loop" loop is that the loop itself can be a value. For example, if you want to print out numbers fron 0 to 9, while setting the variable `a` to the sum of everything you printed, you can do the following.

```rust
let mut sum = 0;
let mut i = 0;
let a = loop {
    if i >= 10 {
        break sum;
    }
    println!("{}", i);
    sum += i;
    i += 1;
}
```

Same thing: this might look silly for now as we can just achieve the same goal using the program below, but the `loop` loop will also be useful when we write program that are more complex.

```rust
let mut a = 0;
for i in 0..10 {
    a += i;
}
```
