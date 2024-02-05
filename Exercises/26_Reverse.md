# Reverse Halves

Given a string, cut it into two equal parts. If the length of the string is odd, leave the middle character within the first chunk, so that the first string contains one more character than the second. Now print a new string on a single row with the first and second halves swapped: second half first and the first half last.

Can you solve it without using `if`?

# Example input

```
Qwerty
```

# Example output

```
rtyQwe
```

<details>
<summary style="font-weight:bold">Solution</summary>
<br>

``` python
s = input()

l = len(s)

first_half = s[:(l // 2) + 1]

second_half = s[l // 2:]
print(second_half + first_half)
```

</details>