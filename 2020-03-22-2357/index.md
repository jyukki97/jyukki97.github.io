# [백준]2357 최솟값과 최댓값

https://www.acmicpc.net/problem/2357

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
ll n, m, a, b; vector<ll> T, Y;
void update(int node, int idx, ll val, int x, int y) {
	if (idx < x || idx > y) return;
	T[node] = T[node] > val ? T[node] : val;
	Y[node] = Y[node] > val ? val : Y[node];
	if (x != y)	
        update(node * 2, idx, val, x, (x + y) / 2), 
    	update(node * 2 + 1, idx, val, (x + y) / 2 + 1, y);
}
ll min(int node, int x, int y, int s, int e) {
	if (e < x || s > y)	return 1000000001;
	if (s <= x && e >= y)	return Y[node];
	int i = min(node * 2, x, (x + y) / 2, s, e),
    t = min(node * 2 + 1, (x + y) / 2 + 1, y, s, e);
	return i > t ? t : i;
}
ll max(int node, int x, int y, int s, int e) {
	if (e < x || s > y)	return 0;
	if (s <= x && e >= y)	return T[node];
	int i = max(node * 2, x, (x + y) / 2, s, e), 
    t = max(node * 2 + 1, (x + y) / 2 + 1, y, s, e);
	return i > t ? i : t;
}
int main() {
	scanf("%d%d",&n,&m);
	a = 1 << (int)(ceil(log2(n)) + 1), T.resize(a), Y.resize(a, 1000000001);
	for (int i = 0; i < n; i++) {
		scanf("%d",&a);
		update(1, i, a, 0, n - 1);
	}
	for (int i = 0; i < m; i++) {
		scanf("%d%d",&a,&b);
		printf("%lld %lld\n",min(1, 0, n - 1, a - 1, b - 1),
               max(1, 0, n - 1, a - 1, b - 1));
	}
}
```

