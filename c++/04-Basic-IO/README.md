# Lesson 04-Basic-IO

*This lesson is greivously oversimplified, but file I/O and command line 
arguments are out of scope for the purposes of these lessons. It also greatly 
simplifies `cout` and `cin` usage.*

## What does IO mean?
IO, sometimes written as I/O, stands for **I**nput and **O**utput. This is an 
overarching description of how your program interacts with the outside world.
This may sound complicated, but you've already encountered it, by way of `cout`,
which printed things to the screen. Input is a little more complicated, but we'll 
talk about this.

### Output
Output is pretty simple in C++. All you have to do is write `cout`, followed by the 
insertion operator `<<`, followed by whatever it is you want to print. Like everywhere
else, the value you want to use can be a literal value, but more often it's going 
to be a variable. 

The part that makes output so simple is that the insertion operator/value pairs 
can be chained, meaning you can print multiple things at once. That looks 
something like this.
```c++
// Let's print the digits of pi the hard way!
std::cout << 3 << '.' << 1 << "4" << 15; 
// note that std::endl is optional.
```

Notice that using `std::endl` is entirely optional. If you don't use it, a newline 
won't be printed.

### Input
Input is a little more complicated, but it isn't too bad. The biggest thing about 
using input is that you have to declare a variable before you can assign to it with
input. 

In C++, `cin` is used for getting input from something called Standard Input, or 
STDIN. This is basically whatever you type into your program while it's running.
You can use `cin` to read into a varaible as follows. Note that the variable 
has to be created beforehand.
```c++
std::string name;
cin >> name;
```
Now `name` has the value of whatever you typed in. Note that you need to press 'Enter'
to tell the program when you're done entering input, otherwise it will sit there 
waiting for you forever.

If you want to see the value that `name` has, you can put a `cout` statement in 
your code to print it out.
