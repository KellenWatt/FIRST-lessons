# Lesson 02-Intro
## A simple example

### Code example
The following is an example of C++ syntax.
```c++
#include <iostream>

int main() {
    std::cout << "Hello, world!" << std::endl;
}
```
#### Line-by-line explanation
**Line 1:** `#include <iostream>` includes the `iostream` *header*, which is used for input 
and output. Here it's used for `cout`, which is used to print "Hello, world!", and `endl`, 
which prints a newline.

**Line 2:** C++ ignores whitespace in most cases, so feel free to as much in as makes your 
code readable.

**Line 3:** `int main()` declares the `main` function, which is the starting point of every
C++ program. All code between `{` and `}` after `main` will be executed. We'll talk about 
functions more later, so don't worry about this too much. Just know that every
C++ program needs a `main` function.

**Line 4:** There's a lot going on here, so we'll address each part individually.
`std::cout` (pronounced "see-out") is a value that represents something 
called Standard Output or STDOUT. The `<<` is called the insertion operator, which 
essentially injects the value on the right into `cout` and printing it to the screen.

The part in the double quotes is called a *string*. We'll talk about this more later, but a 
string is essentially a line of text, or a sequential group of *characters*.

`std::endl` basically adds a newline to the end of whatever is being put in `cout`.

Note that every statement in a C++ program has to end in a semicolon. A statement roughly
equates to a line of code. In some way, it does some function that alters the state of
the program.

You'll notice the `std::` part is repeated for `cout` and `endl`. This is because `std` is 
something called a *namespace*. We'll talk about what a namespace is later. Just know that 
it always needs to prefix `cout`, `endl`, and a few other things that will come up later.

**Line 5:** Just ending `main` with a curly brace. All braces, including parentheses, 
square brackets, and curly braces must be part of a matched pair. Every opening must
have a closing.

