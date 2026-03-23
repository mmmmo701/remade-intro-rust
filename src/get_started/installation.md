# Installation

Now that you know why to learn Rust, let's get it onto your computer! Rust is installed using a tool called **rustup**, which manages everything for you. Find your operating system below and follow the steps.

## Linux and macOS

Open your terminal and paste the following command:

```bash
curl --proto '=https' --tlsv1.2 [https://sh.rustup.rs](https://sh.rustup.rs) -sSf | sh
```

During the process, you might see some text on the screen asking for permission. Just follow the instructions—usually, you just need to press 1 and then Enter to choose the "default" installation.

If the install is successful, you will see this message:

"Rust is installed now. Great!"

> Note for macOS/Linux users: Rust needs a "linker" to turn your code into an actual program. Since you’ve likely taken 15-122 or used C before, you probably already have one. If you get a "linker error" later when trying to run code:
> macOS: Run xcode-select --install in your terminal.
> Linux: Ensure you have gcc or clang installed (on Ubuntu, run sudo apt install build-essential).

## Windows

Installing on Windows is a bit different. Instead of the terminal, you will use a standard installer.

1. Go to the official Rust website.
2. Download the rustup-init.exe file.
3. Run the file and follow the onscreen instructions.

_Note: You may be asked to install "Visual Studio C++ Build Tools." This is normal! It provides the background libraries Rust needs to talk to the Windows operating system._


## Checking Your Work

Once the installation finishes, we need to make sure your computer recognizes Rust. Open a new terminal window (this is important so the terminal can "see" the new tools) and type:

```bash
rustc --version
```

If you see something like `rustc 1.85.0 (2026-02-20)`, you are ready to go! If you get an error saying "command not found," try restarting your computer.


## Keeping Rust Up to Date

Rust moves fast! New versions come out every six weeks. You don't need to go through this whole process again to update. Whenever you want the latest features, just run:

```bash
rustup update
```

## Having Trouble?

If something didn't work, don't worry—installation can be tricky depending on your computer's security settings. You can find very detailed troubleshooting steps on the Official Installation Page.


## What's next?
Now that the "boring" setup is out of the way, you can dive into the actual code. 
