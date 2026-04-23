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


