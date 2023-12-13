# Miscellaneous

## Data Types

### Primitive Types

```cpp
using ll = long long;
using ld = long double;
using ull = unsigned long long;
using i128 = __int128; // GCC
```

### Pairs

```cpp
#define fr first
#define sc second
using pi2 = pair<int, int>;
using pl2 = pair<ll, ll>;
using pd2 = pair<ld, ld>;
#define mkp make_pair

using cpl = complex<ld>;
```

### Data Structures

```cpp
template <typename T> using priority_stack = priority_queue< T, vector<T>, greater<T> >;
template <typename T> using matrix = vector< vector<T> >;
```

## Constants

```cpp
const ld PI = acosl(-1);
const ld TAU = 2*PI;
const ld E = 2.718281828459045;
const ld eps = 1e-15;

const ll mod = 1e9+7; // 1e9+9 // 998244353
```

## Optimizations

```cpp
#pragma GCC optimize("Ofast")
// TODO: avx
```

## Randomizations

```cpp
const time_t TIME = chrono::high_resolution_clock::now().time_since_epoch().count();
mt19937 gen(TIME);

uniform_int_distribution<int> rnd(a, b); // Random number in [a, b]
void usage(){
    int value = rnd(gen);
    shuffle(begin, end, gen);
}
```

## Bitwise Operations

```cpp
inline int bitc(int x){ return __builtin_popcount(x); }
inline int bitl(int x){ return __builtin_clz(x); }
inline int bitr(int x){ return __builtin_ctz(x); }
```

## Custom Compare

### [With same type] Data Structures

```cpp
bool cmp(int a, int b){ return a < b; }
void usage(){
    sort(begin, end, cmp);           // First -> Last
    set<int, decltype(&cmp)> s(cmp); // First -> Last (inorder)
    priority_queue<int, vector<int>, decltype(&cmp)> pq(cmp); // Last on Top
}
```

### [With different type] Binary Search

```cpp
sort(v.begin(), v.end(), [](pi2 a, pi2 b){ return a.fr+a.sc < b.fr+b.sc; });
auto st = lower_bound(v.begin(), v.end(), x, [](pi2 p, int x){ return p.fr+p.sc < x; });
auto ed = upper_bound(v.begin(), v.end(), x, [](int x, pi2 p){ return p.fr+p.sc < x; });
// [st, ed) is where p.fr+p.sc == x
```