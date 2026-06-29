## Perfect Number

### Definition
A **Perfect Number** is a positive integer that is equal to the sum of all of its **proper divisors** (excluding the number itself).

A proper divisor is a number that divides the given number completely without leaving any remainder.

### Example

Consider the number **28**.

Proper divisors of 28 are:

```
1, 2, 4, 7, 14
```

Sum of divisors:

```
1 + 2 + 4 + 7 + 14 = 28
```

Since the sum of all proper divisors is equal to the original number,

```
28 = 28
```

Therefore, **28 is a Perfect Number.**

### Logic

1. Read the number.
2. Initialize `sum = 0`.
3. Find all divisors from **1 to n-1**.
4. If the number is divisible by a divisor, add it to the sum.
5. After the loop, compare the sum with the original number.
6. If both are equal, the number is a Perfect Number; otherwise, it is not.

### Algorithm

1. Start
2. Input the number `n`
3. Set `sum = 0`
4. Repeat from `i = 1` to `n - 1`
   - If `n % i == 0`
     - `sum = sum + i`
5. If `sum == n`
   - Display **Perfect Number**
6. Else
   - Display **Not Perfect Number**
7. Stop

### Example Input

```
28
```

### Output

```
Perfect Number
```

## Palindrome Number

### Definition

A **Palindrome Number** is a number that remains the same when its digits are reversed.

### Examples

```
121
```

Reverse of 121

```
121
```

Since both are equal,

```
121 is a Palindrome Number.
```

Another Example

```
123
```

Reverse

```
321
```

Since both are different,

```
123 is not a Palindrome Number.
```

### Logic

1. Read the number.
2. Store the original number.
3. Extract the last digit using `% 10`.
4. Build the reverse number using:
   ```
   reverse = reverse × 10 + digit
   ```
5. Remove the last digit using `/ 10`.
6. Repeat until the number becomes 0.
7. Compare the original number with the reversed number.
8. If both are equal, the number is a Palindrome Number.

### Algorithm

1. Start
2. Input the number `n`
3. Store original number in `temp`
4. Set `reverse = 0`
5. Repeat while `n > 0`
   - `digit = n % 10`
   - `reverse = reverse × 10 + digit`
   - `n = n / 10`
6. If `temp == reverse`
   - Display **Palindrome Number**
7. Else
   - Display **Not Palindrome Number**
8. Stop

### Example Input

```
1221
```

### Output

```
Palindrome Number
```

## Armstrong Number

### Definition

An **Armstrong Number** is a number that is equal to the sum of each of its digits raised to the power of the total number of digits.

### Formula

```
Sum of (Digit ^ Number of Digits)
```

### Example 1

```
153
```

Number of digits = **3**

```
1³ + 5³ + 3³

= 1 + 125 + 27

= 153
```

Therefore,

```
153 is an Armstrong Number.
```

### Example 2

```
9474
```

Number of digits = **4**

```
9⁴ + 4⁴ + 7⁴ + 4⁴

= 6561 + 256 + 2401 + 256

= 9474
```

Therefore,

```
9474 is also an Armstrong Number.
```

### Logic

1. Read the number.
2. Store the original number.
3. Count the total number of digits.
4. Extract each digit using `% 10`.
5. Raise the digit to the power of the total number of digits.
6. Add the result to the sum.
7. Remove the last digit using `/ 10`.
8. Repeat until all digits are processed.
9. Compare the calculated sum with the original number.
10. If both are equal, the number is an Armstrong Number.

### Algorithm

1. Start
2. Input the number `n`
3. Store original number
4. Count the total number of digits
5. Set `sum = 0`
6. Repeat while number > 0
   - Extract last digit
   - Calculate `digit ^ count`
   - Add it to `sum`
   - Remove last digit
7. If `sum == original number`
   - Display **Armstrong Number**
8. Else
   - Display **Not Armstrong Number**
9. Stop

### Example Input

```
1634
```

### Calculation

```
1⁴ + 6⁴ + 3⁴ + 4⁴

= 1 + 1296 + 81 + 256

= 1634
```

### Output

```
Armstrong Number
```
