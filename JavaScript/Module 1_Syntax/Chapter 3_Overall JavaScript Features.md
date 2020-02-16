# Chapter 3: Overall JavaScript Features

[intro-to-javascript](https://cn.udacity.com/course/intro-to-javascript--ud803) ([backup](https://classroom.udacity.com/courses/ud803))

## Comparisons

| **Operator** | **Meaning** |
|--|--|
| < | Less than |
| > | Greater than |
| <= | Less than or Equal to |
| >= | Greater than or Equal to |
| == | Equal to |
| != | Not Equal to |
| === | Equal to (strict equality) |
| !== | Not equal to (strict equality) |

## Mathematical Expressions & Mathematical Operators
### Mathematical Expressions
### Mathematical Operators
`+`, `-`, `*`, `/` and `%`

## Logical Expressions & Logical Operators
### Logical Expressions
Here’s the logical expression used to represent Julia’s weekend plans:

```
var colt = "not busy";
var weather = "nice";

if (colt === "not busy" && weather === "nice") {
  console.log("go to the park");
}

```

> **Prints:**  "go to the park"

Notice the  `&&`  in the code above.

The  `&&`  symbol is the logical AND operator, and it is used to combine two logical expressions into one larger logical expression. If  **both**  smaller expressions are  _true_, then the entire expression evaluates to  _true_. If  **either one**  of the smaller expressions is  _false_, then the whole logical expression is  _false_.

Another way to think about it is when the  `&&`  operator is placed between the two statements, the code literally reads, "if Colt is not busy  _AND_  the weather is nice, then go to the park".

> **Logical expressions** are similar to mathematical expressions, except logical expressions evaluate to either _true_ or _false_.

```
11 != 12
```

> **Returns:**  true

You’ve already seen logical expressions when you write comparisons. A comparison is just a simple logical expression.

Similar to mathematical expressions that use  `+`,  `-`,  `*`,  `/`  and  `%`, there are logical operators  `&&`,  `||`  and  `!`  that you can use to create more complex logical expressions.

### Logical Operators

**Logical operators**  can be used in conjunction with boolean values (`true`  and  `false`) to create complex logical expressions.

By combining two boolean values together with a logical operator, you create a  _logical expression_  that returns another boolean value. Here’s a table describing the different logical operators:

| **Operator** | **Meaning** | **Example** | **How it works** |
|--|--|--|--|
| `&&` | Logical AND | `value1 && value2` | Returns `true` if **both**  `value1`  **and**  `value2` evaluate to `true`. |
| `||` | Logical OR | `value1 || value2` | Returns  `true`  if  **either**  `value1`  **or**  `value2`  (**or even both!**) evaluates to  `true`. |
| `!` | Logical NOT | `!value1` | Returns the  **opposite**  of  `value1`. If  `value1`  is  `true`, then  `!value1`  is  `false`. |

By using logical operators, you can create more complex conditionals like Julia’s weekend example.

> **TIP:** Logical expressions are evaluated from left to right. Similar to mathematical expressions, logical expressions can also use parentheses to signify parts of the expression that should be evaluated first.

### Truth Tables

**Truth tables**  are used to represent the result of all the possible combinations of inputs in a logical expression.  `A`  represents the boolean value on the left-side of the expression and  `B`  represents the boolean value on the right-side of the expression.

Truth tables can be helpful for visualizing the different outcomes from a logical expression. However, do you notice anything peculiar about the truth tables for logical AND and OR?

#### && (AND)
| **A** | **B** | **A && B** |
|--|--|--|
| `true` | `true` | `true` |
| `true` | `false` | `false` |
| `false` | `true` | `false` |
| `false` | `false` | `false` |

#### || (OR)
| **A** | **B** | **A \|\| B** |
|--|--|--|
| `true` | `true` | `true` |
| `true` | `false` | `true` |
| `false` | `true` | `true` |
| `false` | `false` | `false` |

**Truth tables**  are used to represent the result of all the possible combinations of inputs in a logical expression.  `A`  represents the boolean value on the left-side of the expression and  `B`  represents the boolean value on the right-side of the expression.

Truth tables can be helpful for visualizing the different outcomes from a logical expression. However, do you notice anything peculiar about the truth tables for logical AND and OR?

#### Short-circuiting

[](https://classroom.udacity.com/courses/ud803/lessons/3ace947b-b5f6-40c1-bc11-3ec98fd1d936/concepts/39d374f9-d917-4038-94de-bf63323c51f0#)

![Image depicting the && AND || OR truth table](https://video.udacity-data.com/topher/2016/November/5834b9be_short-circuiting/short-circuiting.png)

*In some scenarios, the value of  `B`  in logical AND and OR doesn't matter.*

In both tables, there are specific scenarios where regardless of the value of  `B`, the value of  `A`  is enough to satisfy the condition.

For example, if you look at  `A AND B`, if  `A`  is  _false_, then regardless of the value  `B`, the total expression will always evaluate to  `false`  because both  `A`  _and_  `B`  must be  `true`  in order for the entire expression to be  `true`.

This behavior is called  **short-circuiting**  because it describes the event when later arguments in a logical expression are not considered because the first argument already satisfies the condition.

### Truthy and Falsy

Every value in JavaScript has an inherent boolean value. When that value is evaluated in the context of a boolean expression, the value will be transformed into that inherent boolean value.

The paragraph above is pretty dense with information. You should probably re-read it again! ☝️

#### Falsy values

A value is  **falsy**  if it converts to  `false`  when evaluated in a boolean context. For example, an empty String  `""`  is falsy because,  `""`  evaluates to  `false`. You already know if...else statements, so let's use them to test the truthy-ness of  `""`.

```
if ("") {
    console.log("the value is truthy");
} else {
    console.log("the value is falsy");
}

```

> **Returns:**  "the value is falsy"

##### List of all of the falsy values:

1.  the Boolean value  `false`
2.  the  `null`  type
3.  the  `undefined`  type
4.  the number  `0`
5.  the empty string  `""`
6.  the odd value  `NaN`  (stands for "not a number", check out the  [`NaN`  MDN article](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN))

That's right, there are only  _six_  falsy values in all of JavaScript!

#### Truthy values

A value is  **truthy**  if it converts to  `true`  when evaluated in a boolean context. For example, the number  `1`  is truthy because,  `1`  evaluates to  `true`. Let's use an if...else statement again to test this out:

```
if (1) {
    console.log("the value is truthy");
} else {
    console.log("the value is falsy");
}
```

> **Returns:**  "the value is truthy"

##### Some examples of truthy values:

 1. true 
 2. 42 
 3. "pizza" 
 4. "0" 
 5. "null" 
 6. "undefined" 
 7. {} 
 8. []

**In summary**,
1. the Boolean value  `true`
2. strings excluding the empty string `""`
3. numbers excluding `0`
4. array
5. list
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ4MzkzMDEyXX0=
-->