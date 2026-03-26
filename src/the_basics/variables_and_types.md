# Variables &amp; Types


## The Basics of Variables

Just like any other programming languages, a variable is a box that stores some information. In Rust, the keyword to declare a variable is `let`. For example, you can write

```rust
let a = 5;
```
to declare a variable `a` with value 5. Now, when you run the program, your computer creates a "box" in a memory and store the number 5 in it. To print the value of a, we write

```rust
println!("{}", a);
```
below the declaration `let a = 5;`. You can put them in a main function to make it a complete program. 

```rust
fn main() {
    let a = 5;
    println!("{}", a);
}
```
If you did everything right, then it will output 5, the value stored in `a`.


## Types

But, here's the question: how can the computer know whether your variable stores an integer or a string? How does `println!("{}", a);` know that `a` is an integer, and output the integer instead of a club symbol in poker, the 5th character from the ASCII code?


### What is Type?

It turns out that every variable in Rust must have a _type_. Unlike languages such as C, where you have to specify the type of each variable, Rust can "guess" the type of your variables. For example, when the Rust compiler sees the declaration above, it guesses that the variable `a` has an integer type.
If you do not want Rust to guess the type of your variables, you can also specify it.

```rust
let a: i32 = 5;
```
Here, we specify the type of `a` to be `i32`, where

 - The `i` means signed integer, which means that variables of this type can store negative numbers, and
 - The `32` is the number of binary bits this variables take. Some mathematics will show that variables of this type can store numbers from \\(-2^{31}\\) to \\(2^{31} - 1\\).

For simple values like integers or strings, the compiler can guess the types even if you don't specify it. However, in the future when you encounter more complicated variables, you may have to specify their types when Rust cannot guess the types. This is because Rust is a _statically typed_ language, so it has to know the types of all variables at compile time, before running your program.


### Why Type?

Just as the preface says, LLMs like ChatGPT can memorize all types of Rust much better than you do, so what's valuable for us to think about is why Rust compiler has such a huge type system that guesses the types of your variables. This connects to the "Why Rust" chapter: the type system is one of the "safety net" of Rust. **It prevents you from accidentally doing silly things.**

For example, suppose you made this program that calculates the value of `"apple" + 3`.

```rust
let a = "apple";
let b = 3;
let c = a + b;
```
In real life, you know that "apple plus three" is meaningless. Correspondingly, if you compile the code above, it will raise an error, because the compiler guesses that `a` is a string (specifically, with type `&str`, which we will cover later), and `b` is an integer, and it knows you did something wrong because you can't add a string with an integer. Precisely, the code does not _type check_.


### A List of Rust Types

So far, we have learned one type in Rust: `i32`. There are a lot of types in Rust, and we will list some of them that store numbers here. Each of these types consists of a letter and a number. For the letter, `i` means signed integers (can be positive, zero and negative), `u` means unsigned integers (can only be non-negative), and `f` means floating point numbers (real numbers). Same as `i32`, the number indicates the number of bits taken by the variable. Below is a table of types in Rust that store numbers. Sometimes the word `size` is in place of a number, which means that the number of bits of this variable depends on the architecture of your computer. In a 32-bit computer, this type will have 32 bits; in a 64-bit computer, this will have 64 bits.

| Signed Integer | Unsigned Integer | Floating Point |
|---|---|---|
| `i8` | `u8` |  |
| `i16` | `u16` |  |
| `i32` | `u32` | `f32` |
| `i64` | `u64` | `f64` |
| `i128` | `u128` |  |
| `isize` | `usize` |  |

Besides these types that store numbers, another simple type is `char` that stores a character. For example, you can write

```rust
let c: char = 'z';
```
to store the character `'z'` into the variable `c`.

## Mutability

After learning variables in Rust, you started to write programs with excitement. You declared a variable and store a value, and then you store a different value.

```rust
fn main() {
    let my_number = 3;
    my_number = 6;
}
```

Then you received an error.

```bash
error[E0384]: cannot assign twice to immutable variable `my_number`
 --> vari.rs:3:5
  |
2 |     let my_number = 3;
  |         --------- first assignment to `my_number`
3 |     my_number = 6;
  |     ^^^^^^^^^^^^^ cannot assign twice to immutable variable
```
"Why?" you think. Then you go to read the error message. It seems like the variable `my_number` is _immutable_, and you are curious about what it means.

Here's the thing: in most languages, variables are _mutable_ by default, which means that you can change the value of variables unless you put something like `const`. In Rust, it's the opposite: variables are _immutable_ by default, which means that you cannot change the value of variables, unless you do something.

The thing to do is: add `mut` in the variable declaration.

```rust
let mut my_number = 3;
```
After adding `mut`, your program should compile now.

## An Example: A + B Problem

Using what we've learned, let's write a program together! We will write a program that takes two integers \\(a\\) and \\(b\\) from user input, and output their sum \\(a + b\\).

Taking inputs from users is extremely hard in Rust, so we won't be getting deep into much details right now. Here's a rough outline of what we'll do. 

1. We'll first prompt user by printing a prompt.
2. Then, we'll store users' inputs in the mutable variable `input` with type `String`
3. Finally, we will parse the string into an integer and store it in the variable `a` with type `i32`. 

Here, you also need to use an external libary `std::io`, this is like `#include` in C or `import` in Python.

```rust
// use the external library std::io
use std::io;

fn main() {
    // print out a prompting message
    println!("Please input the first number. Then press Enter");

    // declare `input` as a variable of type `String`
    let mut input = String::new();

    // read from keyboard and store the string in input
    io::stdin().read_line(&mut input).expect("Failed to read line");

    // parse the input string into an integer and store it in a
    let a: i32 = input.trim().parse().expect("Invalid integer input");
}
```

You do not need to understand the details of the code right now, as we will go through more advanced topics such as functions and error handling. After you completed later chapters, you can come back to see it.

Now, we will do the same thing for `b`.

```rust
use std::io;

fn main() {
    println!("Please input the first number. Then press Enter");
    let mut input = String::new();
    io::stdin().read_line(&mut input).expect("Failed to read line");
    let a: i32 = input.trim().parse().expect("Invalid integer input");
    
    println!("Please input the second number. Then press Enter");
    let mut input2 = String::new();
    io::stdin().read_line(&mut input2).expect("Failed to read line");
    let b: i32 = input2.trim().parse().expect("Invalid integer input");
}
```

Next, we will declare a new variable `c`, and store the value of `a + b`.

```rust
let c = a + b;
```

Using things about type inferences we've learned, the Rust compiler will "guess" that `c` has type `i32`, so it doesn't matter whether or not we specify the type. If we do, it will look like this.

```rust
let c: i32 = a + b;
```

Finally, print the value of `c`, and enjoy your result!

```rust
use std::io;

fn main() {
    println!("Please input the first number. Then press Enter");
    let mut input = String::new();
    io::stdin().read_line(&mut input).expect("Failed to read line");
    let a: i32 = input.trim().parse().expect("Invalid integer input");
    
    println!("Please input the second number. Then press Enter");
    let mut input2 = String::new();
    io::stdin().read_line(&mut input2).expect("Failed to read line");
    let b: i32 = input2.trim().parse().expect("Invalid integer input");

    let c = a + b;
    println!("{}", c);
}
```

