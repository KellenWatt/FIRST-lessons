# Lesson 06-Branching

In programming, it's rarely useful to have code that can only do one thing. 
Instead, you often have to change program behaviour based on changes in the 
environment, like input or randomness.

### If statements
`if` statements are the fundamental form of decision-making in C++. An `if` 
statement executes a block of code if a condition is true. A "condition" is 
any statement that returns a boolean operator, including comparisons and 
any logical operators previously mentioned. The syntax of an `if` statement is 
as follows.
```c++
if condition {
    // Code run if condition is true
}
```
where `condition` is some sort of expression that returns a boolean value.

Code inside an `if` statement will only be run if the conditino is true. When
the condition is false, the code is simply skipped.

### Else clauses
It's possible to use multiple `if` statements to cover all possible conditions 
in any situation, but often this is tedious. For situations like this, you 
can use the `else` clause with an `if` statement.  An `else` clause executes if 
the condition of the associated `if` statement is `false`. This looks like this:
```c++
if condition {
    // Code run if condition is true
} else {
    // Code run when condition is false
}
```
Note that if the condition is `true`, the code in the `else` clause won't be run, 
and if the condition is `false`, the code in the `if` clause won't run.

An `else` clause is always optional, and sometimes it isn't necessary, so if it 
wouldn't do anything, you don't have to include it.

#### else if
Sometimes it's necessary to check multiple conditions, and this can be done using
an `else if` clause. An `else if` clause allows you to add an additional condition 
to check for in a given `if` statement. This looks like teh following.
```c++
if condition {

} else if otherCondition {

} else {

}
```
Like previous sections, only the first block with a `true` value will be executed. 

You can use multiple `else if` clauses, which can be inserted like the `else if` is
to a normal `if ... else` statement.

It's important to note that the conditions are checked in order, vertically. This 
means that if `condition` is `true`, then `otherCondition` will never be checked, 
and consequently the `else if` clause will never run. This applies no matter how 
many `else if` clauses you use. Also, no matter how many clauses you have, the 
`else` clause will be run if all conditions are false.

### Switch statement
In cases where you are checking a single varaible agianst a lot of differnt values, 
instead of using an `if ... else if ... else` chain, you can use a `switch` statement
instead. A `switch` statement has  the following format.
```C++
switch value {
case literal_1:
    break;
case literal_2:
    break;
.
.
.
default:

}
```
There's a lot to unpack here. The basic part is the `switch` on the first line. The 
`value` here can be anything, though it's almost always a variable. This value 
is checked for equality against the literals in each of the `case`s. The literals 
can be any value of the same type as `value`. The `default` case is similar to 
`else` in that it runs when none of the other cases match.

Note the `break` statement in each of the cases. By default, `switch` statements 
do something called "fallthrough". This means that when a case is matched, it 
and every case after it will be run. If you include a `break` statement, that case
will end at the `break`, and it won't fall through, which is usually the 
desired behaviour. 

Note that a `break` is not required for `default`, since it's the last case, 
and falling through means reaching the end of the `switch` statement. This is 
also true for if you don't use a `default` and the last case is a `case`. However,
it's a good practice to always break from `case`s, unless you have a good reason to 
do otherwise, specifically when fallthrough is desired behaviour (this isn't common).


## Scope
When you define new variables, they have something called a *scope*. A variable's 
scope is the part of your code that it's visible to. This is determined by what 
*block* it's declared in. With the `if` and `switch` statements, we now have 
something other than `main` that introduces a new scope. An easy way to think 
about it is that any curly-bracket pair introduces a new level of scope. A scope's 
level is determined by how many curly bracket pairs surround it. That is `main` 
is first level, or top level, and an `if` statement in `main` is second level. 
An `if` statement inside that is third level, and so on.

This is important because variables declared for an inner scope are not available 
to the program outside of that scope, but variables are available to any scope 
deeper than the one they are declared in. This is illustrated as follows.
```c++
int main() {
    int x = 1;
    if someCondition {
        int y = 2;
        // x and y are visible here, so we can use both.
    }
    // Only x is visible here. If we try to use y, the code won't compile.
}
```
It's important to note that variables declared in different scopes of the same 
level will not be visible to each other, since only one can exist at a time. 
This is illustrated in the following examples.
```c++
int main() {
    if condition {
        int x = 1;
        // y won't be visible here because
        //   1) it hasn't been declared yet.
        //   2) it's in a differnt scope. 
    }

    if otherCondition {
        int y = 2;
        // x won't be visible here because its in a different scope.
    }
    
    // Neither x nor y are visible here because they were declared in an inner scope.
}
```
This also applies to `if/else` chains.
```c++
int main() {
    if condition {
        int x = 1;
        // y won't be visible here because
        //   1) it hasn't been declared yet.
        //   2) it's in a differnt scope. 
    } else {
        int y = 2;
        // x won't be visible here because its in a different scope.
    }
    // Neither x nor y are visible here because they were declared in an inner scope.
}
```
