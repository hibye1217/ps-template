# Input & Output

## Input

| Method                               | **C**: `scanf`                | **C++**: `cin`    | **Python**: `input`                   |
| ------------------------------------ | ----------------------------- | ----------------- | ------------------------------------- |
| Integer $n$                          | `int`: `scanf("%d", &n);`     | `cin >> n;`       | `n = int(input())`                    |
|                                      | `ll`: `scanf("%lld", &n);`    |                   |                                       |
| $n$ integers $A_1, A_2, \ldots, A_n$ | `for` loop                    | `for` loop        | `A = list(map(int, input().split()))` |
| Real number $x$                      | `float`: `scanf("%f", &x);`   | `cin >> x`        | `x = float(input())`                  |
|                                      | `double`: `scanf("%lf", &x);` |                   |                                       |
|                                      | `ld`: `scanf("%Lf", &x);`     |                   |                                       |
| Character $c$                        | `scanf("%c", &c);`            | `cin >> c;`       | `c = input()`                         |
| String $s$                           | `scanf("%s", s);`             | `cin >> s;`       | `s = input()`                         |
| Line $L$                             | `fgets(L, sizeof(L), stdin);` | `getline(cin, L)` | `L = input()`                         |
| Buffer Clear                         |                               | `cin.ignore()`    |                                       |

### Fast Input

#### C++

```cpp
#include <bits/stdc++.h>
using namespace std;

int main(){
    ios_base::sync_with_stdio(0); cin.tie(0); cout.tie(0);
}
```

#### Python

```py
import sys
input = lambda: sys.stdin.readline().rstrip('\n')
```

## Output

| Method                               | **C**: `printf`                    | **C++**: `cout`                                          | **Python**: `print`       |
| ------------------------------------ | ---------------------------------- | -------------------------------------------------------- | ------------------------- |
| Integer $n$                          | `int`: `printf("%d", n);`          | `cout << n;`                                             | `print(n)`                |
|                                      | `ll`: `printf("%lld", n);`         |                                                          |                           |
| $n$ integers $A_1, A_2, \ldots, A_n$ | `for` loop                         | `for` loop                                               | `print(*A)`               |
| Real number $x$                      | `float`: `printf("%f", x);`        | `cout << x;`                                             | `print(x)`                |
|                                      | `double`: `printf("%lf", x);`      |                                                          |                           |
|                                      | `long double`: `printf("%Lf", x);` |                                                          |                           |
| Real number $x$ with precision $d$   | `printf("%.<d>f", x);`             | `cout.setf(ios::fixed); cout.precision(d);` `cout << x;` | `print(f"{x:.<d>f}")`     |
| Character $c$                        | `printf("%c", c);`                 | `cout << c;`                                             | `print(c)`                |
| String $s$                           | `printf("%s", s);`                 | `cout << s;`                                             | `print(s)`                |
| EndLine `\n`                         | `printf("\n");`                    | `cout << endl;`                                          | `print` auto              |
|                                      |                                    |                                                          | Turn off: `print(end='')` |
| Buffer Clear                         | `fflush(stdout)`                   | `cout << endl;` automatically does that                  | // TODO                   |
|                                      |                                    | `cout << flush;` for manual                              |                           |

