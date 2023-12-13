# Operator

## C++

| Order |  Operator   |   Example   |                           Explain                            |
| :---: | :---------: | :---------: | :----------------------------------------------------------: |
|  1 →  |    `::`     | `std::cin`  |                       Scope resolution                       |
|  2 →  | suffix `++` |    `n++`    |  Suffix incremental, add $1$ after end of other operations.  |
|       | suffix `--` |    `n--`    | Suffix decremental, subtract $1$ after end of other operations |
|       |  `type()`   |             |                       Functional cast                        |
|       |  `type{}`   |             |                                                              |
|       |    `f()`    | `foo(1, 2)` |                        Function call                         |
|       |    `a[]`    |  `arr[3]`   |                       Array subscript                        |
|       |     `.`     |  `nod.par`  |                  struct/class Member access                  |
|       |    `->`     | `nod->par`  |              struct/class pointer Member access              |
|  3 ←  | prefix `++` |    `++n`    |                 Prefix incremental, add $1$                  |
|       | prefix `--` |    `--n`    |               Prefix incremental, subtract $1$               |
|       |  unary `+`  |    `+x`     |                        Multiply $+1$                         |
|       |  unary `-`  |    `-x`     |                        Multiply $-1$                         |
|       |     `!`     |    `!b`     |                         Boolean NOT                          |
|       |     `~`     |    `~n`     |                         Bitwise NOT                          |
|       |    `(T)`    | `(int)3.6`  |                       C-style Casting                        |
|       | pointer `*` |    `*p`     |                      Pointer reference                       |
|       | address `&` |    `&x`     |                      Address reference                       |
|       |  `sizeof`   | `sizeof(A)` |            Size of a variable, by number of bytes            |
|       | `co_await`  |             |                                                              |
|       |    `new`    |             |                                                              |
|       |   `new[]`   |             |                                                              |
|       |  `delete`   |             |                                                              |
|       | `delete[]`  |             |                                                              |
|  4 →  |    `.*`     |  `nod.*p`   |              struct/class Member pointer access              |
|       |    `->*`    |  `nod->*p`  |          struct/class pointer Member pointer access          |
|  5 →  |     `*`     |    `a*b`    |                         $a \times b$                         |
|       |     `/`     |    `a/b`    |    $a \div b$, round toward $0$ if operands are integer.     |
|       |     `%`     |    `a%b`    |          $a \bmod b$, negative if $a \cdot b < 0$.           |
|  6 →  |     `+`     |    `a+b`    |                            $a+b$                             |
|       |     `-`     |    `a-b`    |                            $a-b$                             |
|  7 →  |    `>>`     |   `a>>b`    |   Bitwise Right Shift $a$ by $b$ bits. Added bits are $0$.   |
|       |    `<<`     |   `a<<b`    |   Bitwise Left Shift $a$ by $b$ bits. Added bits are $0$.    |
|  8 →  |    `<=>`    |      -      |                                                              |
|  9 →  |     `<`     |    `a<b`    |                         is $a < b$?                          |
|       |    `<=`     |   `a<=b`    |                        is $a \le b$?                         |
|       |     `>`     |    `a>b`    |                         is $a > b$?                          |
|       |    `>=`     |   `a>=b`    |                        is $a \ge b$?                         |
| 10 →  |    `==`     |   `a==b`    |                         is $a = b$?                          |
|       |    `!=`     |   `a!=b`    |                        is $a \neq b$?                        |
| 11 →  |     `&`     |    `a&b`    |                         Bitwise AND                          |
| 12 →  |     `^`     |    `a^b`    |                         Bitwise XOR                          |
| 13 →  |     `|`     |    `a|b`    |                          Bitwise OR                          |
| 14 →  |    `&&`     |   `a&&b`    | Logical AND. Short circuiting applies.<br />If $a$ is `false`, then $b$ does not evaluated. |
| 15 →  |    `||`     |   `a||b`    | Logical OR. Short circuiting applies.<br />If $a$ is `true`, then $b$ does not evaluated. |
| 16 ←  |   `?` `:`   |   `a?b:c`   |                     Ternary conditional                      |
|       |   `throw`   |             |                                                              |
|       | `co_yield`  |             |                                                              |
|       |     `=`     |    `a=b`    |               Assign $b$ to the variable $a$.                |
|       |    `+=`     |   `a+=b`    | Add $b$ to the variable $a$.<br />Equivalently, assign $a+b$ to the variable $a$. |
|       |    `-=`     |   `a-=b`    | Subtract $b$ to the variable $a$.<br />Equivalently, assign $a-b$ to the variable $a$. |
|       |    `*=`     |   `a*=b`    | Multiply $b$ to the variable $a$.<br />Equivalently, assign $a \times b$ to the variable $a$. |
|       |    `/=`     |   `a/=b`    | Divide $b$ to the variable $a$.<br />Equivalently, assign $a \div b$ to the variable $a$. |
|       |    `%=`     |   `a%=b`    | Apply modulo $b$ to the variable $a$.<br />Equivalently, assign $a \bmod b$ to the variable $a$. |
|       |    `>>=`    |   `a>>=b`   | Apply Bitwise Right Shift by $b$ bits to the variable $a$.<br />Equivalently, assign $a \gg b$ to the variable $a$. |
|       |    `<<=`    |   `a<<=b`   | Apply Bitwise Left Shift by $b$ bits to the variable $a$.<br />Equivalently, assign $a \ll b$ to the variable $a$. |
|       |    `&=`     |   `a&=b`    | Apply Bitwise AND with $b$ to the variable $a$.<br />Equivalently, assign $a \text{ \& } b$ to the variable $a$. |
|       |    `^=`     |   `a^=b`    | Apply Bitwise XOR with $b$ to the variable $a$.<br />Equivalently, assign $a \oplus b$ to the variable $a$. |
|       |    `|=`     |   `a|=b`    | Apply Bitwise OR with $b$ to the variable $a$.<br />Equivalently, assign $a \mid b$ to the variable $a$. |
| 17 →  |     `,`     |   `a, b`    |                                                              |