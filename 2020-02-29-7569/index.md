# [백준]7569 토마토

https://www.acmicpc.net/problem/7569

# 풀이:

[[백준\]7576 토마토](https://jyukki97.github.io/blog/2020-02-28-7576/) 참고



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <queue>
using namespace std;
int n, m, h, k, q, w, e, a[102][102][102];
queue<pair<int, pair<int, int>>> dp2;
int main() {
	cin >> m >> n >> h;
	for (int y = 0; y < h; y++)
		for (int i = 0; i < n; i++)
			for (int t = 0; t < m; t++) {
				cin >> a[y][i][t];
				if (a[y][i][t] == 1)	dp2.push({ y, {i,t} });
			}
	for (int i = 0;; i++) {
		queue<pair<int, pair<int, int>>> dp1;
		while (!dp2.empty()) {
			q = dp2.front().first;
			w = dp2.front().second.first;
			e = dp2.front().second.second;
			if (w + 1 < n && !a[q][w + 1][e]) {
				dp1.push({ q,{w + 1, e} });
				a[q][w + 1][e]++;
			}
			if (q + 1 < h && !a[q + 1][w][e]) {
				dp1.push({ q + 1,{w, e} });
				a[q + 1][w][e]++;
			}
			if (w >= 1 && !a[q][w - 1][e]) {
				dp1.push({ q,{w - 1, e} });
				a[q][w - 1][e]++;
			}
			if (q >= 1 && !a[q - 1][w][e]) {
				dp1.push({ q - 1,{w, e} });
				a[q - 1][w][e]++;
			}
			if (e + 1 < m && !a[q][w][e + 1]) {
				dp1.push({ q,{w, e + 1} });
				a[q][w][e + 1]++;
			}
			if (e >= 1 && !a[q][w][e - 1]) {
				dp1.push({ q,{w, e - 1} });
				a[q][w][e - 1]++;
			}
			dp2.pop();
		}
		if (dp1.empty()) {
			k = i;
			break;
		}
		dp2 = dp1;
	}
	for (int y = 0; y < h; y++)
		for (int i = 0; i < n; i++)
			for (int t = 0; t < m; t++)
				if (!a[y][i][t]) {
					k = -1;
					break;
				}
	cout << k << endl;
}
```

