# Day 03

## Plan

- Booleans
- Conditionals
- `while`
- `for`

## Boolean Expressions

A **boolean expression** is an expression that is either `True` or `False`.

The double equal sign `==` is the comparison operator.

```python
>>> 5 == 5
True
>>> 5 == 6
False
>>> type(True)
<class 'bool'>
>>> type(False)
<class 'bool'>
>>> bool(0)
False
>>> bool(1)
True
>>> bool("hello")
True
>>> bool(None)
False
>>> bool(42)
True
```

## Comparison Operators

```python
>>> x = 5
>>> y = 6
>>> 
>>> # == is the comparison operator
>>> #  = is the assignment operator
>>>
>>> print(x == y)
False
>>> print(x != y)   # not equal
True
>>> print (x > y)
False
>>> print(x < y)
True
>>> print(x <= y)
True
>>> print(x >= y)
False
>>> 
>>> ## String Comparisons
>>> s1 = "abb"
>>> s2 = "abc"
>>> 
>>> print(s1 == s2)
False
>>> print(s1 < s2)
True
>>> print(s2 > s1)
True
>>> # String comparison is done by lexicographic ordering
>>> 
>>> # strings and ints cannot be compared
>>> print("a" > 5)
Traceback (most recent call last):
  File "<pyshell#24>", line 1, in <module>
    print("a" > 5)
TypeError: '>' not supported between instances of 'str' and 'int'
```

## Logical Operators

```python
>>> not True
False
>>> not False
True
>>> True and True
True
>>> True and False
False
>>> True or True
True
>>> True or False
True
```

Let `a` and `b` be variable names with Boolean values.

| **a** | **b** | **not a** | **a and b** | **a or b** |
| ----- | ----- | ----- | ----- | ----- |
| True  | True  | False | True  | True  |
| True  | False |       | False | True  |
| False | True  | True  | False | True  |
| False | False |       | False | False |

## Control Flow / Branching

```python
# branch.py

x = int(input("Can I have a value for x? "))
# Consider 5, -1, 0

if x > 0:
    print("x is positive")
```

Let's introduce the `else` statement.

```python
if x > 0:
    print("x is positive")
else:
    print("x is negative")
```

Is this true? What about zero? Let's also introduce the `elif` statement.

```python
# branch.py

x = int(input("Can I have a value for x? "))

if x > 0:
    print("x is positive")
elif x < 0:
    print("x is negative")
else:
    print("x is neither positive nor negative!")
```

## abc.py

```python
# abc.py

print("Can I have an a, b, or c?")
letter = input("> ")

if letter == a or letter == b or letter == c:
    print("Thanks for the letter!")
else:
    print(f"I didn't want a {letter}...")
```

## Exercise: Compare

Write a program that asks the user for an `x` and `y`, and then it prints how `x` compares (less than, greater than, or equal) to `y`.

Test the program with `x = 10` and `y = 2` and make sure the output is that `x is greater than y`.

```python
# compare.py
x = float(input("x = "))
y = float(input("y = "))

# The first branch that evaluate to True runs, and then the rest of the branches are ignored.
if x < y:
    print('x is less than y')
elif x > y:
    print('x is greater than y')
else:
    print('x and y are equal')
```

## Nested Execution

Indentation is important in Python, as it creates "blocks"of code.

```python
if x == y:
    print('x and y are equal')
else:
    if x < y:
        print('x is less than y')
    else:
        print('x is greater than y')

# Equivalently... 
# This approach is preferred because it has less indentation.
if x == y:
    print('x and y are equal')

if x < y:
    print('x is less than y')
else:
    print('x is greater than y')
```

## Compound Inequalities

```python
if 0 < x:
    if x < 10:
        print('x is a positive single-digit number.')
 
if 0 < x and x < 10:
    print('x is a positive single-digit number.')
    
if 0 < x < 10: # not available in all languages
    print('x is a positive single-digit number.')
```

## Guessing Game

```python
# guess.py
target = 55
print("I am thinking of a number! Try to guess it.")
guess = int(input("> "))


if target == guess:
    print("That's it!")
else:
    print("Nope!")
```

What if the user needs more than one guess?

## Iteration with `while`


![Alt text](../../Assets/while-loop-diagram.svg)

`while` when we do not know how long something will take.

Let's allow the user to guess until they get it correct.

```python
# guess.py
target = 55
print("I am thinking of a number! Try to guess it.")
guess = int(input("> "))

while guess != target:
    print("Try again!)
    guess = int(input("> "))

print("That's it!")
```

You will probably get stick in a `while` loop. Use `Ctrl + C` (Windows) or `Cmd + C` (MacOS) to `KeyboardInterrupt` execution.

```python
# stuck.py
n = 0
while n < 5:
    print(f"{n} is less than 5. You're stuck!)    
```

You will need a counter variable to stop the `while` loop.

```python
n = 0
# n is a counter variable
# It needs to be declared outside the loop

while n <5:
    print(n)
    n += 1
```

## break

The `break` keyword is used to exit a loop.

Let's find a positive integer that is both divisible by both 11 and 12.
Because we don't know the first number divisible, a `while` loop is a good tool

```python
# divisible.py

x = 1
while True:
    print("Checking", x)
    if x % 11 == 0 and x % 12 == 0:
        break
    x += 1

print(f"{x} is divisible by 11 and 12")
```

## Exercise

Find the *third* positive integer divisible by 17 and 23.

```python
x = 1
counter = 0

while True:
    print("Checking", x)

    # Check if divisible
    if x % 17 == 0 and x % 23 == 0: 
        
        # if divisible, increment counter,
        # break after finding third divisor
        counter += 1  
        if counter == 3:
            break

        # increment integer to be checked
        x += 1

print(x, 'is divisible by 11 and 12') 
```

## `for` loops

`for` loops are used when we know how long we need to iterate.

```python
# This declare a variable named n
# it takes on the values 0 <= i < n,
# incrementing each time through the loop
for n in range(5):
    print(n)
```


Exercise [TBD] will cover more details about the `range` function.

## `continue`

The `continue` keyword is used end the current iteration in a loop and continue to the next iteration.

```python
for n in range(5):
    if n == 4:
        continue
    print(n)
```

## Exercise

Compute the sum of the first 123,456,789 *square* integers. That is, find 
$$\sum_{i=1}^{123,456,789} i^2$$

```python
total = 0

for i in range(123_456_789):
    total += i ** 2

print(total)

# Alternatively, used the closed-form formula for the sum of n squares
n = 123_456_789
total = (n * (n + 1) * (2 * n +1)) / 6
print(total)
```

## VS Code Debugging

## Exercises

Complete exercises 11 through 14.
