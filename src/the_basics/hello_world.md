# Hello, World

For most of you, the first program you wrote when learning a new programming language is probably "Hello, World," a simple program that prints "Hello, World" on the screen. In C, it looks like this. 

```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

If you do not know C, you can ignore the code above. This is not a book that teaches you C, so we will not be going very deep into C. If you have already learned C, that's great, because we're going to write the Rust version of the program right now.


## Writing "Hello, World" in Rust

Now, we will write a "Hello, World" program in Rust. Just like any other programming languages, the source code of a program is a text file. Create a text file at any location you like, with the Rust extension ".rs". Open the text file with your favorite text editor, and we will write the code together.

Similar to C, the "main" function is also where every Rust program starts. The keyword to declare a function in Rust is `fn`, so we will write

```rust
fn main() {
    
}
```

to declare the main function in Rust. In this way, we have declared the "main" function that takes in no parameters and returns no value, similar to the "void" type in C.

The print statement in Rust that goes into the "main" function looks like this.

```rust
println!("Hello, World!");
```

This statement prints out "Hello, World!" on the screen, along with a line break. If you don't want the line break, replace "println" with "print".

Similar to C, all statements in Rust ends with a semicolon ";". However, it is probably your first time seeing an exclamation mark "!" in the print statement in a programming language (not the exclamation mark after "World", but the one right after "println"). This is because "println!" calls a Rust macro. The official document discussed macros in details in [Section 20.5](https://doc.rust-lang.org/book/ch20-05-macros.html), but right now you only need to know that macros behave differently than a function.

Congratulations, you have successfully written your first Rust program: "Hello, World".

```rust
fn main() {
    printf("Hello, World!\n");
}
```


## Compile and Run the Program

Rust is a compiled language, meaning every program must be compiled to an executable file before running. Open a terminal, and type this command to compile your program. Replace `[your file name]` with the file name of your program.

```bash
rustc [your file name].rs
```
If nothing shows up, congratulations: you successfully compiled your first program. If some text shows up, it's usually an error message. Check if you accidentally write something wrong, and fix it. The error message usually also shows what you did wrong.

After successfully compiling your code, you should see another file with the same name as your file, except that it has no extensions (if you use Windows, it has extension `.exe`). Open a terminal, and type this command to run it.

```bash
./[your file name]
```

If you see "Hello, World" printed on your screen, then the program has done its job right. 

## What's next?

We will look at variables, a way to store and process information. There's a lot of special things about variables in Rust.

