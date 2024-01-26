# Digits

Given a two-digit integer, print its left digit (a tens digit) and then its right digit (a ones digit). Use the operator of integer division for obtaining the tens digit and the operator of taking remainder for obtaining the ones digit.

## Example input

```text
79
```

## Example output

```text
7 9
```


<details>
<summary style="font-weight:bold">Solution</summary>
<br>

``` python
n = input()

tens = int(n) // 10
ones = int(n) % 10

print(tens, ones)
```

</details>