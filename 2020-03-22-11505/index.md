# [백준]11505 구간 곱 구하기

https://www.acmicpc.net/problem/11505

# 풀이:

[[백준\]2042 구간 합 구하기](https://jyukki97.github.io/blog/2020-03-22-2042/) 참고



###### cin, cout 은 시간초과가 나므로 주의

# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <math.h>
using namespace std;
#define ll long long
ll n, m, k, a, b, c; vector<ll> T;
ll update(int node, int idx, ll val, int x, int y) {
    if (idx < x || idx > y) return T[node];
    if (x == y) return T[node] = val;
    return T[node] = (update(node * 2, idx, val, x, (x + y) / 2) 
		* update(node * 2 + 1, idx, val, (x + y) / 2 + 1, y)) % 1000000007;
}
ll mul(int node, int x, int y, int s, int e) {
	if (e < x || s > y)	return 1;
	if (s <= x && e >= y)	return T[node];
	return (mul(node * 2, x, (x + y) / 2, s, e)
		* mul(node * 2 + 1, (x + y) / 2 + 1, y, s, e)) % 1000000007;
}
int main() {
	scanf("%d%d%d",&n,&m,&k);
	T.resize(1 << (int)(ceil(log2(n)) + 1));
	for (int i = 0; i < n; i++) {
		scanf("%d",&c);
		update(1, i, c, 0, n - 1);
	}
	for (int i = 0; i < m + k; i++) {
		scanf("%d%d%d",&a,&b,&c);
		if (a == 1) update(1, b - 1, c, 0, n - 1);
		else printf("%lld\n",mul(1, 0, n - 1, b - 1, c - 1));
	}
}
```

