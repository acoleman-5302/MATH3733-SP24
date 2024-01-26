# Sideways Triangles

Be sure to use pencil and paper when problem solving. This problems involves the ability to:

- Display a row of symbols of a particular length using a loop
- Display a series of rows using nested loops
- Create a varying number of symbols in each row using an algebraic expressions instead of a fixed value
- Discover the correct algebraic expression through experimentation and analysis

# Instructions
Ask the user for input for a width `w` of a sideways triangle.

Write a program that uses only two output statements, `print("#", end="")` and `print()` to produce triangle of `#` with maximum width `w`.

## Example (`w=1`)

```
#
```

## Example (`w=2`)

```
#
##
#
```

## Example (`w=3`)
```
#
##
###
##
#
```

## Example (`w=4`)
```
#
##
###
####
###
##
#
```


<details>
<summary style="font-weight:bold">Solution</summary>
<br>

``` python
w = int(input())

h = 2 * w - 1
for i in range(1, h+1):
    for j in range(w - abs(w-i)):
        print("#", end="")
    print()
```

</details>