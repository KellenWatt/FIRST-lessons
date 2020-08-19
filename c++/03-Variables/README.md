# Lesson 03-Variables

## Data Types
Data type is a description of what piece of data means. In programming, all values
are technically just 1s and 0s, but a data type gives those 1s and 0s meaning
based on their position and order.

*Everything that follows is a gross oversimplification.* <br>
There are 4 basic types in C++, and each type has various flavors that each have 
different limitations, detailed below.

#### 1. Integrals
This is probably one of the most common types, since integers are widely used. They
come in 3 different flavors in C++: `short`, `int`, and `long`. Each flavor has a
different number of *bytes* it can store, and consequently different amounts of data.
See the table below for more information.

|   Type   | Size (in bytes) | Minimum value | Maximum value |
| -------- | --------------- | ------------- | ------------- |
| `short`  |        2        |    -32768     |     32767     |
|  `int`   |        4        |  -2147483648  |   2147483647  |
|  `long`  |        4-8      |  -2^63 - 1\*  |   2^63\*      |

\* Sizes listed are for 8-byte representations.

Suffice it to say, `int` will probably be enough for any practical purposes. 
`int` is also usually the most common because it's the easiest to understand.

You can write an integral value by simply writing an integer. This will 
automatically have an integral type.

#### 2. Floating-Point Numbers
Since computers have limited space and limited power, they can't precisely 
represent decimal numbers, rational or irrational. However, they can approximate 
them. This is what a floating-point type is: a size-limited representation 
of a decimal number. This comes in two flavors which, like the integers, can hold 
different amounts of data, and in this case, different degrees of precision.

|   Type   | Size (in bytes) |      Precision     | Approximate range |
| -------- | --------------- | ------------------ | ----------------- |
| `float`  |        4        |  ~7 decimal places |   ±3.4 * 10^±38   |
| `double` |        8        | ~15 decimal places |   ±1.8 * 10^±308  |

The most common of the two is `double` since it is significantly more precise.

You can write a floating-point number by simply writing any number, including 
a decimal point. This includes integers. If you use a "." at the end of an integer,
it now counts as a floating-point number.

#### 3. Boolean
This particular type is much simpler than other types. A boolean, or `bool`, 
represents a value that is `true` or `false`, and nothing else. This may not 
seem all too useful at first glance, but it's incredibly powerful for controlling 
how your code behaves based on certain conditions. We'll get to how you can do 
this later.

A `bool` has exactly two possible values, which are `true` and `false`. These 
usually are the result of some sort of comparison, like `1 < 2` (`true`) or `3 ≠ 3` (`false`).

#### 4. Strings
*This information is grossly simplified so as to not deal with pointers or NTCAs.*
A `string` is a sequential collection of characters that form some kind of text. 
A string can be written by using a pair of double quotes (""), surround 0 or more 
characters. A character is anything you can type, including spaces, punctuation,
normal letters, etc.

The type you use to refer to a string is `std::string`. Note the `std::` part. `string`
is a complex type called a *class* which we'll cover later. All you need to know 
for know is that you need to prefix it with `std::` and you need to use 
`#import <string>` to have access to it. We'll talk about why this is much later.

When you want to represent a single character, this uses the `char` type. You can 
write a `char` value by using a single character, surrounded by single-quotes ('').
This isn't necessarily something you'll use often, so this is more of a curiosity.

**Sidebar**: The concept of "letters" doesn't really exist in programming. Instead, 
we refer to everything as a character. Since all text is technically represented
the same way with no special meaning, "letter" doesn't mean anything.


## Variables
Having various data types are important, but without a way to hold that data,
they're worthless. This is where variables come in. Variables are things with a 
type that hold some kind of data of that type. This is similar to variables in 
math, in the sense that a variable is some kind of name that has a value associated 
with it.

### Declaration
You can create a variable, or *declare* it, by giving it a name and a type, and possibly 
an initial value. This looks like the following.
```c++
int num = 4;
```
Taking this apart, we see four parts to this line. 
First, there's the type of the variable. In this case that's `int`, but it can be 
anything that is a type. Second, we have a name. This is the name of the variable, 
and it's how we'll refer to that particular variable from here on out in our code. 
Note that the name itself doesn't matter, and can be anything, as long as we 
refer to it consistently in our code. Next is the equals sign, which indicates that
we are assigning an initial value to the variable. Finally, we have a value. This
can be anything that resolves to a value, like a literal value or another variable.

In any variable declaration, assigning an initial value is optional, which means you 
can drop the equals sign and the right side of the equals sign, not including the 
semicolon.

### Using a variable
Using a variable is the easiest thing in programming. All you have to do is write 
the variable's name, and when your code is running, it will have the value you've 
given it up to that point.

### Assigning to a variable
A variable wouldn't exactly be *variable* if it couldn't change. The way to do that
is as follows, on the second line.
```c++
double pi = 3 // Wait, pi is 3.14, not 3
n = 3.14
```
To assign a new value to a variable, you can simply write its name, then an equals 
sign, then the new value. The new value has the same rules as assignment mentioned
above, and can be a literal value or another variable.




