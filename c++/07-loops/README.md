# Lesson 07-loops

We've introduced `if` statements, which are incredibly useful for making your 
program change based on various factors. But what if we want to do something 
multiple times. The obvious solution is just copy-pasting the code you want to 
repeat for as many times as you want to repeat it. But if you want to run more 
or less times than you copy-pasted, things become incredibly difficult. And if 
you want to change the repeated code, you have to change it for as many times 
as you copied it. At best, this impractical, and at worst, impossible. 

Loops let you do away with the copy-pasting, and only writing your repeated 
code once. It also lets you control how many times the code is run, and change 
that while your code is running. Depending on what you want to do, there are 
two varieties of loops in C++, the `while` and the `for` loop.

Similar to `if` statements, loops introduce a new scope level.

### While loop
A `while` loop repeats until a certain condition is met. The syntax for this 
looks like this.
```c++
while(condition) {
    // Some code to repeat
}
```
where `condition` is some boolean expression. When that boolean condition 
becomes `false` the loop stops. If the condition is never `true`, the loop is
essentially skipped. If the condition is always `true`, the loop never ends.
Neither of these sound useful on their face, but they both have very practical 
applications.

A common version of the while loops is counting in a sequence. To do this, you 
can do something like this.
```c++
int i = 0;
while(i < n) { // where n is some number
    // Do something ...
    i++;
}
```
This has a variable that "counts" up to some limit, specified by `n`, which can 
be a literal or variable.

### For loop
A for loop has an initial variable, a terminating condition, and a statement that 
is evaluated at the end of every iteration. If you think this sounds kind of like 
the `while` loop example from before, you're exactly correct. A `for` loop is 
exactly equivalent to a while loop like in the example above. The syntax for this 
is as follows.
```c++
for(init; condition; iter) {
    // Do something ...
}
```
An example implementation of this is as follows
```C++
for(int i=0; i < n; i++) {
    // Do something ...
}
```
You'll notice this is very similar to the `while` loop from before. The only 
difference between the two is the scope of the iteration variable. In the 
`while` the variable's scope is outside the loop, but in the `for` loop, it's
only available inside the loop. The difference is usually irreleveant, but it's
important to know it.


### `break` and `continue`
Sometimes it's necessary to skip iterations. Depending on the goal, there are 
two different ways to do this.

#### `break`
When you want to completely stop looping, you can stop iteration by using `break`.
This is most often used combined with an `if` statement to only break under 
certain conditions. An example of this is as follows.
```c++
// This code will only print numbers up to 5
for(int i=0; i < 10; i++) {
    if(i >= 5) {
        break;
    }
    std::cout << i+1 << std::endl;
}
```

This same effect can sometimes be achieved by using a more advanced condition 
on the loop, but using `break` is usually simpler.

#### `continue`
`continue` works a bit like `break`, but instead of stopping the loop entirely, 
it just goes on to the next iteration. In a `while` loop, this skips the rest 
of the code and checks the condition again. In `for` loops, this does the same, 
but also executes the iteration statement. Examples for both types of loops 
follow.
```c++
// Only print even numbers below 10.
for(int i=1; i<=10; i++) {
    if i % 2 != 0 {
        continue;
    }
    cout << i << endl;
}
```
```c++
// Only print even numbers below 10.
int i = 1
while(i <= 10) {
    if i % 2 != 0 {
        continue;
    }
    cout << i << endl;
    i++;
}
```
