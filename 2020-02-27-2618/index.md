# [백준]2618 경찰차

https://www.acmicpc.net/problem/2618

# 풀이:

DP\[i][t] : 첫번째 경찰차가 i 번째 사건을, 두번째 경찰차가 t 번째 사건을 처리했을 때, 이동하는 거리의 합의 최소값

i 와 t 의 차이가 1 이라면, 

DP\[i][t] = DP\[i][0 ~ t - 1] (t 번째와 0 ~ t - 1 번째 사이의 거리)까지의 최소값

1이 아니라면,

DP\[i][t] = DP\[i][t - 1] + (t 번째와 t - 1 번째 사이의 거리) 

을 통해 최솟값을 구할 수 있다.



최솟값을 구한 후, 최솟값을 구한 경로를 역순으로 추적하여, 맡겨진 경찰차의 번호를 구한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int m, n, x[1002], y[1002], dp[1002][1002], mi = 987654321, q, w, e[1002];
int po(int a, int b) {
	if ((!a && !b) || dp[a][b])	return dp[a][b];
	if (a < b)
		if (b - a == 1) {
			dp[a][b] = po(a, 0) + 2 * n - x[b] - y[b];
			for (int i = 1; i < a; i++)
				dp[a][b] = min(dp[a][b], po(a, i) + abs(x[b] - x[i]) + abs(y[b] - y[i]));
		}
		else
			dp[a][b] = po(a, b - 1) + abs(x[b - 1] - x[b]) + abs(y[b - 1] - y[b]);
	else
		if (a - b == 1) {
			dp[a][b] = po(0, b) + x[a] + y[a] - 2;
			for (int i = 1; i < b; i++)
				dp[a][b] = min(dp[a][b], po(i, b) + abs(x[a] - x[i]) + abs(y[a] - y[i]));
		}
		else
			dp[a][b] = po(a - 1, b) + abs(x[a - 1] - x[a]) + abs(y[a - 1] - y[a]);
	return dp[a][b];
}
int main() {
	cin >> n >> m;
	for (int i = 1; i <= m; i++)
		cin >> x[i] >> y[i];
	for (int i = 0; i < m; i++) {
		po(m, i);
		po(i, m);
		if (mi > dp[m][i]) {
			mi = dp[m][i];
			q = m, w = i;
		}
		if (mi > dp[i][m]) {
			mi = dp[i][m];
			q = i, w = m;
		}
	}
	for (int i = m; i > 0; i--) {
		if (q == i) {
			e[i] = 1;
			if (w == i - 1) {
				for (int t = 0; t < w; t++) {
					if (dp[t][w] + abs(x[q] - x[t]) + abs(y[q] - y[t]) == dp[q][w]) {
						q = t;
						break;
					}
				}
			}
			else 	q--;
		}
		else if (w == i) {
			e[i] = 2;
			if (q == i - 1) {
				e[i - 1] = 1;
				for (int t = 0; t < q; t++) {
					if (dp[q][t] + abs(x[w] - x[t]) + abs(y[w] - y[t]) == dp[q][w]) {
						w = t;
						break;
					}
				}
			}
			else	w--;
		}
	}
	cout << mi << endl;
	for (int i = 1; i <= m; i++)
		cout << e[i] << endl;
}
```

