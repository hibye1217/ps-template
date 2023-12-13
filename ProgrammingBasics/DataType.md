# Data Type

## Integer

| Type                        | Range                 | Approx.             |
| --------------------------- | --------------------- | ------------------- |
| **C**: `int`                | $[-2^{31}, 2^{31})$   | $2 \cdot 10^9$      |
| **C**: `long long`          | $[-2^{63}, 2^{63})$   | $9 \cdot 10^{18}$   |
| **C**: `unsigned long long` | $[0, 2^{64})$         | $1.8 \cdot 10^{19}$ |
| **C**: `__int128`           | $[-2^{127}, 2^{127})$ | $10^{37}$           |
| **Python**: `int`           | $(-\infty, \infty)$   | $\infty$            |

## Real Number

| Type                 | Precision |
| -------------------- | --------- |
| **C**: `float`       | $6$       |
| **C**: `double`      | $15$      |
| **Python**: `float`  | $15$      |
| **C**: `long double` | $33$      |

## Character

| Type              | CharSet |
| ----------------- | ------- |
| **C**: `char`     | ASCII   |
| **C++**: `string` | ASCII   |
| **Python**: `str` | UTF-8   |

## Boolean

| Type               | Constant        |
| ------------------ | --------------- |
| **C++**: `bool`    | `true`, `false` |
| **Python**: `bool` | `True`, `False` |

