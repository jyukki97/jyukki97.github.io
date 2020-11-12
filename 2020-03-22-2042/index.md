# [백준]2042 구간 합 구하기

https://www.acmicpc.net/problem/2042

# 풀이:

https://www.acmicpc.net/blog/view/9 참고



크기가 2 ^ (log2(n) + 1)  인 트리를 하나 만든다.

N개의 값을 트리에 모두 저장한다.

a 가 1 이라면, b번째 값을 c로 수정한다.

a 가 2 라면, 2 ~ 5 까지의 모든 수의 합을 출력한다.



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
    return T[node] = update(node * 2, idx, val, x, (x + y) / 2) 
        + update(node * 2 + 1, idx, val, (x + y) / 2 + 1, y);
}
ll sum(int node, int x, int y, int s, int e) {
	if (e < x || s > y)	return 0;
	if (s <= x && e >= y)	return T[node];
	return sum(node * 2, x, (x + y) / 2, s, e) 
        + sum(node * 2 + 1, (x + y) / 2 + 1, y, s, e);
}
int main() {
	cin >> n >> m >> k;
	T.resize(1 << (int)(ceil(log2(n)) + 1));
	for (int i = 0; i < n; i++) {
		cin >> c;
		update(1, i, c, 0, n - 1);
	}
	for (int i = 0; i < m + k; i++) {
		cin >> a >> b >> c;
		if (a == 1) update(1, b - 1, c, 0, n - 1);
		else cout << sum(1, 0, n - 1, b - 1, c - 1) << endl;
	}
}
```

