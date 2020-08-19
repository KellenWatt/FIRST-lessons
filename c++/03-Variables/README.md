# Lesson 03-Variables

## Data Types
Data type is a description of what piece of data means. In programming, all values
are technically just 1s and 0s, but a data type gives those 1s and 0s meaning
based on their position and order.

*The following is a gross oversimplification.* <br>
There are 4 basic types in C++, and various flavors of those types that each have 
different limitations.

#### 1. Integrals
This is probably one of the most common types, since integers are widely used. They
come in 3 different flavors in C++: `short`, `int`, and `long`. Each flavor has a
different number of *bytes* it can store, and consequently different amounts of data.
See the table below for more information.

|   Type   | Size (in bytes) | Minimum value | Maximum value |
| -------- | --------------- | ------------- | ------------- |
| `short`  |        2        |    -32768     |     32767     |
|  `int`   |        4        |  -2147483648  |   2147483647  |
|  `long`  |        4-8      |  -2^63 - 1\*  |   2^63\*      |<br>
\* Sizes listed are for 8-byte values

Suffice it to say, `int` will probably be enough for any practical purposes. 
`int` is also usually the most common because it's the easiest to understand.

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

#### 3. Boolean
This particular type is much simpler than other types. A boolean, or `bool`, 
represents a value that is `true` or `false`, and nothing else.
