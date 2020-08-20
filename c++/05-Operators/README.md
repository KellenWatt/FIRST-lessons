# Lesson 05-Operators

*This lesson leaves out bitwise operators, electing to not explain "insertion" 
and "extraction" operators. It also doesn't explain implicit type conversion.*

Operators are one of the most important ways to get things done at a fundamental level.
There are operators defined for all primitive types. In fact, you've encountered 3 
operaters already: the assignment operator (`=`) and the insertion and extraction 
operators (`<<` and `>>`). 

Operators are used to combine two values into some result, based on which operation 
it is. The values you use, like usual, can be literal values or variables. Note that 
operators have a certain *precedence*, meaning that certain operators are 
evaluated before others. This will be addressed per group. You can change 
precedence by surrounding an expression with parentheses.

We'll talk about the operators in a few groups: arithmetic, assignment, comparison, 
and logical.

### Arithmetic Operators
Arithmetic operators are those operations you do in math, like addition and division.
They behave more or less like one would expect, with a few exceptions that will 
be addressed. The precedence of arithmetic operators is the normal *order of 
operations*. Whenever there is a combination of floating-point and integer values,
the result will always be a floating-point value.

#### +
`+` is the addition operator. It works exactly as expected.

#### - 
`-` is the subtraction operator. It works exactly as expected.

#### \*
`*` is the multiplication operator. It works exactly as expected.

#### /
`/` is the division operator. It behaves differently for integer values and 
floating-point values.

For floating-point values, it behaves exactly as expected. For integer values, 
it performs something called *integer division*. Traditionally, when doing 
division between two integers, there's an integer quotient and an integer 
remainder. `/` returns only the quotient.

#### %
`%` is the modulo operator. This one only works for integer values. It behaves like
the other half of integer division, returning the remainder instead of the quotient.
This is commonly used to check if an integer is divisible by another integer.

### Assignment Operators
In the class of assignment operators, there is the basic assignment operator, which 
is used to update the value of a variable. There are also assignment operators which 
perform a simple operation on the variable being assigned to, then assigns the 
resulting value back to the variable.

#### +=
`+=` performs addition on the variable on the left, using the value on the right.
```c++
int n = 5;
n += 12; // n = 17
```
#### ++
`++` is a special case of `+=`, which is equivalent to `+= 1`.
```c++
int n = 5;
n++; // n = 6
```

#### -=
`-=` performs subtraction on the variable on the left, using the value on the right.
```c++
int n = 5;
n -= 12; // n = -7
```

#### --
`--` is a special case of `-=`, which is equivalent to `-= 1`.
```c++
int n = 5;
n--; // n = 6
```


#### \*=
`*=` performs multiplication on the variable on the left, using the value on the right.
```c++
int n = 5;
n *= 12; // n = 60
```

#### /=
`/=` performs division on the variable on the left, using the value on the right. 
This follows the same rules as division with respect to floating-point and 
integer values.
```c++
// For integers
int n = 61;
n /= 4;  // n = 15

// For floats and ints
double n = 61.0;
n /= 4;  // n = 15.25
```

#### %=
`%=` performs the modulo operation on the variable on the left, using the 
value on the right. This is the same as the normal modulo, which only works for
integers.
```c++
int n = 12;
n %= 5; // n = 2
```

### Comparison Operators
Comparison operators are used to compare values of similar types to each other. This 
always returns a boolean value, which can be used to comtrol how the program 
runs. How you can do this will be discussed in later lessons.

#### ==
`==` is the equality operator. This checks if the values on the left and right are equal.
This operator works for any type.
```c++
int n = 3;
bool eq  = n == 3; // eq = true
bool neq = n == 5; // neq = false
```
#### !=
`!=` is the opposite of `==`. It checks if the values on the left and right are not equal.
This operator works for any type.
```c++
int n = 3;
bool eq  = n != 3; // eq = false
bool neq = n != 5; // neq = true
```

#### \>, \>=
`>` checks if the value on the left is greater than the value on the right.
`>=` checks if the left value is greater than *or equal to* the right value.
```c++
float n = 4.0;
bool comp    = n > 4;  // comp = false
bool greater = n > 5;  // greater = true
bool compe   = n >= 4; // compe = true
```

#### \<, \<=
`<` checks if the value on the left is less than the value on the right.
`<=` checks if the left value is less than *or equal to* the right value.
```c++
float n = 4.0;
bool comp  = n < 4;  // comp = false
bool less  = n < 5;  // less = true
bool compe = n <= 4; // compe = true
```

### Logical Operators
Logical operators combine boolean values into more complex values. The precedence 
of logical operators is often very important, and will be noted.

#### || (or)
The "or" operator combines two statements that return boolean values, and returns 
`true` if either is `true`, and `false` otherwise. `||` has the lowest precedence 
of the logical operators.
```c++
false || false   // false
false || true    // true
true  || false   // true
true  || true    // true
```

#### && (and)
The "and" operator combines two statements that return boolean values, and returns 
`true` if both are `true` and `false` otherwise. `&&` has higher precedence than 
`||`, but lower than `!`.
```c++
false && false   // false
false && true    // false
true  && false   // false
true  && true    // true
```

#### ! (not)
The "not" operator negates the value of a statement that returns a boolean value.
It returns `true` if the statement is `false`, and the opposite for `false`.
`!` has the highest precedence of logical operators.
```c++
!false  // true
!true   // false
```

---

These operators are very important, but by themselves, they don't do much. We'll 
see how to use them to affect your program in the next lesson.


