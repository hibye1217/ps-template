# Main Template

## Problem Solving

```cpp
#include <bits/stdc++.h>
#define endl '\n'
using namespace std;
const int PRECISION = 0;

void Main(){
    
}

int main(){
    ios_base::sync_with_stdio(0); cin.tie(0); cout.tie(0);
    cout.setf(ios::fixed); cout.precision(PRECISION); Main();
}
```

## Competitive Programming

```cpp
#include <bits/stdc++.h>
#define endl '\n'
const int PRECISION = 0;
using namespace std;
using ll = long long;
using ld = long double;
#define fr first
#define sc second
using pi2 = pair<int, int>;
using pl2 = pair<ll, ll>;
using pd2 = pair<ld, ld>;
template <typename T> using priority_stack = priority_queue< T, vector<T>, greater<T> >;
template <typename T1, typename T2> istream& operator>>(istream& in, pair<T1, T2>& p){
	return in >> p.fr >> p.sc;
}
template <typename T1, typename T2> ostream& operator<<(ostream& out, pair<T1, T2>& p){
	return out << p.fr << ' ' << p.sc;
}
template <typename T> inline void unq(vector<T>& v){
	sort(v.begin(), v.end());
	v.erase(unique(v.begin(), v.end()), v.end());
}
template <typename T> inline int cvt(vector<T>& v, T x){
	return lower_bound(v.begin(), v.end(), x) - v.begin() + 1;
}



void Main(){

}

int main(){
	ios_base::sync_with_stdio(0); cin.tie(0); cout.tie(0);
	cout.setf(ios::fixed); cout.precision(PRECISION);
	Main();
}
```