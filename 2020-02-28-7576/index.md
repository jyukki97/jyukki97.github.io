# [백준]7576 토마토

https://www.acmicpc.net/problem/7576

# 풀이:

[[백준\]2178 미로 탐색](https://jyukki97.github.io/blog/2020-02-28-2178/) 참고



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <queue>
using namespace std;
int n, m, k, q, w, a[1002][1002];
queue<pair<int, int>> dp2;
int main() {
	cin >> m >> n;
	for (int i = 0; i < n; i++)
		for (int t = 0; t < m; t++) {
			cin >> a[i][t];
			if (a[i][t] == 1)	dp2.push({ i,t });
		}
	for (int i = 0;; i++) {
		queue<pair<int, int>> dp1;
		while (!dp2.empty()) {
			q = dp2.front().first;
			w = dp2.front().second;
			if (w + 1 < m && !a[q][w + 1]) {
				dp1.push({ q,w + 1 });
				a[q][w + 1]++;
			}
			if (q + 1 < n && !a[q + 1][w]) {
				dp1.push({ q + 1,w });
				a[q + 1][w]++;
			}
			if (w >= 1 && !a[q][w - 1]) {
				dp1.push({ q,w - 1 });
				a[q][w - 1]++;
			}
			if (q >= 1 && !a[q - 1][w]) {
				dp1.push({ q - 1,w });
				a[q - 1][w]++;
			}
			dp2.pop();
		}
		if (dp1.empty()) {
			k = i;
			break;
		}
		dp2 = dp1;
	}
	for (int i = 0; i < n; i++)
		for (int t = 0; t < m; t++)
			if (!a[i][t]) {
				k = -1;
				break;
			}
	cout << k << endl;
}
```

